---
description: Audience Manager とサードパーティデータプロバイダーの間でユーザー ID を同期するために、最初の HTTP 呼び出しで使用される構文およびパラメーターについて説明します。最初の ID 同期を試す前に、担当の Adobe Audience Manager コンサルタントにお問い合わせください。
seo-description: Audience Manager とサードパーティデータプロバイダーの間でユーザー ID を同期するために、最初の HTTP 呼び出しで使用される構文およびパラメーターについて説明します。最初の ID 同期を試す前に、担当の Adobe Audience Manager コンサルタントにお問い合わせください。
seo-title: 送信データ転送のための ID 同期
solution: Audience Manager
title: 送信データ転送のための ID 同期
uuid: f3849be8-1094-47db-9296-7482f020af18
translation-type: tm+mt
source-git-commit: e206d3a3cba259dc215f2f4190c9b4e03264f080

---


# 送信データ転送のための ID 同期{#id-synchronization-for-outbound-data-transfers}

Audience Manager とサードパーティデータプロバイダーの間でユーザー ID を同期するために、最初の `HTTP` 呼び出しで使用される構文およびパラメーターについて説明します。最初の ID 同期を試す前に、担当の Adobe Audience Manager コンサルタントにお問い合わせください。

<!-- c_id_sync_out.xml -->

## ID 同期の目的

ID 同期は、送信の非同期データ転送プロセスの最初のステップです。このステップでは、[!DNL Audience Manager] およびベンダーは、各自のサイトベンダーの ID を比較およびマッチングします。例えば、ある [!DNL Audience Manager] のお客様は、ID 123 でユーザーを把握します。しかし、データパートナーは、このユーザーを ID 456 で識別します。この同期プロセスにより、[!DNL Audience Manager] およびデータベンダーは、これらの様々な ID を照合し、各自のシステムでユーザーを識別できます。完了したら、[!DNL Audience Manager] およびサードパーティデータプロバイダーは、個別ユーザーごとに対応する ID をアドビのネットワーク上で確認できます。

## URL 構文

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL パラメーター

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
   <td colname="col2">エンコードされた URL は、マクロ <code>${DD_UUID}</code> が埋め込まれてリダイレクトされます。 <p><b>注意：</b>データプロバイダーが呼び出しを開始した場合にのみ追加されます。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code><i>dgpr=&lt;0|1&gt;</i></code> </td> 
   <td colname="col2"> <p><code>dgpr</code> は、0（GGPRが適用されません）または1（GGPR適用）です。</p><p><b>注釈:</b> <ul><li><code>dgpr</code> および <code>dgpr_ accept</code> パラメーターは、アクティベートパートナーと共に徐々にID同期URLでロールアウトされます。See Activation partners that support IAB TCF in <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in for IAB TCF.</a></li><li>This parameter can only be used together with <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>dgpr_ accept=&lt;エンコードされたSTRING&gt;</i></code> </td> 
   <td colname="col2"><p><code>ddpr_ accept</code> は、URLセーフベースの64エンコードGGPRの同意文字列です（ <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB仕様</a>を参照）。</p><p><b>注意:</b> このパラメーターは <code>gdpr</code>と一緒にのみ使用できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [データ収集サーバー（DCS）API メソッドおよびコード](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [データ収集コンポーネント](../../reference/system-components/components-data-collection.md)

