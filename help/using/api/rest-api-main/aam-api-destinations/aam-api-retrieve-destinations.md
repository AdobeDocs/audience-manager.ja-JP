---
description: 指定した宛先 ID の宛先を返す GET メソッド。
seo-description: 指定した宛先 ID の宛先を返す GET メソッド。
seo-title: 宛先 ID を基準に宛先を返す
solution: Audience Manager
title: 宛先 ID を基準に宛先を返す
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
exl-id: c0850e71-7830-4635-b773-e9a28ab5bd68
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 100%

---

# 宛先 ID を基準に宛先を返す {#return-a-destination-by-destination-id}

指定した `GET` の宛先を返す `destinationId` メソッド。

<!-- r_get_all_destinations_order_id.xml -->

## リクエスト

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>`mappings` フィールドに値を入力するには、URL に `includeMappings=true` を渡します。

## 応答

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## すべての宛先を返す {#return-all-destinations}

指定したパートナーのすべての宛先を返す `GET` メソッド。

<!-- r_get_all_destinations.xml -->

### リクエスト

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *（オプション）*`containsSegment=<sid>` を渡すと、指定したセグメントにマッピングされたすべての宛先の配列が返されます。例えば、クエリは次のようになります `GET .../destinations/?containsSegment=4321`。
   >
   >
* 完全な宛先オブジェクトは返されません。完全に準備されたオブジェクトが必要な場合は、データ順序を基準に宛先を取得します。


### オプションのクエリパラメーター

オブジェクトの&#x200B;*すべて*&#x200B;のプロパティを返す API メソッドで、これらのオプションパラメーターを使用できます。そのクエリを [!DNL API] に渡す際に、リクエスト文字列にこれらのオプションを設定します。[オプションのパラメーター](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)を参照してください。

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th>
   <th colname="col2" class="entry"> 説明 </th>
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td>
   <td colname="col2"> ページ番号を返します。番号は 0 から始まります。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> リクエストによって返された応答結果の番号を設定します（10 がデフォルト）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">指定された <span class="keyword">JSON</span> プロパティに従って、結果を並べ替えて返します。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 結果を降順で並べ替えて返します。昇順がデフォルトです。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">検索パラメーターとして使用する指定文字列に基づいて結果を返します。例えば、項目の任意のフィールドに「Test」という語があるすべてのモデルの結果を探したい場合は、サンプルリクエストは次のようになります。    <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>を参照してください。 </p> <p>「get all」メソッドで返されるすべての値を検索できます。 </p> </td>
  </tr>
 </tbody>
</table>

### 応答

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## マッピング ID で宛先マッピングを返す {#return-dest-mapping-id}

`GET` に基づいて個々の宛先マッピングを返す `mappingId` メソッド。

<!-- r_get_destination_trait_data_order.xml -->

### リクエスト

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`*`<destinationMappingId>`*

### 応答

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## 宛先マッピングを返す {#return-dest-mappings}

宛先のマッピングを返す `GET` メソッド。

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>返されるマッピングは、宛先タイプと設定に特有のものです。

### リクエスト

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings`

>[!NOTE]
>
>ページングパラメーターをサポートしています。

### 応答

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## 使用可能な宛先プラットフォームをすべて返す {#return-dest-platforms}

宛先の使用可能なデバイスプラットフォームをすべて返す `GET` メソッド。

<!-- r_get_dest_platforms.xml -->

### リクエスト

`GET /destinations/configurations/available-platforms/`

### 応答

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## S2S および一括 S2S 宛先ジョブ履歴を返す {#return-job-history}

送信[!UICONTROL Server-to-Server]（[!UICONTROL S2S]）および一括[!UICONTROL S2S]宛先のジョブ履歴情報を返す `GET` メソッド。

<!-- r_get_job_history.xml -->

### リクエスト

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

必須クエリパラメータ：`startDate` = *&lt;`epochtime`>* および `endDate` = *&lt;`epochtime`>*。

### 応答

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```
