---
description: Audience Manager の DCS 地域のリストをブログラムで取得するためのメソッド。
seo-description: Audience Manager の DCS 地域のリストをブログラムで取得するためのメソッド。
seo-title: DCS 地域 API メソッド
solution: Audience Manager
title: DCS 地域 API メソッド
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DCS 地域 API メソッド {#dcs-region-api-methods}

Audience Manager の [!UICONTROL DCS] 地域のリストをブログラムで取得するためのメソッド。

<!-- c_rest_api_regions.xml -->

地域と対応する整数の一覧については、[DCS の地域 ID、場所、ホスト名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)を参照してください。

## 特定の DCS 地域のリスト {#list-specific-dcs-region}

特定の `GET` 地域のリストを返す [!UICONTROL DCS] メソッド。

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

## DCS 地域のリスト {#list-dcs-regions}

`GET` 地域のリストを返す [!UICONTROL DCS] メソッド。

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
