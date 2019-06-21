---
description: ファイルベースの ID 同期に使用される必須フィールド、構文および命名規則について説明します。これらの仕様に従って、ファイルコンテンツを命名し編成します。
seo-description: ファイルベースの ID 同期に使用される必須フィールド、構文および命名規則について説明します。これらの仕様に従って、ファイルコンテンツを命名し編成します。
seo-title: ID 同期ファイルの名前およびコンテンツの要件
solution: Audience Manager
title: ID 同期ファイルの名前およびコンテンツの要件
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# ID 同期ファイルの名前およびコンテンツの要件 {#name-and-content-requirements-for-id-synchronization-files}

ファイルベースの ID 同期に使用される必須フィールド、構文および命名規則について説明します。これらの仕様に従って、ファイルコンテンツを命名し編成します。

>[!NOTE]
>
>テキストスタイル（`monospaced text`斜体 * *、括弧 `[ ]` `( )`、その他）コード要素およびオプションを表します。詳しくは、[コードおよびテキスト要素のスタイル規則](../../../reference/code-style-elements.md)を参照してください。

## ファイル名構文および例 {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID ファイル名には、以下の必須およびオプション要素が含まれます。

`adobe_id_`*`MASTERDPID_DPID[_DPID_DPID`*`]_`*`TIMESTAMP`*`.sync[.`*`SPLIT_NUMBER`*`][.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>ファイルを ID ファイルとして識別する静的なプレフィックス。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> マスターデータプロバイダー ID は、ファイル名の DPID の親 ID です。また、データファイルの最初のユーザー ID は、マスター ID に対応します。次の DPID は、マスターに属する他の識別子です。同期をおこなうと、ファイル名の DPID がファイル内の UUID にマッピングされます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>データプロバイダー ID。これらの ID は、マスター DPID に関連付けられたエンティティまたはデータソースを表しています。同期をおこなうと、ファイル名の DPID がファイル内の UUID にマッピングされます。 </p> <p>ファイル名の DPID の数は、データファイル内の UUID の数に一致する必要があります。例えば、ファイル名にマスター DPID および 3 つの DPID が含まれているとします。データファイルには、後述のファイルコンテンツの節で説明する形式で、UUID の 4 つの対応する列が含まれている必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>10 桁の UNIX タイムスタンプ（秒単位）。タイムスタンプは、各ファイル名を一意にするのに役立ちます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>通常の完全同期を示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整数。大きなファイルを複数の小さいファイルに分割する際に使用されます。これは、処理時間の向上に役立ちます。数は、送信している元のファイルのどの部分かを示します。後述のファイル名の例を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>ファイルがオプションの gzip 圧縮で圧縮されていることを示します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### ファイル名の例

以下の例に、適切に書式設定されたファイル名を示します。ファイル名は、このようになります。

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
</ul>

## ファイルコンテンツ構文および例 {#file-content-syntax}

ID ファイルのコンテンツには、以下の要素が含まれます。

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

The file contains user IDs ([!DNL UUID]). 各行では、ID をタブで区切ります。以下の例に、適切に書式設定された ID ファイルを示します。コンテンツは、このようになります。

```
abc123 def456 ghi789 xyz987
```

## 同期による DPUUID の UUID との一致 {#sync-matches-dpuuids-uuids}

ID 同期ファイルの目的は、独自のデータソースの [DPUUID](../../../reference/ids-in-aam.md) を [!DNL Audience Manager] UUID と同期することです。Synchronization maps the [!DNL DPUUID]s from the master [!DNL DPID] and its related [!DNL DPID]s to the [!DNL Audience Manager] [!DNL UUID]s. Where you put the IDs in the file name and body determines how these identifiers are mapped to each other. 例えば、以下に 2 つのサンプルファイルを示します。

* **ファイル 1：** `adobe_id_0_12345_1476312152.sync`

* **ファイル 2：** `adobe_id_12345_67890_1476312876.sync`

<br/>

このサンプル名およびコンテンツと仮定すると、ID は以下のようにお互いにマッピングされます。

**ファイル 1**（[サンプルファイルをダウンロード](assets/adobe_id_0_12345_1476312152.sync)）

| DPID 0 = Adobe Audience Manager UUIDs | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Step 1: the ID sync process will sync the [!DNL DPUUID]s from [!DNL DPID] 12345 with the [!DNL Audience Manager] [!DNL UUID]s in the left column. Note that the [!DNL DPID] &quot;0&quot; in the file name represents [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**ファイル 2**（[サンプルファイルをダウンロード](assets/adobe_id_12345_67890_1477846458.sync)）

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Step 2: the [!DNL DPUUID]s from [!DNL DPID] 12345 have been synced in step 1 with the Audience Manager [!DNL UUID]s. What this ID sync will do is sync the [!DNL DPUUID]s from [!DNL DPID] 67890 with the Audience Manager [!DNL UUID]s from step 1.

<br/>

## その他の形式要件 {#other-format-reqs}

ユーザー ID では以下のことができません。

* ID 自体にタブを含める。タブは、データファイル内で個別の ID を区切るためにのみ使用されます。
* Contain personally identifiable information ([!UICONTROL PII]).
* [!DNL URL] エンコーディングを使用します。エンコードされていない ID のみを渡します。

タブまたはスペースで終わる任意の行は、処理または認識されません。ルールとして、行末に空白文字を挿入しないようにしてください。