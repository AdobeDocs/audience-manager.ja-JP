---
description: 標準のキー値ペアとシリアル化されたキー値ペアを定義し説明します。
keywords: integration code
seo-description: 標準のキー値ペアとシリアル化されたキー値ペアを定義し説明します。
seo-title: キー値ペアの解説
solution: Audience Manager
title: キー値ペアの解説
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# キー値ペアの解説{#key-value-pairs-explained}

標準のキー値ペアとシリアル化されたキー値ペアを定義し説明します。

<!-- 

c_key_value_explained.xml

 -->

キー値ペアは 2 つの関連するデータ要素（キーと値）で構成されます。キーは、データセットを定義する定数（例：性別、色、価格など）です。値は、そのセットに属する変数（例：男性／女性、緑、100 など）です。完全形式のキー値ペアは、次のようになります。

* `gender = male`
* `color = green`
* `price > 100`

## 標準およびシリアル化されたキー値ペア {#standard-serialized-pairs}

宛先はキーと値のデータを *`standard`* または *`serialized`* 形式で受け取ります。標準形式では、データを個別のキー値ペアに編成します。各キーは、明示的に指定されます（異なる値を定義するために再利用される場合でも）。それに対して、シリアル化形式では、複数の値を単一のキーで定義された 1 つのセットにまとめます。また、シリアル化されたペアでは、キー値セット内で値を区切るために、特別なインジケーターが使用されます。最後に、標準およびシリアル化されたキー値には、単一または複数の値を含めることができます。標準およびシリアル化されたキー値形式の例を次の表に示します。

| 形式 | 単一キー | キー値ペア |
|---|---|---|
| **標準** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **シリアル型** | `x=1;2` | `x=1;2&y=3;4` |



## キー、デリミター、セパレーター {#keys-delimiters-separators}

シリアル化データを扱う場合、キー値ペア*内*およびキー値ペア*間*の値を区切る文字を指定する必要があります。キー値ペアの要素は、次のように定義されます。

* **キー：** キー値ペア内の一意の識別子。
* **キー値デリミター：** 個々のキー値ペアを区切ります。
* **キー値セパレーター：** キー値ペア内のキーと値を区切ります。
* **シリアルセパレーター：** シリアル化されたキー値ペア内の個々の値を区切ります。

## 標準およびシリアル化されたキー値要素 {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> タイプ </th> 
   <th colname="col2" class="entry"> 例 </th> 
   <th colname="col3" class="entry"> キー </th> 
   <th colname="col4" class="entry"> キー値セパレーター </th> 
   <th colname="col5" class="entry"> キー値デリミター </th> 
   <th colname="col6" class="entry"> シリアルセパレーター </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>単一キー</b> <p>（標準） </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> なし </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>キー値ペア</b> <p>（標準） </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2&amp;y=3&amp;y=4 </code> </td> 
   <td colname="col3"> x、y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>単一キー</b> <p>（シリアル） </p> </td> 
   <td colname="col2"> <code> x=1;2;3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> なし </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>キーと値のペア</b>（シリアル） </td> 
   <td colname="col2"> <code> x=1;2&amp;y=3;4 </code> </td> 
   <td colname="col3"> x、y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

