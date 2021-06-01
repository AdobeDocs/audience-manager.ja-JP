---
description: データ送信先のドメインを作成および管理できるドメイン管理メソッド（Cookie の宛先の場合のみ）。
seo-description: データ送信先のドメインを作成および管理できるドメイン管理メソッド（Cookie の宛先の場合のみ）。
seo-title: ドメイン管理 API メソッド
solution: Audience Manager
title: ドメイン管理 API メソッド
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 100%

---

# ドメイン管理 API メソッド {#domain-management-api-methods}

データ送信先のドメインを作成および管理できるドメイン管理メソッド（Cookie の宛先の場合のみ）。

<!-- c_partner_site.xml -->

## 新しいドメインの作成 {#create-new-domain}

新しいドメインを作成できる `POST` メソッド（Cookie の宛先の場合のみ）。

<!-- r_post_new_partner_site.xml -->

### リクエスト

`POST` `https://api.demdex.com/v1/partner-sites/`

### リクエストのサンプル

```
{
   "url":"example1.com"
}
```

### 応答

成功すると、`201 created` とパートナーサイトが返されます。パートナーサイトの一意の ID もあわせて返されます。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## ドメインの削除 {#delete-domain}

ドメインを削除できる `DELETE` メソッド（Cookie の宛先の場合のみ）。

<!-- r_delete_partner_site.xml -->

### リクエスト

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 応答

成功するとレスポンスで `204 no content` が返されます。パートナーサイトが見つからない場合は `404 not found` が返されます。

## ドメインのプロパティを返す {#return-props-domain}

指定されたドメインに関する詳細を返す `GET` メソッド（Cookie の宛先の場合のみ）。

<!-- r_get_partner_site.xml -->

### リクエスト

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 応答

成功すると、`200 OK` とデータが以下のサンプルのように返されます。サイト ID やパートナーが見つからない場合、`404 Not found` が返されます。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## すべてのドメインのプロパティを返す {#return-props-all-domains}

すべてのドメインに関する情報を返す `GET` メソッド（Cookie の宛先の場合のみ）。

<!-- r_get_partner_sites.xml -->

### リクエスト

`GET https://api.demdex.com/v1/partner-sites/`

### オプションのクエリパラメーター

オブジェクトの&#x200B;*すべて*&#x200B;のプロパティを返す [!DNL API] メソッドで、これらのオプションパラメーターを使用できます。そのクエリを [!DNL API] に渡す際に、リクエスト文字列にこれらのオプションを設定します。[オプションのパラメーター](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)を参照してください。

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
   <td colname="col2"> 指定された JSON プロパティに従って、結果を並べ替えて返します。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 結果を降順で並べ替えて返します。昇順がデフォルトです。 </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">検索パラメーターとして使用する指定文字列に基づいて結果を返します。例えば、項目の任意のフィールドに「Test」という語があるすべてのモデルの結果を探したい場合は、サンプルリクエストは次のようになります。    <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>を参照してください。 </p> <p>「get all」メソッドで返されるすべての値を検索できます。 </p> </td>
  </tr> 
 </tbody> 
</table>

### 応答

成功すると、`200 OK` とデータが配列で以下のサンプルのように返されます。サイト ID やパートナーが見つからない場合、`404 Not found` が返されます。

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```
