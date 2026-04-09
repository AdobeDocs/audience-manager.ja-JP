---
description: Audience Manager の DCS 地域のリストをブログラムで取得するためのメソッド。
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: DCS 地域 API メソッド
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
TQID: https://experienceleague.adobe.com/ipsOlq24Y00SHvGKgUFJHnRQ11DZIuDNY76D5LCAgso
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 110
ht-degree: 100%

---

# DCS 地域 API メソッド {#dcs-region-api-methods}

Audience Manager の [!DNL DCS] 地域のリストをブログラムで取得するためのメソッド。

<!-- c_rest_api_regions.xml -->

地域と対応する整数の一覧については、[DCS の地域 ID、場所、ホスト名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)を参照してください。

## 特定の DCS リージョンのリスト {#list-specific-dcs-region}

特定の [!DNL DCS] 地域のリストを返す `GET` メソッド。

<!-- r_rest_api_regions_list_specific.xml -->

### リクエスト

`GET /v1/dcs-regions/`*`<id>`*

### レスポンスのサンプル

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

成功すると `200 OK` が返されます。

地域と対応する整数の一覧については、[DCS の地域 ID、場所、ホスト名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)を参照してください。

## DCS リージョンのリスト {#list-dcs-regions}

[!DNL DCS] 地域のリストを返す `GET` メソッド。

<!-- r_rest_api_regions_list.xml -->

### リクエスト

`GET /v1/dcs-regions/`

### レスポンスのサンプル

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

成功すると `200 OK` が返されます。

地域と対応する整数の一覧については、[DCS の地域 ID、場所、ホスト名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)を参照してください。
