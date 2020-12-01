---
description: セグメントビルダーでは、最新性と頻度を使用すると、設定された日数ごとに繰り返されるアクションに基づいて訪問者をセグメント化することができます。
seo-description: セグメントビルダーでは、最新性と頻度を使用すると、設定された日数ごとに繰り返されるアクションに基づいて訪問者をセグメント化することができます。
seo-title: 最新性と頻度
solution: Audience Manager
title: 最新性と頻度
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 55%

---


# 最新性と頻度 {#recency-and-frequency}

[!UICONTROL Segment Builder]では、最新性と頻度を使用すると、設定された日数ごとに繰り返されるアクションに基づいて訪問者をセグメント化することができます。

Audience Manager では、[!DNL recency] と [!DNL frequency] は次のように定義されています。

* **[!UICONTROL Recency]**[!UICONTROL traits]
* **[!UICONTROL Frequency]**[!UICONTROL traits]

[!UICONTROL Recency] と [!UICONTROL Frequency] の設定は、サイト、セクションまたは特定のクリエイティブに対する実際の（または認識された）関心レベルに基づいて訪問者をセグメント化するのに役立ちます。例えば、高い最新性／頻度要件でセグメントの対象として認定されるユーザーは、それほど頻繁に訪問していないユーザーよりも、サイトまたは製品に関心がある可能性があります。

## [!UICONTROL Recency and Frequency]設定{#location}の場所

[!UICONTROL Segment Builder]では、[!UICONTROL Recency]設定と[!UICONTROL Frequency]設定は、[!UICONTROL Traits]パネルの[!UICONTROL Basic View]セクションにあります。時計アイコンをクリックして、これらのコントロールを表示します。

![](assets/recency_frequency.png)

## 制限とルール  {#limitations-rules}

最新性と頻度をセグメントの特性に適用する場合は、以下の制限およびルールを確認および理解してください。

### [!UICONTROL Recency] {#recency}

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 制限またはルール </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>最小値</b> </p> </td> 
   <td colname="col2"> <p>最新性は 0 より大きい値である必要があります。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>特性タイプ</b> </p> </td> 
   <td colname="col2"> <p>ルールベースおよびフォルダー特性にのみ最新性コントロールを適用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>サードパーティ特性</b> </p> </td> 
   <td colname="col2"> <p>個々のサードパーティ特性またはサードパーティ特性の特性グループに対して、最新性ルールを設定することはできません。最新性と頻度は、独自の特性にのみ適用されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Frequency] {#frequency}

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 制限またはルール </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>サードパーティ特性</b> </p> </td> 
   <td colname="col2"> <p>個々のサードパーティ特性またはサードパーティ特性の特性グループに対して、頻度ルールを設定することはできません。最新性と頻度は、独自の特性にのみ適用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>特性タイプ</b> </p> </td> 
   <td colname="col2"> <p>ルールベースおよびフォルダー特性にのみ頻度コントロールを適用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>最新性の要件</b> </p> </td> 
   <td colname="col2"> <p>最新性の要件を設定せずに、頻度の要件を設定できます。<i></i>頻度の値を設定するだけで、最新性のフィールドは空のままにします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>プロファイル結合ルール</b> </p> </td> 
   <td colname="col2"> <p><a href="../../faq/faq-profile-merge.md#trait-freq-device-rules">特性頻度、デバイスグラフ、プロファイル結合ルール</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最新性の例 {#recency-examples}

以下に、UI での選択に応じた、最新性の仕組みの 2 つの例を示します。

### 次よりも小さいか等しい演算子（&lt;=）の使用

![次よりも小さいか等しい](assets/less-than-equal-to.png)

この例では、スクリーンショットに示すように、&lt;= 演算子を選択します。[!UICONTROL segment][!UICONTROL traits][!UICONTROL segment][!UICONTROL segment]

![過去 5 日間](assets/last-5-days.png)

### 次よりも大きいか等しい演算子（=>）の使用

![次よりも大きいか等しい](assets/greater-than-equal-to.png)

この例では、スクリーンショットに示すように、=> 演算子を選択します。[!UICONTROL segment][!UICONTROL traits]次のタイムラインは、[!UICONTROL segment]が作成された時点の[!UICONTROL segment]資格を示しています。10月1日と10日後です。

![より早い認定](assets/earlier-qualification.png)


## 頻度キャップの例 {#frequency-capping}

[!UICONTROL trait]以下に、正しい例と間違った例を示します。

* `frequency([1000T]) <= 5`[!UICONTROL trait][!UICONTROL trait][!UICONTROL segment]

* [!UICONTROL trait][!UICONTROL trait]`frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* [!UICONTROL trait]`AND`[!UICONTROL trait]`frequency([1000T]) <= 5 AND isSiteVisitorTrait`

* [!UICONTROL segment]`(frequency([1000T] <= 2D) >= 5)`[!UICONTROL trait][!UICONTROL segment]`NOT`[!UICONTROL segment]この方法は、頻度キャップと同じ目的を提供しますが、[!DNL Audience Manager] でより優れたパフォーマンスを達成します。

>[!MORELIKETHIS]
>
>* [セグメントビルダーのコントロール：「Traits」セクション](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [セグメント式エディターで使用するコード構文](../../features/segments/segment-code-syntax.md)

