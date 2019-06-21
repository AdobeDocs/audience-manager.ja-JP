---
description: セグメント - 広告ユニット間重複レポートは、広告ユニットと Audience Manager セグメントの間の重複が多い部分と少ない部分を強調したヒートチャートとして表示されます。
seo-description: セグメント - 広告ユニット間重複レポートは、広告ユニットと Audience Manager セグメントの間の重複が多い部分と少ない部分を強調したヒートチャートとして表示されます。
seo-title: セグメント - 広告ユニット間重複
solution: Audience Manager
title: セグメント - 広告ユニット間重複
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# セグメント - 広告ユニット間重複{#segment-to-ad-unit-overlap}

セグメント - 広告ユニット間重複レポートは、広告ユニットと Audience Manager セグメントの間の重複が多い部分と少ない部分を強調したヒートチャートとして表示されます。

## ユースケース {#use-cases}

[!UICONTROL Segment to Ad Unit Overlap] レポートでは、どのオーディエンスがWebプロパティを訪問したかを把握できます。このレポートには、[!DNL Audience Manager] セグメントのメンバーと Web プロパティの訪問者数の間の重複が表示されます。重複が多い場合は、セグメントの多数のメンバーが Web プロパティを訪問していることになります。

## セグメント - 広告ユニット間重複レポートの使用 {#using-the-report}

Use the **[!UICONTROL Top N Ad Units]** and **[!UICONTROL Top N Segments]** controls to select your desired number of ad units and segments for the overlap. それぞれ、最大 100 個の項目を選択できます。

**Day Range** コントロールと **Date Through コントロールを使用して、ルックバック範囲を調整します。** 7 日と 30 日のルックバック期間は、日付が日曜日の場合にのみ有効であることに注意してください。

**[!UICONTROL Segment Name]****[!UICONTROL Ad Unit]** このボックスを使用して、セグメントと広告ユニットのいずれかをフィルタリングします。

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## 結果の解釈 {#interpreting-results}

[!UICONTROL Segment to Ad Unit Overlap] レポートは以下のようになります。任意のセルの上にマウスポインターを置くと、その特定の重複に関する詳細が表示されます。追加情報については、サンプルレポートの下の表を参照してください。

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Ad Unit </span> </p> </td> 
   <td colname="col2"> <p>インベントリ項目の名前。例えば、Web サイトの 1 つや Web サイト上の記事などです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment Real Time Uniques Count</span> </p> </td> 
   <td colname="col2"> <p>指定した時間範囲にリアルタイムで認識され、また <span class="keyword"> Audience Manager</span>で認識された時点でセグメントの対象として認定された個別訪問者の数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Ad Unit Uniques Count</span> </p> </td> 
   <td colname="col2"> <p>この特定の広告ユニットの訪問者の数。この情報は DFP ログから抽出されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap Uniques Count</span> </p> </td> 
   <td colname="col2"> <p>広告ユニット項目が表示されたセグメントメンバーの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap Percentage</span> </p> </td> 
   <td colname="col2"> <p>広告ユニット母集団とセグメント母集団の間の重複。これは、「<span class="wintitle"> Overlap Uniques Count</span>」を「<span class="wintitle"> Segment Real Time Uniques</span>」に占める割合（パーセント）で表したものです。 </p> </td> 
  </tr> 
 </tbody> 
</table>

