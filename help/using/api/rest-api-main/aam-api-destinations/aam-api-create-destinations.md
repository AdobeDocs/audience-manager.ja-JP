---
description: これらの RESTful API メソッドで宛先を作成します。
seo-description: これらの RESTful API メソッドで宛先を作成します。
seo-title: 宛先の作成
solution: Audience Manager
title: 宛先の作成
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 100%

---


# 宛先の作成 {#create-destinations}

これらの [!UICONTROL RESTful API] メソッドで宛先を作成します。

<!-- c_create_destinations.xml -->

## サポートされている宛先のタイプ：URL および Cookie のみ

使用可能な `POST` メソッドでは、[!UICONTROL URL] および [!UICONTROL cookie destinations]のみを作成できます。現在は、[!DNL REST API] メソッドで [!UICONTROL server-to-server destinations] を使用できます。ただし、宛先の関連 `GET` メソッドでは、ユーザーインターフェイスで作成された[!UICONTROL server-to-server destinations]の情報を取得できます。

## 非シリアル URL 宛先の作成 {#create-nonserial-dest}

単一のキーと値のペア（例：`gender=male` や `gender=female`）で構成されるセグメントを受け入れる宛先を作成できる `POST` メソッド。

<!-- r_create_nonserial_destination.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`

### リクエストのサンプル

このリクエストでは、1 つの宛先を作成します。特に指示のない限り、すべてのリクエスト値が必須です。

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 応答

リクエストが成功すると、`201 created` と宛先が返されます。

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 
```

## シリアル化 URL 宛先の作成 {#create-serial-url-dest}

単一のキーに関連付けられた複数の値（例：`color=blue, red, green`）を受け入れる宛先を作成できる `POST` メソッド。

<!-- r_create_serial_url_destination.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`

### リクエストのサンプル

宛先に渡すキーと値のペアのセキュリティで保護された [!DNL URL] と区切り文字を指定します。特に指示のない限り、すべてのリクエスト値が必須です。

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### 応答

更新が成功すると、レスポンスコード `201 created` と宛先が返されます。

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

## Cookie 宛先の作成：単一のキー、非シリアル化 {#create-cookie-dest-single}

単一のキーと値のペア（例：`gender=male` や `gender=female`）で構成されるセグメントを受け入れる[!UICONTROL cookie destination]を作成できる `POST` メソッド。

<!-- r_cookie_destination_singlekey_noserial.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`

### リクエストのサンプル

特に指示のない限り、すべてのリクエスト値が必須です。

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### 応答

更新が成功すると、レスポンスコード `201 created` と宛先が返されます。

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false
} 
```

## Cookie 宛先の作成：単一のキー、シリアル化 {#create-cookie-dest-single-serial}

単一のキーに関連付けられた複数の値（例：`color=blue, red, green`）を受け入れる宛先を作成できる `POST` メソッド。

<!-- r_cookie_destination_singlekey_serial.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`

### リクエストのサンプル

特に指示のない限り、すべてのリクエスト値が必須です。

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### 応答

更新が成功すると、レスポンスコード `201 created` と宛先が返されます。

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

## Cookie 宛先の作成：複数キー、非シリアル化 {#create-cookie-dest-multi}

異なる値を持つ複数のキー（例：`gender=male; gender=female; color=blue; color=red`）を含むセグメントを受け入れる宛先を作成できる `POST` メソッド。

<!-- r_create_cookie_multikey_noserial.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`

### リクエストのサンプル

特に指示のない限り、すべてのリクエスト値が必須です。

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### 応答

更新が成功すると、レスポンスコード `201 created` と宛先が返されます。

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## Cookie 宛先の作成：複数キー、シリアル化 {#create-cookie-dest-multi-serial}

複数のキーと値（例：`gender=male, female; color=blue, red, green`）を含むセグメントを受け入れる宛先を作成できる `POST` メソッド。

<!-- r_cookie_destination_multikey_serial.xml -->

### リクエスト

`POST https://api.demdex.com/v1/destinations/`

### リクエストのサンプル

特に指示のない限り、すべてのリクエスト値が必須です。

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains",
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### 応答

更新が成功すると、レスポンスコード `201 created` と宛先が返されます。

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORELIKETHIS]
>
>* [宛先](../../../features/destinations/destinations.md)
>* [宛先のシリアル化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [キーと値のペアの解説](../../../reference/key-value-pairs-explained.md)

