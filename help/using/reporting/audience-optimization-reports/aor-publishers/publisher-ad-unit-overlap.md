---
description: 広告ユニット間重複レポートは、広告ユニット間の重複が多い部分と少ない部分を強調したヒートチャートとして表示されます。
seo-description: 広告ユニット間重複レポートは、広告ユニット間の重複が多い部分と少ない部分を強調したヒートチャートとして表示されます。
seo-title: 広告ユニット間重複
solution: Audience Manager
title: 広告ユニット間重複
uuid: e4467e81-acbf-474e-b501-89d57395651f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 広告ユニット間重複{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]** このレポートは、広告数量の間の上下にハイライトされるヒートチャートとして表示されます。

## ユースケース {#use-cases}

**[!UICONTROL Ad Unit Overlap]** レポートを使用すると、オーディエンスがWebプロパティに重なる場所についての洞察を得ることができます。このレポートでは、上位 100 件の関連プロパティを検討し、それらの間の重複を示します。

## 広告ユニット間重複レポートの使用 {#using-the-report}

Use the **[!UICONTROL Top N Base Ad Units]** and **[!UICONTROL Top N Overlapping Ad Units]** controls to select your desired number of ad units for the overlap. それぞれ、最大 100 個の項目を選択できます。

**Day Range** コントロールと **Date Through コントロールを使用して、ルックバック範囲を調整します。** 7 日と 30 日のルックバック期間は、日付が日曜日の場合にのみ有効であることに注意してください。

Use the **[!UICONTROL Base Ad Unit]** and the **[!UICONTROL Overlap Ad Unit]** controls to select which of your ad units you want to display in the overlap report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## 結果の解釈 {#interpreting-results}

[!UICONTROL Ad Unit Overlap] レポートは以下のようになります。任意のセルの上にマウスポインターを置くと、その特定の重複に関する詳細が表示されます。追加情報については、サンプルレポートの下の表を参照してください。

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap Ad Unit</span> </p> </td> 
   <td colname="col2"> <p>インベントリ項目の名前。例えば、Web サイトの 1 つや Web サイト上の記事などです。上記の図では、ベース広告ユニットは記事 9 ～ 18 です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Base Ad Unit</span> </p> </td> 
   <td colname="col2"> <p>インベントリ項目の名前。例えば、Web サイトの 1 つや Web サイト上の記事などです。上記の図では、ベース広告ユニットは記事 1 ～ 8 です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap Ad Unit Uniques Count</span> </p> </td> 
   <td colname="col2"> <p>広告ユニット項目 9 ～ 18 を訪問したユーザーの数。この情報は DFP ログから抽出されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Base Ad Unit Uniques Count</span> </p> </td> 
   <td colname="col2"> <p>広告ユニット項目 1 ～ 8 を訪問したユーザーの数。この情報は DFP ログから抽出されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap Uniques Count</span> </p> </td> 
   <td colname="col2"> <p>「<span class="wintitle"> Base Ad Unit</span>」を訪問したユーザーと「<span class="wintitle"> Overlap Ad Unit</span>」を訪問したユーザー間の重複。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap Percentage</span> </p> </td> 
   <td colname="col2"> <p>「<span class="wintitle"> Base Ad Unit</span>」を訪問したユーザーと「<span class="wintitle"> Overlap Ad Unit</span>」を訪問したユーザー間の重複。これは「<span class="wintitle"> Overlap Uniques Count</span>」を「<span class="wintitle"> Base Ad Unit</span>」に占める割合（パーセント）で示したものです。 </p> </td> 
  </tr> 
 </tbody> 
</table>
