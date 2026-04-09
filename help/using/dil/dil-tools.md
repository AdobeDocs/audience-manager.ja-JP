---
description: DIL ツール名前空間のメソッドについて説明します。これらのユーティリティ関数は、特定のタスクを実行するのに役立ちます。
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL ツール
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
TQID: https://experienceleague.adobe.com/W3xzJ172rBhQ9Flqs5towA5pE3-nJHpwnJ1jd1mXIyo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 343
ht-degree: 81%

---

# DIL ツール

>[!WARNING]
>
>2023年7月以降、Adobeは[!DNL Data Integration Library (DIL)]と[!DNL DIL]拡張機能の開発を中止しました。
>
>既存のお客様は、引き続き[!DNL DIL]実装を使用できます。 ただし、Adobeはこの時点を超えて[!DNL DIL]を開発しません。 お客様は、長期的なデータ収集戦略について[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を評価することをお勧めします。
>
>2023年7月以降に新しいデータ収集インテグレーションを導入するお客様は、代わりに[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を使用してください。

`DIL.tools` 名前空間のメソッドについて説明します。これらのユーティリティ関数は、特定のタスクを実行するのに役立ちます。

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

現在のページに到達するために使用された検索語句を返します。

<!-- 

r_dil_get_search_referrer.xml

 -->

### `getSearchReferrer` の用途

DIL では、`getSearchReferrer` はサイトに到達するために使用された検索結果（名前とキーワード）を返します。この関数には特定の検索語句を渡すこともできますが、デフォルトでは、`document.referrer` を基に、サポートされている検索エンジン（[!DNL AOL]、[!DNL Ask]、[!DNL Bing]、[!DNL Google] および [!DNL Yahoo]）が検索されます。

### 関数シグネチャ

関数シグネチャ：`DIL.tools.getSearchReferrer(uri, initConfig)`

### 関数のパラメーター

`getSearchReferrer` では次のパラメーターを使用します。

* *`{string}`*：*（オプション）*&#x200B;検索 URL を含む文字列（定義されていない場合は `document.referrer` が使用されます）。
* *`{object}`*：*（オプション）*`hostPattern`、`queryParam` または `queryPattern` の設定が格納されたオブジェクト。

また、次のものを返します。

* `{object}`：有効な名前とキーワードを含むオブジェクト。

### 例

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> 検索タイプ </th> 
   <th> 説明 </th> 
   <th> コードサンプル </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> デフォルトの検索</td> 
   <td> AOL、Ask、Bing、Google および Yahoo の各検索エンジンが使用する検索語句を返します。 </td> 
   <td>
      <code>var&nbsp;results&nbsp;=&nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>カスタム URL を渡す</td> 
   <td>カスタム URL に基づいて検索リファラーを返します。</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>ホスト名をカスタム正規表現と照合</b></td> 
   <td> カスタム正規表現を渡し、参照 URL のホスト名と照合します。 </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",&lbrace; 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      &rbrace;); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>検索パターンをカスタム正規表現と照合</b> </td> 
   <td> カスタム正規表現を渡し、カスタム検索を実行します。 </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      &lbrace;
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      &rbrace;);
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

Uniform Resource Identifier（[!DNL URI]）を構成コンポーネント（`hash`、`host`、`href`、`pathname`、`protocol`、`search` および `[!DNL uriParams]`）に変換します。

<!-- 

r_dil_decompose.xml

 -->

関数シグネチャ：`DIL.tools.decomposeURI`

### 関数のパラメーター

`decomposeURI` では次のパラメーターを使用します。

* *`uri {string}`*：*（オプション）* URI を含む文字列。指定されていない場合は、デフォルトで `document.location.href` が適用されます。

また、次のものを返します。

* *`{object}`*：有効な名前とキーワードを含むオブジェクト。

### サンプルコード


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## getMetaTags

Web ページ上のメタタグで定義された特定のコンテンツを検索し、そのデータをオブジェクトで返します。

<!-- 

r_dil_get_metatags.xml

 -->

### 関数シグネチャ

関数シグネチャ：`DIL.tools.getMetaTags( 1 or more parameters)`

### 関数のパラメーター

`getMetaTags` は、検索する名前パラメーター（文字列タイプ）を 1 つ以上使用します。キーと値のペアで構成されるオブジェクトが返されます。

### サンプルコード

<pre class="javascript"><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: <i>&grave;partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
