---
description: 式ビルダーのコードエディターで式を作成する場合に参考になる例です。
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: ブール演算子と比較演算子を使用した式のサンプル
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 88%

---

# ブール演算子と比較演算子を使用した式のサンプル {#sample-expressions-with-boolean-and-comparison-operators}

[!UICONTROL Expression Builder]のコードエディターで式を作成する場合に参考になる例です。

## コードサンプルの概要 {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

[!UICONTROL Expression Builder]のコードエディターで独自の特性ルールを作成します。次の例を参照してください。例の一部では、*`key`* 変数の前に `c_` を付けて、ユーザー定義変数として識別します。 イベント呼び出しでデータを `c_` に送信するために必要であれば、*`key`* 変数でプレフィックス [!DNL Audience Manager]（またはその他の命名規則）を使用します。

## ブール式 {#boolean-expressions}

### AND の例

このルールは、ブール演算子 [!UICONTROL AND] を使用して特性認定要件を設定します。

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> サンプルコード </th> 
   <th colname="col2" class="entry"> 訪問者が認定されるための条件 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">特定の製造元とモデルを検索します。 </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">検索結果ページから製品を探します（search = "1" または "true"）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### OR の例

このルールでは、[!DNL Boolean] 演算子 [!UICONTROL OR] と [!UICONTROL AND] を使用して特性認定要件を指定しています。

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> サンプルコード </th> 
   <th colname="col2" class="entry"> 訪問者が認定されるための条件 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> 変数 <code><i>a </i></code> または <code><i>b </i></code> および <code><i>c </i></code> で設定された条件を満たします。 </td> 
  </tr> 
 </tbody> 
</table>

## 「次より大きい」、「次より小さい」、「次と等しい」を使用した範囲の例

このルールでは、範囲を使用して特性認定要件を指定しています。

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> サンプルコード </th> 
   <th colname="col2" class="entry"> 訪問者が認定されるための条件 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> 1.00 と 100.00 の範囲の価格条件を満たしている。 </td> 
  </tr> 
 </tbody> 
</table>
