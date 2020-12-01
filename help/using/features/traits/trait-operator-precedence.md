---
description: 特性ビルダーでは、以下に示す演算順序（優先順位の高い順）に従って、式を評価します。優先順位が高い演算子で定義された特性要素は、他の優先順位の演算子より先に評価されます。ここでは、優先順位に従って、高い順に各演算子をランク付けしています。
seo-description: 特性ビルダーでは、以下に示す演算順序（優先順位の高い順）に従って、式を評価します。優先順位が高い演算子で定義された特性要素は、他の優先順位の演算子より先に評価されます。ここでは、優先順位に従って、高い順に各演算子をランク付けしています。
seo-title: 特性ビルダーでの演算順序
solution: Audience Manager
title: 特性ビルダーでの演算順序
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 100%

---


# 特性ビルダーでの演算順序 {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder]では、以下に示す演算順序（優先順位の高い順）に従って、式を評価します。優先順位が高い演算子で定義された特性要素は、他の優先順位の演算子より先に評価されます。ここでは、優先順位に従って、高い順に各演算子をランク付けしています。

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 演算子の優先順位 </th> 
   <th colname="col2" class="entry"> シンボル </th> 
   <th colname="col3" class="entry"> Comments </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 丸括弧 </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> 丸括弧内の式は、常に最初に評価され、優先順位に従います。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 比較演算子 </td> 
   <td colname="col2"> &lt;&gt; &lt;&gt;= </td> 
   <td colname="col3"> 次の値より小さい、次の値より大きい、次の値以下、次の値以上が、次に評価されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 等価演算子 </td> 
   <td colname="col2"> == ! = </td> 
   <td colname="col3"> 次と等しい、次と等しくないが、前の演算子の後に評価されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1">ブール演算子 <span class="wintitle">AND</span> </td> 
   <td colname="col2"><span class="wintitle"> AND</span> </td> 
   <td colname="col3" morerows="1"> なし </td> 
  </tr> 
  <tr> 
   <td colname="col1">ブール演算子 <span class="wintitle">OR</span> </td> 
   <td colname="col2"><span class="wintitle"> OR</span> </td> 
   <td colname="col3" morerows="1"> なし </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [特性ビルダーでのブール式の使用（AND、OR、NOT）](../../reference/boolean-expressions-tsb.md)
>* [特性ビルダーでの比較演算子の使用](../../features/traits/trait-comparison-operators.md)

