---
description: データ収集サーバー（DCS）で生成されるエラーコードおよびメッセージをコード ID の順に説明します。
seo-description: データ収集サーバー（DCS）で生成されるエラーコードおよびメッセージをコード ID の順に説明します。
seo-title: DCS エラーコード、メッセージ、例
solution: Audience Manager
title: DCS エラーコード、メッセージ、例
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 38c4c46709491656071f4a958e9f0de26d42dd74
workflow-type: ht
source-wordcount: '1547'
ht-degree: 100%

---

# DCS エラーコード、メッセージ、例 {#dcs-error-codes-messages-and-examples}

[!UICONTROL Data Collection Servers]（[!DNL DCS]）で生成されるエラーコードおよびメッセージをコード ID 順に説明します。

以下の表で、*斜体*&#x200B;の部分には実際の情報が入ります。

## システムエラーコード {#system-error-codes}

| エラーコード | エラーメッセージ | 説明 |
|---|---|---|
| 0 | Unspecified error | これは、他のエラーハンドラーでカバーされないイベントを処理する包括的なエラーです。このエラーのトラブルシューティングは困難です。種々の不明なアクションやイベントが原因になっている可能性があります。このエラーが発生した場合は、[!DNL DCS] 要求をもう一度試してください。問題が解決しない場合は、[!DNL Adobe] 担当者にお問い合わせください。 |
| 1 | Could not find config for hostname:     `hostname` | 送信された要求に含まれているホスト名が、アドビのパートナープロビジョニングチームでセットアップされていません。このエラーメッセージが表示された場合は、[!DNL Adobe] 担当者にご連絡ください。 |
| 2 | Invalid `d_orgid` value (could not find a config for this org id): `ID` | 組織 ID が正しくありません。ID を確認して、要求をもう一度試してください。組織 ID が不明な場合は、組織 ID の見つけ方について、[組織とアカウントのリンク](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/organizations.html)の「管理ページ」を参照してください。 |
| 10 | 特性を評価できません | リクエスト上の特性は、部分的に評価されたか、まったく評価されていません。 問題が解決しない場合は、[!DNL Adobe] 担当者にお問い合わせください。 |

## 統合エラーコード {#integration-error-codes}

| エラーコード | エラーメッセージ | 説明 |
|---|---|---|
| 100 | Could not retrieve host name for the request | [!DNL API] 呼び出しで送信された要求にホスト ヘッダーが含まれていませんでした。[!DNL HTTP]ホストヘッダーを呼び出しに追加して、もう一度試してください。なお、ほとんどのブラウザーおよび [!DNL API] クライアントでは、これを自動的におこないます。 |
| 101 | Invalid [!DNL Experience Cloud] id passed in `ID` | [!DNL DCS] 呼び出しに無効な [!DNL Experience Cloud] ID が含まれています。ヘッダー文字列の `d_mid=` キー値ペアを確認してください。正しい [!DNL Experience Cloud] ID を渡していることを確認して、要求をもう一度試してください。 |
| 102 | Invalid [!DNL AAM ID] passed in request `ID` | [!DNL DCS] 呼び出しに無効な [!DNL Audience Manager] ID が含まれています。ヘッダー文字列の `d_uuid=` キー値ペアを確認してください。正しい [!DNL Audience Manager] ID を渡していることを確認して、要求をもう一度試してください。 |
| 104 | All customer IDs are invalid | 呼び出しに含まれているすべての顧客 ID が無効です。ID を確認して、もう一度試してください。 |
| 109 | リファラー `HTTP referer` はパートナーの `Partner ID` で使用できます。 | 呼び出しの `HTTP referer` ヘッダーは、呼び出しのパートナー ID では使用できません。`HTTP referer` ヘッダーが正しいことを確認します。 |
| 111 | Invalid `IMS` token received | [!DNL Audience Manager] - [!DNL Adobe Target] 統合に対して返されます。エラーがスローされるのは、無効な [!DNL IMS] トークンを含んだ呼び出しが [!DNL DCS] に対しておこなわれた場合です。トークンの形式が正しくないか有効期限が切れている、または要求したリソースにアクセスする権限をユーザーが持っていない可能性があります。 |

## オプトアウトエラーコード {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> コード ID </th> 
   <th colname="col2" class="entry"> メッセージ </th> 
   <th colname="col3" class="entry"> 説明 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>Encountered opt out tag for id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>お客様がインタレストベース広告の受信をオプトアウトしました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Blocked cookies </p> </td> 
   <td colname="col3"> <p>ユーザーのブラウザーがサードパーティ Cookie をブロックしている場合に返されます。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Encountered trust relationship via <a href="https://www.networkadvertising.org/" format="http" scope="external">NAI</a> </p> </td> 
   <td colname="col3"> <p>ユーザーが NAI を通じてオプトアウトプロセスを開始しました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Requests from this country are blocked by partner </p> </td> 
   <td colname="col3"> <p><span class="wintitle">DCS</span> では、パートナーがトラフィックを意図的に制限している国からの要求を IP アドレスに基づいてブロックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Requests from this country are not allowed </p> </td> 
   <td colname="col3"> <p><span class="wintitle">DCS</span> では、次の国からの要求を IP アドレスに基づいてブロックします。 </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">キューバ（CU） </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">イラン（IR） </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">北朝鮮（KP） </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">スーダン（SD） </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">シリア（SY） </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## プロファイル取得エラーコード {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> コード ID </th> 
   <th colname="col2" class="entry"> メッセージ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> Cannot read traits from profile cache for id:     <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>アドビの社内ストレージからユーザープロファイルを読み取れない場合に返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Cannot read device ids from profile cache for customer id:     <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p><a href="../../../reference/ids-in-aam.md">デバイス ID</a> をプロファイルリンク結合ルールのために取得できない場合に返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Cannot read related customer for device id:     <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>デバイス ID に関連付けられている<a href="../../../reference/ids-in-aam.md">顧客 ID（UUID）</a>を、前回の認証済みプロファイル結合ルールのためにアドビの社内ストレージから取得できない場合に返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Cannot read device cluster for id:     <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>このデバイス ID にリンクされているデバイス ID を同じデバイスグラフクラスターから返せません。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Could not perform migration since profile read failed for primary device </p> </td> 
   <td colname="col3"> <p>このエラーが報告された場合は、アドビのデータストア（<span class="wintitle">PCS</span>）にスケーラビリティの問題が発生している可能性があります。問題が解決しない場合は、アドビの担当者にお問い合わせください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Could not perform migration from<code><i>ID</i></code> to <code><i>ID</i></code>, because profile read failed for <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>このエラーが報告された場合は、アドビのデータストア（<span class="wintitle">PCS</span>）にスケーラビリティの問題が発生している可能性があります。問題が解決しない場合は、アドビの担当者にお問い合わせください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 統合警告コード {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> コード ID </th> 
   <th colname="col2" class="entry"> メッセージ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>Invalid customer id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>顧客 ID が無効です（データソースの値がない、統合コードがない、データソースの形式が無効、顧客 ID がブロックされている、顧客 ID が未指定、パートナーの管理下にないデータソースに不正にアクセスしようとしている、など）。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Maximum number of customer ids exceeded.Maximum allowed is<code><i>maximum allowed</i></code>. Found is <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>クロスデバイス対応データソースに関連付けられている顧客 ID の数が、要求あたりのクロスデバイス ID 数の上限を超えています。このような ID にはクロスデバイス ID、モバイル ID、Cookie ID などがあります。上限は現在 10 に設定されています。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>Unauthorized customer id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>顧客 ID データソースが現在の組織 ID に所有されていない場合に返されます。組織 ID が不明な場合は、組織 ID の見つけ方について、<a href="https://experiencecloud.adobe.com/resources/help/ja_JP/mcloud/organizations.html" format="https" scope="external">組織とアカウントのリンク</a>の「組織 ID を見つける」を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>Blocked customer id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>顧客 ID が悪意のある ID と見なされてブロックリストに追加されている場合に返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>Blocked datasource id  <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>データソース ID が悪意のある ID と見なされてブロックリストに追加されている場合に返されます </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Blocked declared device id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>デバイス ID が悪意のあるもの見なされ、ブロックリストに加えられました。この問題は、このデバイス ID を含む <span class="wintitle"> DCS</span> 要求を短期間で大量に受信した場合に発生する可能性があります。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Blocked profile operation for <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>ID が悪意のあるIDと見なされてブロックに加えられたため、読み取り/書き込み操作がブロックされました。エラーコード 306 を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>Customer id<code><i>ID</i></code> was discarded because it exceeded the limit of declared customer ids per request </p> </td> 
   <td colname="col3"> <p>エラー 301 に関係します。このエラーは、上限を超えたため破棄された顧客 ID を示します。 </p> <p>例えば、12 個の顧客 ID が <span class="wintitle">DCS</span> 呼び出しで宣言された場合は、そのうちの 2 個が破棄されます。どの ID が破棄されたかを伝えるために、このエラーは応答に 2 回表示されます（破棄された顧客 ID ごとに 1 回ずつ）。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>Customer id was discarded because it exceeded the limit for a given namespace.Namespace id is<code><i>ID</i></code>, customer id is <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>このエラーコードが返されるのは、1 回の <code> DPID</code>DCS<span class="wintitle"> 呼び出しで同じ名前空間（</span>）に 4 個以上の顧客 ID が宣言されている場合です。 </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>このサンプル <span class="wintitle">DCS</span> 要求では、同じ名前空間に（統合コード one で）4 個の ID が宣言されています。これらの ID の 1 つが破棄され、エラー 310 が返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>Request contains invalid parameters </p> </td> 
   <td colname="col3"> <p><span class="wintitle">DCS</span> がこのエラーコードを返すのは、少なくとも 1 つの URL パラメーターが正しくエンコードされていない場合です。その場合、<span class="wintitle">DCS</span> は要求全体を無視します。 </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>上記のサンプル要求では、<code> %</code> の列が誤ってエンコードされています。その結果、<span class="wintitle">DCS</span> はこの要求を無視します。 </p> <p>正しくエンコードされたサンプルは次のようになります。 </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>Request contains an invalid Global Device ID </p> </td> 
   <td colname="col3"> <p><span class="wintitle">DCS</span> がこのエラーコードを返すのは、要求に無効なグローバルデバイス ID が含まれている場合です。DCS は無効な ID を無視し、この無効な ID に関するエラーとあわせて 312 エラーをスローします。適切なデバイス広告 ID の形式および対応するグローバルデータソースについて詳しくは、<a href="../../../features/global-data-sources.md" format="dita" scope="local">グローバルデータソース</a>および <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Audience Manager の ID のインデックス</a>を参照してください。</p>
   <p>不正な呼び出しの例： <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>説明：<span class="keyword">IDFA（DPID 20915）</span>は大文字の ID である必要がありますが、例の要求では ID を小文字で指定しています。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>CMP ID is not present in GCL</p> </td> 
   <td colname="col3"> <p><code>gdpr=1</code> および IAB TC 文字列が CMP ID によって生成され、評価時点においてその CMP ID が、Audience Manager のグローバル CMP リストのキャッシュバージョンに存在しない場合、IAB TCF 用 Audience Manager プラグインは IAB TC 文字列を破棄し、通常どおりリクエストを処理します。IAB TCF v2.0 ${GDPR} マクロが 0 に設定され、${GDPR_CONSENT_XXX} マクロは空になります。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>CMP ID is marked as deleted in GCL</p> </td> 
   <td colname="col3"> <p><code>gdpr=1</code> および IAB TCF 文字列が CMP によって生成され、その CMP がグローバル CMP リストのキャッシュバージョンで削除とマークされている場合、評価時間がグローバル CMP リストの削除時間を経過すると、IAB TC 用 Audience Manager プラグインは TC 文字列を破棄し、通常どおりリクエストを処理します。IAB TCF v2.0 ${GDPR} マクロが 0 に設定され、${GDPR_CONSENT_XXX} マクロは空になります。</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>Consent string indicates no consent</p> </td> 
   <td colname="col3"> <p>同意が提供されない場合、IAB TCF の Audience Manager プラグインは、それ以上のデータ収集からユーザーをオプトアウトするか、パートナーコンテキストが検出されない場合は呼び出しを完全にドロップします。</p>
   </td>
  </tr>

</tbody>
</table>

## サンプルエラーコードメッセージ {#sample-error-codes}

[!DNL DCS] では、エラーコードおよびメッセージを HTTP 応答文字列の [!DNL JSON] オブジェクトまたは X ヘッダーで返します。

### サンプル DCS エラーコードおよびメッセージ

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### X-Error

X- ヘッダーで表現されたエラーコード（例えば `X-Error: 101,102` など）が URL 文字列に含まれます。

[競合状態とエラー処理](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
