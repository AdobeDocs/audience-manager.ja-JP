---
description: Audience Manager とサードパーティデータプロバイダーの間でユーザー ID を同期するために、最初の HTTP 呼び出しで使用される構文およびパラメーターについて説明します。最初の ID 同期を試す前に、担当の Adobe Audience Manager コンサルタントにお問い合わせください。
seo-description: Audience Manager とサードパーティデータプロバイダーの間でユーザー ID を同期するために、最初の HTTP 呼び出しで使用される構文およびパラメーターについて説明します。最初の ID 同期を試す前に、担当の Adobe Audience Manager コンサルタントにお問い合わせください。
seo-title: 送信データ転送のための ID 同期
solution: Audience Manager
title: 送信データ転送のための ID 同期
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: 送信データ転送
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 99%

---

# 送信データ転送のための ID 同期 {#id-synchronization-for-outbound-data-transfers}

Audience Manager とサードパーティデータプロバイダーの間でユーザー ID を同期するために、最初の `HTTP` 呼び出しで使用される構文およびパラメーターについて説明します。最初の ID 同期を試す前に、担当の Adobe Audience Manager コンサルタントにお問い合わせください。

<!-- c_id_sync_out.xml -->

## ID 同期の目的

ID 同期は、送信の非同期データ転送プロセスの最初のステップです。このステップでは、[!DNL Audience Manager] およびベンダーは、各自のサイトベンダーの ID を比較およびマッチングします。例えば、ある [!DNL Audience Manager] のお客様は、ID 123 でユーザーを把握します。しかし、データパートナーは、このユーザーを ID 456 で識別します。この同期プロセスにより、[!DNL Audience Manager] およびデータベンダーは、これらの様々な ID を照合し、各自のシステムでユーザーを識別できます。完了したら、[!DNL Audience Manager] およびサードパーティデータプロバイダーは、ユニークユーザーごとに対応する ID をアドビのネットワーク上で確認できます。

## URL 構文

ID 交換では、適切な形式の [!DNL URL] 文字列は次のようになります。

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL パラメーター

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
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">データプロバイダーの一意の ID（<span class="keyword">Audience Manager</span> によって割り当てられる）。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> 一意のユーザー ID。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">エンコードされた URL は、マクロ <code> ${DD_UUID}</code> が埋め込まれてリダイレクトされます。 <p><b>注意：</b>データプロバイダーが呼び出しを開始した場合にのみ追加されます。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code>  には、0（GDPR 適用対象外）または 1（GDPR 適用対象）を使用できます。</p><p><b>注意：</b> <ul><li><code>gdpr</code> および <code>gdpr_consent</code> パラメーターは、アクティベートパートナーと共に ID 同期 URLで徐々にロールアウトされます。<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">IAB TCF の Audience Manager プラグイン</a>で、IAB TCF をサポートするアクティベーションパートナーを参照してください。</li><li>このパラメーターは、 と一緒に使用する必要があります <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code>  は、URL で使用できる base64 でエンコードされた GDPR コンセントストリングです（<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB の仕様</a>を参照）。</p><p><b>注意：</b>このパラメーターは、常に <code>gdpr</code> と一緒に使用する必要があります。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [データ収集サーバー（DCS）API メソッドおよびコード](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
* [データ収集コンポーネント](../../reference/system-components/components-data-collection.md)

