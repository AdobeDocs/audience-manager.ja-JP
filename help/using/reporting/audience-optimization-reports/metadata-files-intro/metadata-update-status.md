---
description: S3 ステータスディレクトリには .info ファイルがあり、アップロードされたファイルの成功と失敗に関する情報が格納されています。ファイルには JSON 形式のデータがあり、ステータスの結果が配列に格納されています。
seo-description: S3 ステータスディレクトリには .info ファイルがあり、アップロードされたファイルの成功と失敗に関する情報が格納されています。ファイルには JSON 形式のデータがあり、ステータスの結果が配列に格納されています。
seo-title: メタデータファイルのステータスの更新
solution: Audience Manager
title: メタデータファイルのステータスの更新
uuid: 56a1e88a-41da-4d51-a21e-2be98cca7fa2
feature: ログファイル
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 100%

---


# メタデータファイルのステータスの更新{#status-updates-for-metadata-files}

S3 status ディレクトリには `.info` ファイルがあり、アップロードされたファイルの成功と失敗に関する情報が格納されています。ファイルには JSON 形式のデータがあり、ステータスの結果が配列に格納されています。

`.info` ファイルのコンテンツは、以下の例のようになります。

```js
//sample file path
/log_ingestion/pid=1234/dpid=567/status/20150827.info

//sample contents
{
    "Files": [
        {
            "FileByteSize": 488900,
            "FileChecksumMD5": "94b821082daff242e452c0d8796b08f0",
            "FileName": "20141112_4_2",
            "MetadataType": "Creative",
            "Parent": "Site",
            "Status": "SUCCESS",
            "Description": ""
        },
        {
            "FileByteSize": 58812,
            "FileChecksumMD5": "db79f148e6a635629701c13a7bcc8db0",
            "FileName": "20141112_0_4",
            "MetadataType": "Site",
            "Parent": "None",
            "Status": "FAILURE",
            "Description": "Invalid format."
        }
    ],
    "Summary": {
        "Day": "2014-11-12",
        "ProcessingTimeRFC2822": "Wed, 10 Dec 2014 21:07:58 -0000",
        "ProcessingTimestampPOSIX": 1418263678,
        "TotalByteSize": 547712,
        "TotalNumberFiles": 2,
        "NumberSuccess": 1,
        "NumberFailure": 1,
        "GlobalStatus": "FAILURE"
    }
}
```

## 定義済みのメタデータのキーと値のペア {#key-value-pairs}

次の表は、メタデータステータスファイルの「`Files`」セクションと「`Summary`」セクションにあるキーの一覧とその定義です。

**Files 配列のキー**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> キー </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Description</code> </p> </td> 
   <td colname="col2"> <p>処理が失敗した理由の簡単な説明が含まれています。処理が成功した場合、このフィールドは空白となります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>ファイルサイズ（バイト単位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p><code> meta</code> ディレクトリにアップロードされたメタデータファイルの MD 5 チェックサム。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p><code> meta</code> ディレクトリにアップロードされたメタデータファイルの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MetadataType</code> </p> </td> 
   <td colname="col2"> <p>ファイルに含まれるデータの種類を示すわかりやすい名前。ファイル名の子 ID に基づいています。 </p> <p><a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md">メタデータファイルの命名規則</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Parent</code> </p> </td> 
   <td colname="col2"> <p>ファイルに含まれるデータの種類を示すわかりやすい名前。ファイル名の親 ID に基づいています。 </p> <p><a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md">メタデータファイルの命名規則</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Status</code> </p> </td> 
   <td colname="col2"> <p>メタデータファイルの処理状態を表す 2 通りのテキスト値を返します。 </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**概要オブジェクトのキー**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> キー </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>ファイル処理日（<code><i>yyyy-mm-dd</i></code> 形式）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>1 日の間での、すべてのファイルの処理状態を表す 2 通りのテキスト値を返します。 </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberFailure</code> </p> </td> 
   <td colname="col2"> <p>処理が失敗したファイルの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberSuccess</code> </p> </td> 
   <td colname="col2"> <p>処理が成功したファイルの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>処理開始時刻を表す、わかりやすいタイムスタンプを返します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimePOSIX</code> </p> </td> 
   <td colname="col2"> <p>処理開始時刻を表す UNIX タイムスタンプ。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>1 日のすべてのメタデータの合計バイト数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>1 日に処理されたファイルの総数。 </p> </td> 
  </tr> 
 </tbody> 
</table>
