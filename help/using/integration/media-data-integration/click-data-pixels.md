---
description: 'null'
seo-description: 'null'
seo-title: ピクセル呼び出しを使用したキャンペーンのクリックデータのキャプチャ
solution: Audience Manager
title: ピクセル呼び出しを使用したキャンペーンのクリックデータのキャプチャ
uuid: 7c3797f7-9674-493d-972b-38be0584fede
translation-type: ht
source-git-commit: b1e438a77a472c192117a2c1ddcf63f4eb25d07d

---


# ピクセル呼び出しを使用したキャンペーンのクリックデータのキャプチャ {#capturing-campaign-click-data-via-pixel-calls}

クリック追跡によって、サードパーティクリエイティブのクリックベースのアクティビティが記録されるので、キャンペーン全体を通して訪問者のエンゲージメントを測定することができます。インプレッションの収集と同様に、イベント呼び出しが Audience Manager のデータ収集サーバー（[!UICONTROL DCS]）に送信されて処理されます。訪問者はその後、意図した Web アドレスにリダイレクトされます。

## 要件

クリック追跡呼び出しには次のパラメーターが必要です。

* `d_event=click`：イベント呼び出しをクリックイベントとして識別するキーと値のペア。
* `d_rd=redirect URL`：エンコードされたリダイレクト [!DNL URL] が含まれているキーと値のペア。

さらに、呼び出しには、特性認定や他のレポートへのデータやメタデータの提供に使用できるキーと値のペアを含めることもできます｡

## 要求のサンプル

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 応答

応答は、`d_rd` パラメーターで指定された [!DNL URL] にブラウザーをリダイレクトします。応答文字列には、サポートされている下記マクロのいずれかで生成された値を含めることができます。

上記の例に従うと、ブラウザーは次の [!DNL URL] にリダイレクトされます。

[!DNL `https://adobe.com/callback?creative=123`]

## サポートされているマクロ

クリックイベントでは、次の表に示したマクロをサポートしています。マクロは、キャンペーンやユーザー追跡用の広告タグが読み込まれるときに起動される小さい自己完結型コード単位です。マクロは、`%macro%` の形式でマークされている限り、宛先 [!DNL URL] と一緒に渡されます。一部のキーにはマクロがなく、代わりに、ハードコードされた ID 値を受け取ります。[オーディエンスの最適化レポート](../../reporting/audience-optimization-reports/audience-optimization-reports.md)でデータを分析する場合はハードコードされた値を受け取るキーが必要になります。

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> キー </th> 
   <th colname="col02" class="entry"> マクロ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>広告サーバーから割り当てられた広告グループ ID（数値）。 </p> <p>オプションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>マクロなし。 </p> <p>ハードコードされた ID 値を受け取ります。 </p> </td> 
   <td colname="col2"> <p>広告主 ID。</p> <p>広告主のデータソースの統合コード。Audience Manager のデータソースとは関係ありません。</p> <p> <span class="wintitle">Audience Optimization</span> レポートの場合は必須。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>事業部門の ID（数値）。 </p> <p> <span class="wintitle">Audience Optimization </span> レポートの場合は必須。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>広告サーバーから割り当てられたキャンペーン ID（数値）。 </p> <p> <span class="wintitle">Audience Optimization </span> レポートの場合は必須。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>広告サーバーから割り当てられたクリエイティブ ID（数値）。 </p> <p>必須。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>データプロバイダー ID。 </p> <p>データプロバイダー ID をユーザー ID にリンクするために <code> d_dpuuid</code> と一緒に使用することが多い。 </p> <p>オプションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>データプロバイダーから提供される一意のユーザー ID。 </p> <p>ユーザー ID をデータプロバイダー ID にリンクするために <code> d_dpid</code> と一緒に使用することが多い。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID</span> (ECID)ECID について詳しくは、<a href="https://marketing.adobe.com/resources/help/ja_JP/mcvid/mcvid_cookies.html" format="https" scope="external">Cookie と Experience Cloud ID</a> を参照してください。 </p> <p>オプションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>広告サーバーから割り当てられたプレースメント ID（数値）。 </p> <p>オプションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>要求に対してサービスを提供する DCS クラスターの地域 ID（数値）。DCS について詳しくは、<a href="../../reference/system-components/components-data-collection.md"> データ収集コンポーネント</a>を参照してください。 </p> <p>オプションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>キャッシュバスティングに使用される乱数。 </p> <p>オプションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>広告サーバーから割り当てられたサイト ID（数値）。 </p> <p>オプションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>Audience Manager が取り込むメタデータのソースの DPID。 </p> <p>必須。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Demdex Cookie に頼らずに、訪問者の ID を URL で直接指定します。 </p> <p>オプションです。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_applies%</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF 用の Audience Manager プラグイン</a>に関連しています。 </p><p><code>gdpr</code> には、0（GDPR 適用対象外）または 1（GDPR 適用対象）を使用できます。</p> <p>デフォルト値は 0 です。</p><p>オプションです。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_consent%</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF 用の Audience Manager プラグイン</a>に関連しています。</p><p> <code>gdpr=1</code> の場合、<code>%gdpr_consent%</code> は <code>gdpr_consent</code> 文字列に置き換えられます（<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB 仕様</a>を参照）。</p> <p>デフォルト値は 0 です。</p><p>オプションです。</p></td> 
  </tr> 
 </tbody> 
</table>

## マクロの例

これは、クリエイティブ、広告グループ、プレースメントの各マクロの受け渡しの例です。ここでは、各パラメーターの値がクリック追跡呼び出しの非リダイレクト部分に渡されると仮定しています。

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## リクエスト

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## 応答

上記の例に従うと、ブラウザーは次の [!DNL URL] にリダイレクトされます。

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORELIKETHIS]
>
>* [Audience Optimization レポートのデータおよびメタデータファイル](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

