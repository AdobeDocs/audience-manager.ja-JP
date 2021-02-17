---
description: /event 呼び出しで DCS 応答を要求する方法については、ここを参照してください。この節では、応答の例と、応答でよく使用されるデータ要素の定義を示します。
seo-description: /event 呼び出しで DCS 応答を要求する方法については、ここを参照してください。この節では、応答の例と、応答でよく使用されるデータ要素の定義を示します。
seo-title: DCS からのデータ受信
solution: Audience Manager
title: DCS からのデータ受信
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 100%

---


# DCS からのデータ受信 {#receive-data-from-the-dcs}

[!DNL DCS] 呼び出しで `/event` 応答を要求する方法については、こちらを参照してください。この節では、応答の例と、応答でよく使用されるデータ要素の定義を示します。

このコンテンツを確認する前に、[DCS へのデータ送信](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)を参照してください。

## DCS 応答パラメーター：復習 {#dcs-response-parameters}

[!DNL DCS] からの応答を受信する場合は、`d_rtbd=json` 要求に [!DNL DCS] を含める必要があります。このパラメーターを省略した場合、[!DNL DCS] はデータを返しません。データを要求する場合の [!DNL DCS] への基本的な呼び出しでは、次の構文を使用します。

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## レスポンスのサンプル {#sample-response}

[DCS へのデータ送信](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)ドキュメントで、架空の会社 [!DNL Acme, Inc.] がこの呼び出しをおこなったことを思い出してください。

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

この呼び出しには必要な応答パラメーターが含まれているので、[!DNL DCS] は以下のような [!DNL JSON] オブジェクトを送り返します。実際の応答は、これと同様の場合もあれば、もっと複雑な場合もあります。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 応答パラメーター {#response-parameters}

[!DNL DCS] からの応答でよく見かけるパラメーターを、それぞれ次の表で定義します。これは、イベント呼び出しや、データを返すその他の [!DNL DCS][!DNL API] クエリに当てはまります。

| パラメーター | 説明 |
|--- |--- |
| `c` | [URL の宛先](../../../features/destinations/create-url-destination.md)として設定された URL です。 |
| `cn` | [Cookie の宛先](../../../features/destinations/create-cookie-destination.md)の Cookie 名フィールドに設定された名前または ID です。 |
| `cv` | &quot;cn&quot;:&quot;destinaton name&quot; パラメーターで定義された宛先に送信された値です。 |
| `dcs_region` | [サーバー間 DCS 呼び出し](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | このオブジェクトには、UI で設定されるすべての URL 宛先の情報が含まれています。このオブジェクトの値（リスト）は、ユーザーのアクションに応じて動的に変わります。 |
| `dmn` | Cookie の宛先の「Cookie Domain」フィールドに指定されたドメインです。[Cookie の宛先のオプション設定](../../../features/destinations/cookie-destination-options.md)を参照してください。サーバー間統合の場合は、`aam-api.com` などのドメインを使用することをお勧めします。 |
| `e` | URL の宛先に設定されたセキュア URL です。 |
| `stuff` | このオブジェクトには、すべての Cookie の宛先の情報が含まれています。このオブジェクトの値（リスト）は、ユーザーのアクションに応じて動的に変わります。 |
| `tid` | トランザクション ID（デバッグ目的で使用される 12 文字の一意の ID）です。DCS への各 /event 呼び出しでは、応答の改善および高速化に関するサポートへの問い合わせで参照できる tid を受け取ります。 |
| `ttl` | Cookie の有効期間（日単位）です。 |
| `u` および `uuid` | Audience Manager によって割り当てられ一意のユーザー ID。これが必要になるのは、[サーバー間 DCS 呼び出し](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)をおこなう場合です。 |
| `y` | 宛先のタイプ。iFrame（`iframe`）または画像（`img`）。 |

>[!MORELIKETHIS]
>
>* [DCS でサポートされるキーと値のプレフィックスおよび変数](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

