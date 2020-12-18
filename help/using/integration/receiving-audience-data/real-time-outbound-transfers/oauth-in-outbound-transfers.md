---
description: リアルタイムサーバー間統合を使用してパートナー宛先にセグメントを公開する場合、Audience Manager は、リクエストをおこなう際に OAuth 2.0 を使用して認証するように設定できます。これは、Audience Manager からお客様のエンドポイントに認証済みリクエストを発行できることを表しています。
seo-description: リアルタイムサーバー間統合を使用してパートナー宛先にセグメントを公開する場合、Audience Manager は、リクエストをおこなう際に OAuth 2.0 を使用して認証するように設定できます。これは、Audience Manager からお客様のエンドポイントに認証済みリクエストを発行できることを表しています。
seo-title: リアルタイムのアウトバウンド転送での OAuth 2.0 統合
solution: Audience Manager
title: リアルタイムのアウトバウンド転送での OAuth 2.0 統合
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
translation-type: ht
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: ht
source-wordcount: '492'
ht-degree: 100%

---


# リアルタイムアウトバウンド転送への [!DNL OAuth 2.0] の統合 {#oauth-integration-for-real-time-outbound-transfers}

リアルタイムサーバー間統合を使用してパートナー宛先にセグメントを公開する場合、Audience Manager は、リクエストをおこなう際に [!DNL OAuth 2.0] を使用して認証するように設定できます。これは、Audience Manager からお客様のエンドポイントに認証済みリクエストを発行できることを表しています。

## 認証フロー {#auth-flow}

[!DNL Adobe Audience Manager][ の OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) 認証実装は、クライアント資格情報許可フローに基づいていて、次の手順に従っています。

1. 次の情報を指定する必要があります。
   * 認証トークンを生成する [!DNL OAuth 2.0] エンドポイント。
   * トークンの生成に使用する資格情報。
1. 提供された情報を使用して、[!DNL Audience Manager] コンサルタントが [宛先](../../../features/destinations/destinations.md)を設定します。
1. セグメントがこの宛先にマッピングされると、リアルタイムデータ転送システム（[IRIS](../../../reference/system-components/components-data-action.md#iris)）がトークンエンドポイントへの `POST` リクエストを作成し、bearer トークンの資格情報を交換します。
1. パートナーエンドポイントへのセグメント公開リクエストごとに、[!UICONTROL IRIS] は bearer トークンを使用して認証をおこないます。

![](assets/oauth2-iris.png)

## 要件 {#auth-requirements}

[!DNL Audience Manager] パートナーが認証済みリクエストを受け取るには、次のエンドポイントが必要です。

### エンドポイント 1：IRIS が bearer トークンの取得に使用

このエンドポイントは手順 1 で指定された資格情報を受け取り、以降のリクエストで使用する bearer トークンを生成します。

* このエンドポイントは `HTTP POST` リクエストを受け入れる必要があります。
* このエンドポイントは [!DNL Authorization] ヘッダーを受け入れ、参照する必要があります。このヘッダーの値は `Basic <credentials_provided_by_partner>` となります。
* このエンドポイントは [!DNL Content-type] ヘッダーを参照し、値が「`application/x-www-form-urlencoded ; charset=UTF-8`」であることを検証する必要があります。
* リクエストの本文は `grant_type=client_credentials` となります。

### Audience Manager により bearer トークンの取得のためパートナーエンドポイントに対して作成されたリクエストの例

```
POST /oauth2/token HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Basic zq2LOO1CcYGrODS5nXiNHpEz97eCpVHAoMF8pAgCntXAzxp5uRV7DTAE2qtPLjhMQwrEX3O6MHV4S
Content-Type: application/x-www-form-urlencoded;charset=UTF-8
Content-Length: 29
Accept-Encoding: gzip
  
grant_type=client_credentials
```

### パートナーエンドポイントからの応答の例

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### エンドポイント 2：IRIS が bearer トークンによるセグメントの公開に使用

[!DNL Audience Manager] は、ユーザーがセグメントで認定されるとほぼリアルタイムでこのエンドポイントにデータを送信します。さらに、この方法では 24 時間ごとにオフラインまたは転送済みのデータのバッチを送信できます。

エンドポイント 1 で生成された bearer トークンは、このエンドポイントへのリクエストの発行に使用されます。[!DNL Audience Manager] のリアルタイムデータ転送システム（[IRIS](../../../reference/system-components/components-data-action.md#iris)）は、通常の HTTPS リクエストを作成し、Authorization ヘッダーを挿入します。このヘッダーの値は Bearer `<bearer token from step 1>` となります。

### パートナーエンドポイントからの応答の例

```
GET /segments/aam HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Bearer glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY
Content-Type: application/json
Accept-Encoding: gzip
   
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   }]
}
```

>[!NOTE]
>
>このリクエストには標準ペイロード（リクエスト）が含まれています。

## 重要な考慮事項 {#considerations}

### トークンはパスワード

パートナーから提供される資格情報や、[!DNL OAuth 2.0] フローによる認証時に [!DNL Audience Manager] が取得するトークンは機密情報です。サードパーティとは共有しないでください。

### [!DNL SSL] が必須

[!DNL SSL]認証プロセスを保護するために、 を使用する必要があります。トークンの取得や使用のためのリクエストを含め、すべてのリクエストが `HTTPS` エンドポイントを使用する必要があります。