---
description: 送信データファイルの名前に使用される必須フィールド、構文および規則について説明します。
seo-description: 送信データファイルの名前に使用される必須フィールド、構文および規則について説明します。
seo-title: 送信データファイル名：構文と例
solution: Audience Manager
title: 送信データファイル名：構文と例
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: 送信データ転送
exl-id: 0944da72-5a8d-45a2-951e-b2988eb3d490
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 99%

---

# 送信データファイル名：構文と例 {#outbound-data-file-name-syntax-and-examples}

送信データファイルの名前に使用される必須フィールド、構文および規則について説明します。

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>スタイル要件（`monospaced text`、*斜体*、括弧 `[ ]` `( )`、など）コード要素およびオプションを表します。詳しくは、[コードおよびテキスト要素のスタイル規則](../../../reference/code-style-elements.md)を参照してください。

## 構文およびファイル名要素 {#syntax-file-name}

送信ファイル名には、次の要素が含まれています。以下の要素はすべてオプションです。

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### パラメーター

送信データファイル名の要素の定義を次の表に示します。

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファイル名要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>データ転送方法を参照します。転送方法には以下が含まれます。 </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - SFTP を使用した転送 </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3</span> - <span class="keyword">Amazon AWS</span> への転送 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>宛先 ID。 </p> <p><span class="keyword">Audience Manager</span> では、宛先は、ターゲット設定可能なセグメントをマッピングできる統合のインスタンスです。顧客は、ビジネス要件に応じて、複数の宛先を持つことができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>データプロバイダーまたはデータソース ID。この ID は、ファイルコンテンツに存在するユーザー ID のタイプを識別します。最も一般的なユーザー ID キーを次に示します。 </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword">Google 広告主 ID</span>（raw、ハッシュ化されていない） </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword">広告主用 Apple ID</span>（raw、ハッシュ化されていない） </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">ベンダー ID - サードパーティユーザー ID（Web／Cookie） </li> 
     </ul> </p> <p>詳しくは、「<a href="https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/features/data-sources/global-data-sources.html">グローバルデータソース</a>」を参照してください。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> サードパーティプラットフォームからの顧客識別子。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>同期モードは、同期タイプに基づいてファイル名にラベルを追加するマクロプレースホルダーです。同期タイプには、完全および増分があります。ファイル名に <code> iter </code> または <code> full </code> として現れます。 </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>：「反復」または増分同期を示します。増分ファイルには、最後の同期以降に収集された新しいデータのみが含まれます。 </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>：「完全」同期を示します。完全に同期されたファイルには、古いデータと最後の同期以降に収集された新しいデータが含まれます。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>UTC タイムゾーンの 13 桁の UNIX タイムスタンプ（ミリ秒）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>整数。処理時間を向上するために複数の部分に分割されたファイルの部分を特定します。番号は、データが属する元のファイルのどの部分かを示します。</p>  <p>3 桁以上の整数にする必要があり、分割サイズが 100 よりも小さいは、前にゼロを付ける必要があります。</p>  <p>元のファイルには、分割番号はありません。最初の分割ファイルは、001 で終わります。後述の例を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP 圧縮。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## ファイル名の例 {#file-name-examples}

### シナリオ 1

[!DNL Amazon S3] の場所に送信されたファイルで、*`PID_ALIAS="XYZCustomer"`* を満たし、かつファイルコンテンツに [!DNL Google Advertiser IDs] を含むもの。

例：増分ファイル：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

例：完全ファイル：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### シナリオ 2

[!DNL FTP] の場所に送信されたファイルで、*`PID_ALIAS`* がなく、ファイルコンテンツに [!DNL Apple Advertiser IDs] を含むもの：

例：増分ファイル：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

例：完全ファイル：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**シナリオ 3**：[!DNL FTP]で *`PID_ALIAS="XYZCustomer"`* の場所に送信されたファイルで、ファイルコンテンツにサードパーティユーザー ID （*`Vendor ID=45454`*）を含むもの。

例：増分ファイル：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

例：完全ファイル：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## 送信データファイルコンテンツ：構文とパラメーター {#outbound-contents-syntax}

送信データファイルの情報を編成するのに使用する必須フィールド、構文、規則について説明します。これらの仕様に従って、データの形式を設定します。

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>スタイル要件（`monospaced text`、*斜体*、括弧 `[ ]` `( )`、など）コード要素およびオプションを表します。詳しくは、[コードおよびテキスト要素のスタイル規則](../../../reference/code-style-elements.md)を参照してください。

### 構文

データファイルのフィールドの順序は次のとおりです。

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### パラメーター

データファイルのコンテンツを定義する変数を次の表に示します。

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> により割り当てられた一意のユーザー ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>UUID とセグメントデータをスペースで区切ります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>訪問者が属するセグメントの ID。複数のセグメントをコンマで区切ります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>ユーザーが対象外だったセグメントの ID。複数のセグメントをコンマで区切ります。完全同期を使用すると、データファイルにはユーザーの現在のセグメントの完全なリストが含まれるので、削除されたセグメントを無視できます。通常、ユーザーが削除されたセグメントではなく、ユーザーが属するセグメントを知る必要があります。詳しくは、<a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples">送信データファイル名：構文と例 </a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 例：基本的なファイル形式

適切な形式のデータファイルは次のサンプルのようになります。このファイルエントリは、セグメント 24、26 および 27 の対象となるユーザーを示します。必要に応じて、スペースで `UUID` とセグメント ID を区切ります。もう 1 つのスペースで、セグメント ID のセットを区切ります。この例では、ユーザーは、セグメント 24、26 および 27 に属します。セグメント 25 および 28 からは削除されています。

```
59767559181262060060278870901087098252  24,26,27  25,28
```
