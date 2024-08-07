---
description: （オプション）通常、関数に従ってまたは独自の内部レポートプロセスで、特性をユーザー定義タイプまたはカテゴリに割り当てるためのメソッド。
seo-description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-title: Trait Type Methods
solution: Audience Manager
title: 特性タイプメソッド
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 100%

---

# 特性タイプメソッド {#trait-type-methods}

（オプション）通常、関数に従ってまたは独自の内部レポートプロセスで、特性をユーザー定義タイプまたはカテゴリに割り当てるためのメソッド。

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>特性タイプメソッドは、特性を[一般的なカテゴリ](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)で使用されるカテゴリに割り当てません。これらは、一般的な分類とは別のラベルと考えてください。

視覚的に参照する場合、[!UICONTROL Trait Types]は、[!DNL UI]配下の **[!UICONTROL Traits > Create new trait > Basic Information]** にあるドロップダウンコントロールです。

## 新しい特性タイプの作成 {#create-trait-type}

新しい特性タイプを作成するための `POST` メソッド。

<!-- r_rest_api_create_trait_type.xml -->

### リクエスト

`POST https://api.demdex.com/v1/customer-trait-types`

### リクエストのサンプル

```
{
"name":"Custom trait type"
}
```

### 応答

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## 特性タイプのプロパティを返す {#return-props}

指定した特性タイプに関する詳細を返す `GET` メソッド。

<!-- r_rest_api_get_trait_type.xml -->

### リクエスト

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### 応答

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## すべての特性タイプのプロパティを返す {#return-props-all}

すべての特性タイプに関する詳細を配列で返すための `GET` メソッド。

<!-- r_rest_api_get_trait_types.xml -->

### リクエスト

`GET https://api.demdex.com/v1/customer-trait-types/`

### 応答

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```
