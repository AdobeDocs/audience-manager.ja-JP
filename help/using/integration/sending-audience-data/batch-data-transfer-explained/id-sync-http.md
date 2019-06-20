---
description: ベンダーと Audience Manager の間でユーザー ID を同期するために、最初の HTTP 呼び出しで使用される構文およびパラメーターについて説明します。ID 同期は、データ分類を Audience Manager に送信した後で開始できます。
seo-description: ベンダーと Audience Manager の間でユーザー ID を同期するために、最初の HTTP 呼び出しで使用される構文およびパラメーターについて説明します。ID 同期は、データ分類を Audience Manager に送信した後で開始できます。
seo-title: 受信データ転送のための ID 同期
solution: Audience Manager
title: 受信データ転送のための ID 同期
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
translation-type: tm+mt
source-git-commit: 0fac081c93be36d2aa40023c7323ef1886b3860a

---


# 受信データ転送のための ID 同期{#id-synchronization-for-inbound-data-transfers}

ベンダーと Audience Manager の間でユーザー ID を同期するために、最初の `HTTP` 呼び出しで使用される構文およびパラメーターについて説明します。ID 同期は、データ分類を Audience Manager に送信した後で開始できます。

<!-- c_id_sync_in.xml -->

ID 同期は、受信の非同期データ転送プロセスの最初のステップです。このステップでは、Audience Manager およびベンダーは、各自のサイトベンダーの ID を比較およびマッチングします。例えば、ある [!DNL Audience Manager] のお客様は、ID 123 でユーザーを把握します。しかし、データパートナーは、このユーザーを ID 456 で識別します。この同期プロセスにより、[!DNL Audience Manager] およびデータベンダーは、これらの様々な ID を照合し、各自のシステムでユーザーを識別できます。完了したら、[!DNL Audience Manager] およびサードパーティパートナーは、個別ユーザーごとに対応する ID をアドビのネットワーク上で確認できます。

以下の方法を使用してデータを [!DNL Audience Manager] に取得できます。

* [ID 同期 HTTP リクエスト](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [宣言済み ID イベント](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [電子メール埋め込み画像からの ID 同期](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID 同期 `HTTP` リクエスト {#id-sync-http}

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

The [!DNL URL] for your inbound ID synchronization call should contain variables described in the table below.

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
   <td colname="col2"> <p>エンコードされた URL は、マクロ <code>${DD_UUID}</code> が埋め込まれてリダイレクトされます。 </p> <p>注意：コンテンツプロバイダーが呼び出しを開始した場合にのみ追加されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>dgpr=&lt;0|1&gt;</i></code> </td> 
   <td colname="col2"> <p>オプションです。Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code> dgpr</code> は、0（GGPRが適用されません）または1（GGPR適用）です。 </p> <p> <b>注意:</b> このパラメーターはgdpr_ acceptと <code>一緒にのみ使用</code>できます。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>dgpr_ accept=&lt;エンコードされたSTRING&gt;</i></code> </td> 
   <td colname="col2"> <p>オプションです。Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code>ddpr_ accept</code> は、URLセーフベースの64エンコードGGPRの同意文字列です（ <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB仕様</a>を参照）。 </p> <p> <b>注意:</b> このパラメーターは <code>gdpr</code>と一緒にのみ使用できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 宣言済み ID イベント {#declared-id-event}

詳しくは、[宣言済み ID](../../../features/declared-ids.md) を参照してください。

## 電子メール埋め込み画像からの ID 同期 {#id-sync-email-image}

電子メール画像で ID をマッチングさせるための形式は、前述のものと同じです。ただし、電子メールのその画像は、これが機能するように有効になっている必要があります。これは、ほとんどのメールシステムは、デフォルトで画像を無効にしているので、電子メールを使用した ID 同期に影響します。

>[!MORE_LIKE_THIS]
>
>* [データ収集コンポーネント](../../../reference/system-components/components-data-collection.md)

