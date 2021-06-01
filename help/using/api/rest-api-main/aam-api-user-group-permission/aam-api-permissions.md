---
description: オブジェクトおよびグループの権限を管理するための Rest API メソッド。
seo-description: オブジェクトおよびグループの権限を管理するための Rest API メソッド。
seo-title: 権限管理 API メソッド
solution: Audience Manager
title: 権限管理 API メソッド
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 100%

---

# 権限管理 API メソッド {#permissions-management-api-methods}

オブジェクトおよびグループの権限を管理するための Rest [!DNL API] メソッド。

<!-- c_rest_api_perm_man.xml -->

## 使用可能なオブジェクトタイプのリストを表示 {#list-object-types}

役割に基づくアクセス制御を設定できる使用可能なオブジェクトタイプのリストを返す `GET` メソッド。

<!-- r_rest_api_perm_list.xml -->

### リクエスト

`GET /api/v1/permissionable-object-types/`

### 応答

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## オブジェクトタイプで使用可能な権限のリスト {#list-permissions-object-type}

オブジェクトタイプに使用可能な権限のリストを返す `GET` メソッド。

<!-- r_rest_api_perm_list_perms.xml -->

### リクエスト

`GET /api/v1/permissionable-object-types/SEGMENT/`

### 応答

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>オブジェクトタイプ TAGS および DERIVED SIGNALS では、通常使用する権限はありません。これらのオブジェクトタイプに対する制御は「All」または「Nothing Wild Card Permissions」のみとなります。
