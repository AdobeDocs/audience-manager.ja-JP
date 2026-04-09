---
description: オブジェクトおよびグループの権限を管理するための Rest API メソッド。
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: 権限管理 API メソッド
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
TQID: https://experienceleague.adobe.com/E9JWh1JKhHOSd7MzeOR8csVXChyh4Q0RiCj3Y5yb2vM
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 96
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
