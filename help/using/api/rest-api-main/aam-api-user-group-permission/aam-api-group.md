---
description: グループの管理（グループの作成、更新、リスト、削除など）をおこなうための Rest API メソッド。
seo-description: グループの管理（グループの作成、更新、リスト、削除など）をおこなうための Rest API メソッド。
seo-title: グループ管理 API メソッド
solution: Audience Manager
title: グループ管理 API メソッド
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 100%

---

# グループ管理 API メソッド {#group-management-api-methods}

グループの管理（グループの作成、更新、リスト、削除など）をおこなうための Rest [!DNL API] メソッド。

<!-- c_rest_api_user_man_group.xml -->

## グループの作成 {#create-group}

新しいユーザーグループを作成するための `POST` メソッド。

<!-- r_rest_api_group_create.xml -->

### リクエスト

`POST /api/v1/groups/`

### リクエスト本文のサンプル

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### 応答

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## グループの更新 {#update-group}

ユーザーグループを更新するための `PUT` メソッド。

<!--
r_rest_api_group_update.xml
-->

### リクエスト

`PUT /api/v1/groups/`*`<groupId>`*

### リクエスト本文のサンプル

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### 応答

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## グループのリスト {#list-groups}

ユーザーグループのリストを表示するための `GET` メソッド。

<!--
r_rest_api_group_list.xml
-->

### リクエスト

`GET /api/v1/groups/`

### 応答

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## グループの削除 {#delete-groups}

ユーザーグループを削除し、そのグループからすべてのメンバーを削除するための `DELETE` メソッド。

<!-- r_rest_api_group_delete.xml -->

### リクエスト

`DELETE /api/v1/groups/`*`<groupId>`*

成功すると `204 No Content` が返されます。競合が発生する場合、`409 Conflict` が返されます。

## グループの一括削除 {#delete-groups-bulk}

複数のグループを一括で削除し、そのグループからすべてのメンバーを削除するための `DELETE` メソッド。

<!-- r_rest_api_group_delete_bulk.xml -->

### リクエスト

`DELETE /api/v1/groups/bulk-delete`

成功すると `204 No Content` が返されます。競合が発生する場合、`409 Conflict` が返されます。

## グループのすべての権限のリスト {#list-permissions-group}

グループの権限オブジェクトのリストを表示するための `GET` メソッド。

<!-- r_rest_api_perm_list_group.xml -->

### リクエスト

`GET /api/v1/groups/{groupId}/permissions`

### 応答

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

グループにアクセスできない場合、`400 Bad Request` を返します。

## グループの権限の設定 {#set-permissions-group}

グループ権限を更新するための `PUT` メソッド。このメソッドは、古い権限を新しい権限で上書きします。

<!-- r_rest_api_perm_set.xml -->

### リクエスト

`PUT /api/v1/groups/{groupId}/permissions/`

### 応答

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

このレスポンスのサンプルは、更新された権限オブジェクトのリストを表しています。

成功すると `200 OK` が返されます。無効な権限がある場合、`400` が返されます。また、ログインしたユーザーがオブジェクトにアクセスできない場合は `403` が返されます。
