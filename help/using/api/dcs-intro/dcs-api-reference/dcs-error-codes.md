---
description: データ収集サーバー（DCS）で生成されるエラーコードおよびメッセージをコード ID 順に説明します。
title: DCS エラーコード、メッセージ、例
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
TQID: https://experienceleague.adobe.com/FHc7VAvl6LcI-xtrxdg-eMRHMncTPHpxGxIx0sXOb-E
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 1519
ht-degree: 75%

---

# DCS エラーコード、メッセージ、例 {#dcs-error-codes-messages-and-examples}

[!UICONTROL Data Collection Servers]（[!DNL DCS]）で生成されるエラーコードおよびメッセージをコード ID 順に説明します。

以下の表で、*斜体*&#x200B;の部分には実際の情報が入ります。

## システムエラーコード {#system-error-codes}

| エラーコード | エラーメッセージ | 説明 |
|---|---|---|
| 0 | Unspecified error | これは、他のエラーハンドラーでカバーされないイベントを処理する包括的なエラーです。このエラーのトラブルシューティングは困難です。種々の不明なアクションやイベントが原因になっている可能性があります。このエラーが発生した場合は、[!DNL DCS] 要求をもう一度試してください。問題が解決しない場合は、[!DNL Adobe] 担当者にお問い合わせください。 |
| 1 | ホスト名の構成が見つかりませんでした：`hostname` | 送信された要求に含まれているホスト名が、アドビのパートナープロビジョニングチームでセットアップされていません。このエラーメッセージが表示された場合は、[!DNL Adobe] 担当者にご連絡ください。 |
| 2 | Invalid `d_orgid` value (could not find a config for this org id): `ID` | 組織 ID が正しくありません。ID を確認して、要求をもう一度試してください。組織 ID が不明な場合は、組織 ID の見つけ方について、[組織とアカウントのリンク](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=ja)の「管理ページ」を参照してください。 |
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
   <td colname="col2"> <p>ID <code><i>ID</i></code>のオプトアウトタグが検出されました </p> </td> 
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
   <td colname="col2"> <p> ID <code><i>ID</i></code>のプロファイル キャッシュから特性を読み取れません </p> </td> 
   <td colname="col3"> <p>アドビの社内ストレージからユーザープロファイルを読み取れない場合に返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> 顧客ID <code><i>ID</i></code>のプロファイル キャッシュからデバイス IDを読み取れません </p> </td> 
   <td colname="col3"> <p><a href="../../../reference/ids-in-aam.md">デバイス ID</a> をプロファイルリンク結合ルールのために取得できない場合に返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>デバイス ID <code><i>ID</i></code>の関連する顧客を読み取れません </p> </td> 
   <td colname="col3"> <p>デバイス ID に関連付けられている<a href="../../../reference/ids-in-aam.md">顧客 ID（UUID）</a>を、前回の認証済みプロファイル結合ルールのためにアドビの社内ストレージから取得できない場合に返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> ID <code><i>ID</i></code>のデバイスクラスターを読み取れません </p> </td> 
   <td colname="col3"> <p>このデバイス ID にリンクされているデバイス ID を同じデバイスグラフクラスターから返せません。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Could not perform migration since profile read failed for primary device </p> </td> 
   <td colname="col3"> <p>このエラーが報告された場合は、アドビのデータストア（<span class="wintitle">PCS</span>）にスケーラビリティの問題が発生している可能性があります。問題が解決しない場合は、アドビの担当者にお問い合わせください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p><code><i>ID</i></code>のプロファイル読み取りに失敗したため、<code><i>ID</i></code>から<code><i>ID</i></code>への移行を実行できませんでした </p> </td>
   <td colname="col3"> <p>このエラーが報告された場合は、アドビのデータストア（<span class="wintitle">PCS</span>）にスケーラビリティの問題が発生している可能性があります。問題が解決しない場合は、アドビの担当者にお問い合わせください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 統合警告コード {#integration-warning-codes}

| コード ID | メッセージ | 説明 |
| --- | --- | --- |
| 300 | 無効な顧客ID `_ID_` | 顧客 ID が無効です（データソースの値がない、統合コードがない、データソースの形式が無効、顧客 ID がブロックされている、顧客 ID が未指定、パートナーの管理下にないデータソースに不正にアクセスしようとしている、など）。 |
| 301 | Maximum number of customer ids exceeded.許可される最大値は`_maximum allowed_`です。 Found is `_maximum found_`. | クロスデバイス対応データソースに関連付けられている顧客 ID の数が、要求あたりのクロスデバイス ID 数の上限を超えています。このような ID にはクロスデバイス ID、モバイル ID、Cookie ID などがあります。上限は現在 10 に設定されています。 |
| 302 | 未認証の顧客ID `_ID_` | 顧客 ID データソースが現在の組織 ID に所有されていない場合に返されます。組織IDがわからない場合や、組織IDがない場合は、[組織とアカウントリンク ](https://experiencecloud.adobe.com/resources/help/ja_JP/mcloud/organizations.html)の「組織IDの検索」の節で、その検索方法について説明しています。 |
| 303 | ブロックされた顧客ID `_ID_` | 顧客 ID が悪意のある ID と見なされてブロックリストに追加されている場合に返されます。 |
| 304 | ブロックされたデータソース ID `_ID_` | データソース ID が悪意のある ID と見なされてブロックリストに追加されている場合に返されます |
| 306 | ブロックされた宣言済みデバイス ID `_ID_` | デバイス IDが悪意のあるものと認識され、デバイス IDがデバイス IDに追加されました。この問題は、このデバイス IDを含むDCS リクエストを短時間で大量に受け取った場合に発生する可能性があります。 |
| 307 | `_ID_`のプロファイル操作をブロックしました | ID が悪意のあるIDと見なされてブロックに加えられたため、読み取り/書き込み操作がブロックされました。エラーコード 306 を参照してください。 |
| 309 | 顧客ID `_ID_`は、リクエストごとに宣言された顧客IDの制限を超えたため破棄されました | エラー 301 に関係します。このエラーは、上限を超えたため破棄された顧客 ID を示します。<br><br>例えば、DCS呼び出しで宣言された顧客IDが12個ある場合、そのうちの2つは破棄されます。 どの ID が破棄されたかを伝えるために、このエラーは応答に 2 回表示されます（破棄された顧客 ID ごとに 1 回ずつ）。 |
| 310 | 指定された名前空間における制限を超えたため、顧客 ID は破棄されました。名前空間IDは`_ID_`、顧客IDは`_ID_`です。 | このエラーコードは、DCS呼び出しで同じ名前空間（`DPID`）に対して3つ以上の顧客IDが宣言されている場合に返されます。<br><br>`https://partner.demdex.net/event?d_rtbd=json&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one`<br><br>このサンプル DCS リクエストでは、同じ名前空間に対して4つのIDが宣言されています（統合コード 1を使用）。 これらの ID の 1 つが破棄され、エラー 310 が返されます。 |
| 311 | Request contains invalid parameters | DCS がこのエラーコードを返すのは、少なくとも 1 つの URL パラメーターが正しくエンコードされていない場合です。その場合、DCS は要求全体を無視します。<br><br>`http(s)://partner.demdex.net/event?d_event=imp&d_rtbd=json&d_src=38454&d_site=%esid!&d_creative=%ecid!&d_adgroup=%eaid!&d_placement=%epid!&d_campaign=%ebuy!&d_adsrc=48123`<br><br>上記のサンプルリクエストでは、`%` シーケンスが正しくエンコードされていません。 その結果、DCS はこの要求を無視します。<br><br>正しくエンコードされたサンプルは次のようになります：<br><br>`http(s)://partner.demdex.net/event?d_event=imp&d_rtbd=json&d_src=38454&d_site=%25esid!&d_creative=%25ecid!&d_adgroup=%25eaid!&d_placement=%25epid!&d_campaign=%25ebuy!&d_adsrc=48123` |
| 312 | Request contains an invalid Global Device ID | DCSは、リクエストに無効なグローバルデバイス IDが含まれている場合、このエラーコードを返します。 DCS は無効な ID を無視し、この無効な ID に関するエラーとあわせて 312 エラーをスローします。適切なデバイス広告 ID の形式および対応するグローバルデータソースについて詳しくは、[グローバルデータソース](../../../features/global-data-sources.md)および [Audience Manager の ID のインデックス](../../../reference/ids-in-aam.md)を参照してください。<br><br>誤った呼び出しの例：`"http://partner.demdex.net/event?d_rtbd=json&d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"`<br><br>説明：IDFA （DPID 20915）は大文字のIDである必要があります。 例の要求では ID を小文字で指定しています。 |
| 313 | CMP ID is not present in GCL | `gdpr=1` および IAB TC 文字列が CMP ID によって生成され、評価時点においてその CMP ID が、Audience Manager のグローバル CMP リストのキャッシュバージョンに存在しない場合、IAB TCF 用 Audience Manager プラグインは IAB TC 文字列を破棄し、通常どおりリクエストを処理します。IAB TCF v2.2 ${GDPR} マクロは0に設定され、${GDPR\_CONSENT\_XXX} マクロは空です。 |
| 314 | CMP ID is marked as deleted in GCL | `gdpr=1`とIAB TC文字列が、キャッシュされたバージョンのグローバル CMP リストで削除とマークされたCMPによって生成された場合、IAB TCF用のAudience Manager プラグインは、TC文字列を破棄し、グローバル CMP リストからの削除時間を超えている場合、通常どおりリクエストを処理します。 IAB TCF v2.2 ${GDPR} マクロは0に設定され、${GDPR\_CONSENT\_XXX} マクロは空です。 |
| 315 | Consent string indicates no consent | 同意が提供されない場合、IAB TCF の Audience Manager プラグインは、それ以上のデータ収集からユーザーをオプトアウトするか、パートナーコンテキストが検出されない場合は呼び出しを完全にドロップします。 |

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
