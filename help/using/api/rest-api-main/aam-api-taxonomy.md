---
description: Audience Manager の一般的な分類を表示するためのメソッド。このオプションの分類スキームでは、特性を業界標準のカテゴリに整理します。
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: 分類 API メソッド
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
TQID: https://experienceleague.adobe.com/LIHEWvF3t-VNHJEviomvCF-dxE2Jy-BFxBynonvwP3w
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
topic_v2: id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 100%

---

# 分類 API メソッド {#taxonomic-api-methods}

Audience Manager の一般的な分類を表示するためのメソッド。このオプションの分類スキームでは、特性を業界標準のカテゴリに整理します。

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>これらのメソッドで新しい分類カテゴリを作成したり、特性を分類することはできません。特性を分類するには、特性の作成または更新メソッドで適切な `categoryId` を指定します。

## 特定の分類を返す {#return-specific-taxonomy}

指定した分類カテゴリに関する詳細を返すための `GET` メソッド。

<!-- r_rest_api_taxonomy.xml -->

### リクエスト

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 応答

成功すると、`200 OK` と、指定した ID のカテゴリが返されます。ID が存在せずリクエストが失敗した場合、`404 No Content` が返されます。

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## すべての分類カテゴリを返す {#return-all-taxonomy-categories}

トップレベルのカテゴリのリストを配列で返すための `GET` メソッド。

<!-- r_rest_api_taxonomies.xml -->

### リクエスト

`GET https://api.demdex.com/v1/taxonomies/0/`

### 応答

簡潔になるよう一部省略されています。

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## 分類サブカテゴリを返す {#return-taxonomy-sub-categories}

指定した親カテゴリのサブカテゴリを配列で返すための `GET` メソッド。

<!-- r_rest_api_taxonomy_sub.xml -->

### リクエスト

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 応答

成功すると、`200 OK` と、指定した ID のカテゴリが返されます。ID が存在せずリクエストが失敗した場合、`404 No Content` が返されます。簡潔になるよう一部省略されています。

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```
