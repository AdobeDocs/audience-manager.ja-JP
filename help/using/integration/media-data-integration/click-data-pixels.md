---
description: クリック追跡によって、サードパーティクリエイティブのクリックベースのアクティビティが記録されるので、キャンペーン全体を通して訪問者のエンゲージメントを測定することができます。
seo-description: クリック追跡によって、サードパーティクリエイティブのクリックベースのアクティビティが記録されるので、キャンペーン全体を通して訪問者のエンゲージメントを測定することができます。
seo-title: ピクセル呼び出しを使用したキャンペーンのクリックデータのキャプチャ
solution: Audience Manager
title: ピクセル呼び出しを使用したキャンペーンのクリックデータのキャプチャ
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Integration with Campaign
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 100%

---


# ピクセル呼び出しを使用したキャンペーンのクリックデータのキャプチャ {#capturing-campaign-click-data-via-pixel-calls}

クリック追跡によって、サードパーティクリエイティブのクリックベースのアクティビティが記録されるので、キャンペーン全体を通して訪問者のエンゲージメントを測定することができます。[インプレッションの収集](/help/using/integration/media-data-integration/impression-data-pixels.md)と同様に、イベント呼び出しを処理するため、 の[!DNL Audience Manager]データ収集サーバー（[!DNL DCS]）に送信されます。訪問者はその後、意図した Web アドレスにリダイレクトされます。

>[!NOTE]
>
>クライアントドメイン専用の正確な [!DNL URL] については、[!DNL Audience Manager] コンサルタントまたはアカウントリードにお問い合わせください。

## 要件

クリック追跡呼び出しには次のパラメーターが必要です。

* `d_event=click`：イベント呼び出しをクリックイベントとして識別するキーと値のペア。
* `d_rd=redirect URL`：二重エンコードされたリダイレクト [!DNL URL] が含まれているキーと値のペア。オンラインエンコーディングツールを使用している場合、リダイレクトが機能するように、エンコーダーを使用して文字列を実行してから、結果を再びエンコードします。

さらに、呼び出しには、特性認定や他のレポートへのデータやメタデータの提供に使用できるキーと値のペアを含めることもできます｡

## 要求のサンプル

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 応答

応答は、`d_rd` パラメーターで指定された [!DNL URL] にブラウザーをリダイレクトします。応答文字列には、サポートされている下記マクロのいずれかで生成された値を含めることができます。

上記の例に従うと、ブラウザーは次の [!DNL URL] にリダイレクトされます。

`https://adobe.com/callback?creative=123`

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
   <td colname="col2"> <p>事業部門の ID（数値）。 </p> <p> <span class="wintitle">Audience Optimization</span> レポートの場合は必須。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>広告サーバーから割り当てられたキャンペーン ID（数値）。 </p> <p> <span class="wintitle">Audience Optimization</span> レポートの場合は必須。 </p> </td> 
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
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID</span> (ECID)ECID について詳しくは、<a href="https://docs.adobe.com/content/help/ja-JP/id-service/using/intro/cookies.html" format="https" scope="external">Cookie と Experience Cloud ID</a> を参照してください。 </p> <p>オプションです。 </p> </td> 
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
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF 用の Audience Manager プラグイン</a>に関連しています。 </p><p><code>gdpr</code>  には、0（GDPR 適用対象外）または 1（GDPR 適用対象）を使用できます。</p> <p>デフォルト値は 0 です。</p><p>オプションです。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF 用の Audience Manager プラグイン</a>に関連しています。</p><p> <code>gdpr=1</code> の場合、<code>${gdpr_consent_XXXX}</code> は <code>gdpr_consent</code> 文字列とベンダー ID に置き換えられます（<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external">IAB 仕様</a>を参照）。</p> <p>デフォルト値は 0 です。</p><p>オプションです。</p></td> 
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
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## 応答

上記の例に従うと、ブラウザーは次の [!DNL URL] にリダイレクトされます。

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## 追加機能 - [!UICONTROL Audience Optimization Reports]

ピクセル呼び出しを使用して、[Audience Optimization](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md) レポートを強化できます。ピクセルを使用してレポートに出力する場合は、[メタデータファイルの概要とマッピング](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)を参照してください。


>[!MORELIKETHIS]
>
>* [Audience Optimization レポートのデータおよびメタデータファイル](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

