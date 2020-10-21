---
description: DIL ツール名前空間のメソッドについて説明します。これらのユーティリティ関数は、特定のタスクを実行するのに役立ちます。
seo-description: DIL ツール名前空間のメソッドについて説明します。これらのユーティリティ関数は、特定のタスクを実行するのに役立ちます。
seo-title: DIL ツール
solution: Audience Manager
title: DIL ツール
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 91%

---


# DIL ツール

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

* *`{string}`*: *（オプション）* 検索URLを含む文字列(未定義の場合に使用 `document.referrer` )。
* *`{object}`*: *（オプション）* 、、、またはの設定を含むオブジェクト `hostPattern`で `queryParam`す `queryPattern`。

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
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
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
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>検索パターンをカスタム正規表現と照合</b> </td> 
   <td> カスタム正規表現を渡し、カスタム検索を実行します。 </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
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

* *`uri {string}`*: *（オプション）* URIを含む文字列。 指定されていない場合は、デフォルトで `document.location.href` が適用されます。

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

<pre class="&ldquo;javascript&rdquo;"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
