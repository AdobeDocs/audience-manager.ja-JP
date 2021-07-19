---
description: これらの RESTful API メソッドを使用して、セグメントを宛先にマッピングします。
seo-description: これらの RESTful API メソッドを使用して、セグメントを宛先にマッピングします。
seo-title: セグメントの宛先へのマッピング
solution: Audience Manager
title: セグメントの宛先へのマッピング
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
feature: API
exl-id: 906df6c5-f878-48e6-a804-eb5b4407f304
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 100%

---

# セグメントの宛先へのマッピング {#map-segments-to-a-destination}

これらの [!DNL RESTful API] メソッドを使用して、セグメントを宛先にマッピングします。

<!-- c_api_map_seg_dest.xml -->

## サポートされている宛先のタイプ：URL および Cookie のみ

利用可能な `POST` メソッドは、[!UICONTROL URL] および [!UICONTROL cookie destinations]にのみセグメントをマッピングできます。現在、これらの [!DNL REST API] メソッドを使用して、[!UICONTROL server-to-server destinations]にセグメントをマッピングすることはできません。代わりにユーザーインターフェイスを使用してください。ただし、宛先の関連 `GET` メソッドでは、ユーザーインターフェイスで作成された[!UICONTROL server-to-server destinations]の情報を取得できます。

## シリアル化されていない URL ベースの宛先へのセグメントのマッピング {#map-segment-non-serial}

シリアル化されていない [!UICONTROL URL] 宛先にセグメントをマッピングするための `POST` メソッド。

<!-- r_map_noserial_url.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### リクエストのサンプル

特に指示のない限り、すべてのリクエスト値が必須です。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### 応答

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## シリアル化された URL ベースの宛先へのセグメントのマッピング {#map-segment-serial}

シリアル化された `POST` 宛先にセグメントをマッピングするための [!UICONTROL URL] メソッド。

<!-- r_map_serialized_url.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### リクエストのサンプル

このリクエストでは、`traitAlias` はキーと値のペアのキーに対応します。特に指示のない限り、すべてのリクエスト値が必須です。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### 応答

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## Cookie ベースの宛先へのセグメントのマッピング：単一キー、非シリアル化 {#map-segment-cookie-noserial}

単一キーでシリアル化されていない [!UICONTROL cookie] 宛先にセグメントをマッピングするための `POST` メソッド。

<!-- r_map_cookie_noserial.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### リクエストのサンプル

このリクエストでは、`valueAlias` はキーと値のペアの値に対応します。特に指示のない限り、すべてのリクエスト値が必須です。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### 応答

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## Cookie ベースの宛先へのセグメントのマッピング：複数キー、非シリアル化 {#map-segment-cookie-multi-noserial}

複数キーのシリアル化されていない [!UICONTROL cookie] の宛先にセグメントをマッピングするための `POST` メソッドをを使用します。

<!-- r_map_cookie_multikey_noserial.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### リクエストのサンプル

このリクエストでは、`traitAlias` と `valueAlias` はキーと値のペアのキーと値をそれぞれ設定します。特に指示のない限り、すべてのリクエスト値が必須です。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### 応答

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Cookie ベースの宛先へのセグメントのマッピング：複数キー、シリアル化 {#map-segment-cookie-multi-serial}

複数キーのシリアル化された [!UICONTROL cookie destination]にセグメントをマッピングするための `POST` メソッド。

<!-- r_map_cookie_multikey_serialized.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### リクエストのサンプル

このリクエストでは、`traitAlias` と `valueAlias` はキーと値のペアのキーと値を設定します。特に指示のない限り、すべてのリクエスト値が必須です。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### 応答

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## サーバー間宛先へのセグメントのマッピング {#map-segment-s2s}

既存の[!UICONTROL server-to-server]宛先にセグメントをマッピングするための `POST` メソッド。現在利用可能なこれらの [!DNL API] メソッドを使用して [!UICONTROL server-to-server] を作成することはできません。

<!-- r_map_segment_s2s.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### リクエストのサンプル

このリクエストでは、`traitAlias` はキーと値のペアのキーに対応します。特に指示のない限り、すべてのリクエスト値が必須です。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### 応答

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## 宛先マッピングの一括作成 {#bulk-create}

 [!UICONTROL cookie] または [!UICONTROL URL] 宛先マッピングの配列を渡す `POST` メソッド

<!-- r_bulk_create.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### リクエストのサンプル

特に指示のない限り、すべてのリクエスト値が必須です。

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### 応答

レスポンスが正常に処理されると、作成されたマッピングの配列が返されます。

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## 宛先への複数のセグメントの追加 {#add-segments-dest}

宛先に複数のセグメントをマッピングできる `POST` メソッド。

<!-- r_add_segments_to_destination.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### リクエストのサンプル

複数の宛先マッピングを配列で作成します。特に指示のない限り、すべてのリクエスト値が必須です。

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### 応答

作成されたマッピングの配列を返します。

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## 宛先 ID による宛先の更新 {#update-dest-data-order}

`destinationId` で既存の宛先を更新できる `PUT` メソッド。

<!-- r_update_destination_data_order_id.xml -->

### リクエスト

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### リクエストのサンプル

特に指示のない限り、すべてのリクエスト値が必須です。

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 応答

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## マッピング ID による宛先へのマッピングの更新 {#update-mapping-dest-id}

指定した `PUT` で宛先へのマッピングを更新できる `mappingId` メソッド。

<!-- r_update_destination_trait_data_order_id.xml -->

### リクエスト

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### リクエストのサンプル

特に指示のない限り、すべてのリクエスト値が必須です。

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### 応答

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```

>[!MORELIKETHIS]
>
>* [宛先](../../../features/destinations/destinations.md)
* [宛先のシリアル化](../../../features/destinations/key-value-pairs.md#destination-serialized)
* [キーと値のペアの解説 ](../../../reference/key-value-pairs-explained.md)

