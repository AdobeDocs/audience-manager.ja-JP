---
description: ベンダーと Audience Manager の間でユーザー ID を同期するために、最初の HTTP 呼び出しで使用される構文およびパラメーターについて説明します。ID 同期は、データ分類を Audience Manager に送信した後で開始できます。
seo-description: ベンダーと Audience Manager の間でユーザー ID を同期するために、最初の HTTP 呼び出しで使用される構文およびパラメーターについて説明します。ID 同期は、データ分類を Audience Manager に送信した後で開始できます。
seo-title: 受信データ転送のための ID 同期
solution: Audience Manager
title: 受信データ転送のための ID 同期
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: 受信データ転送
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 100%

---

# 受信データ転送のための ID 同期 {#id-synchronization-for-inbound-data-transfers}

ベンダーと [!DNL Audience Manager] の間でユーザー ID を同期するために、最初の `HTTP` 呼び出しで使用される構文およびパラメーターについて説明します。ID 同期は、データ分類を [!DNL Audience Manager] に送信した後で開始できます。

ID 同期は、受信の非同期データ転送プロセスの最初のステップです。このステップでは、[!DNL Audience Manager] およびベンダーは、各自のサイトベンダーの ID を比較およびマッチングします。例えば、ある [!DNL Audience Manager] のお客様は、ID 123 でユーザーを把握します。しかし、データパートナーは、このユーザーを ID 456 で識別します。この同期プロセスにより、[!DNL Audience Manager] およびデータベンダーは、これらの様々な ID を照合し、各自のシステムでユーザーを識別できます。完了したら、[!DNL Audience Manager] およびサードパーティパートナーは、ユニークユーザーごとに対応する ID をアドビのネットワーク上で確認できます。

以下の方法を使用してデータを [!DNL Audience Manager] に取得できます。

* [ID 同期 HTTP リクエスト](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [宣言された ID イベント](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [電子メール埋め込み画像からの ID 同期](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID 同期 `HTTP` リクエスト {#id-sync-http}

ID 交換では、適切な形式の [!DNL URL] 文字列は次のようになります。

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

受信 ID 同期呼び出しの [!DNL URL] には、以下の表で説明する変数が含まれている必要があります。

>[!NOTE]
>
>斜体のコンテンツを実際のパラメーター値に置き換えてください。

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>コンテンツプロバイダーの一意の ID（<span class="keyword">Audience Manager</span> によって割り当てられる）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>一意のユーザー ID の URL（パーセント）エンコード表現。エンコード予約済み ASCII 文字に加えて、任意の非 ASCII 文字も、UTF-8 文字エンコード表に基づいてパーセントエンコードされる必要があります。 </p> <p>詳しくは、<a href="https://www.url-encode-decode.com" format="http" scope="external">URL Encode/Decode Online</a> Web サイトを参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>エンコードされた URL は、マクロ <code> ${DD_UUID}</code> が埋め込まれてリダイレクトされます。 </p> <p>注意：コンテンツプロバイダーが呼び出しを開始した場合にのみ追加されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>オプションです。<a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF用 Audience Manager プラグイン</a>を使用している場合は、このパラメーターを追加します。</p> <p><code> gdpr</code>  には、0（GDPR 適用対象外）または 1（GDPR 適用対象）を使用できます。 </p> <p> <b>注意：</b>このパラメーターは、常に <code>gdpr_consent</code> と一緒に使用する必要があります。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>オプションです。<a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF用 Audience Manager プラグイン</a>を使用している場合は、このパラメーターを追加します。</p> <p><code>gdpr_consent</code>  は、URL で使用できる base64 でエンコードされた GDPR コンセントストリングです（<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB の仕様</a>を参照）。 </p> <p> <b>注意：</b>このパラメーターは、常に <code>gdpr</code> と一緒に使用する必要があります。</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] イベント {#declared-id-event}

詳しくは、[宣言された ID](../../../features/declared-ids.md) を参照してください。

## 電子メール埋め込み画像からの ID 同期 {#id-sync-email-image}

電子メール画像で ID をマッチングさせるための形式は、前述のものと同じです。ただし、電子メールのその画像は、これが機能するように有効になっている必要があります。これは、ほとんどのメールシステムは、デフォルトで画像を無効にしているので、電子メールを使用した ID 同期に影響します。

>[!MORELIKETHIS]
>
>* [データ収集コンポーネント](../../../reference/system-components/components-data-collection.md)

