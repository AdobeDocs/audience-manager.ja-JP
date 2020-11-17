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

* **[!UICONTROL Recency]:** ユーザーが最近表示または資格を持った1つ（または複数）の時間 [!UICONTROL traits]。
* **[!UICONTROL Frequency]:** ユーザーが1人（または複数）に対して視聴または資格を得た率 [!UICONTROL traits]。

[!UICONTROL Recency] と [!UICONTROL Frequency] の設定は、サイト、セクションまたは特定のクリエイティブに対する実際の（または認識された）関心レベルに基づいて訪問者をセグメント化するのに役立ちます。例えば、高い最新性／頻度要件でセグメントの対象として認定されるユーザーは、それほど頻繁に訪問していないユーザーよりも、サイトまたは製品に関心がある可能性があります。

## 設定の場所 [!UICONTROL Recency and Frequency] {#location}

[!UICONTROL Segment Builder]では、[!UICONTROL Recency]設定と[!UICONTROL Frequency]設定は、[!UICONTROL Traits]パネルの[!UICONTROL Basic View]セクションにあります。時計アイコンをクリックして、これらのコントロールを表示します。

![](assets/recency_frequency.png)

## 制限とルール {#limitations-rules}

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

この例では、スクリーンショットに示すように、&lt;= 演算子を選択します。This qualifies your user for the [!UICONTROL segment] if they qualify for any of the three [!UICONTROL traits] a minimum of three times within the last five days. The timeline below shows the [!UICONTROL segment] qualification at the time the [!UICONTROL segment] is created, on October 1st, and ten days later.

![過去 5 日間](assets/last-5-days.png)

### 次よりも大きいか等しい演算子（=>）の使用

![次よりも大きいか等しい](assets/greater-than-equal-to.png)

この例では、スクリーンショットに示すように、=> 演算子を選択します。This qualifies your user for the [!UICONTROL segment] if they qualify for any of the three [!UICONTROL traits] a minimum of three times anytime between their first qualification on the Audience Manager platform and the cut-off time five days ago. The timeline below shows the [!UICONTROL segment] qualification at the time the [!UICONTROL segment] is created, on October 1st, and ten days later.

![より早い認定](assets/earlier-qualification.png)


## 頻度キャップの例 {#frequency-capping}

Frequency-capping expressions include all the users whose number of [!UICONTROL trait] realizations is below a desired value. 以下に、正しい例と間違った例を示します。

* Wrong - The expression `frequency([1000T]) <= 5` includes all users that have realized the [!UICONTROL trait] with the ID &quot;1000&quot; a maximum of five times but also includes users who have not realized the [!UICONTROL trait]. Therefore, Audience Manager does not validate this expression for performance reasons, as it would qualify too many users for the [!UICONTROL segment].

* Right - If you want to include all users that have realized the [!UICONTROL trait] with the ID &quot;1000&quot; a maximum of five times, add another condition to the expression, to make sure the users have qualified for the [!UICONTROL trait] at least once:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Right- When you need recency/frequency requirements to be less than a specific number of times or days, join that [!UICONTROL trait] to another with an `AND` operator. Using the example in the first bullet point, this expression becomes valid when joined with another [!UICONTROL trait] as shown here: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Right - For advertising frequency-capping use cases, you could create a [!UICONTROL segment] rule similar to this: `(frequency([1000T] <= 2D) >= 5)`. This expression includes all users that have realized the [!UICONTROL trait] with the ID &quot;1000&quot; in the past 2 days at least five times. Set frequency capping by sending this [!UICONTROL segment] to the ad server with a `NOT` set on the [!UICONTROL segment] in the ad server. この方法は、頻度キャップと同じ目的を提供しますが、[!DNL Audience Manager] でより優れたパフォーマンスを達成します。

>[!MORELIKETHIS]
>
>* [セグメントビルダーのコントロール：「Traits」セクション](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [セグメント式エディターで使用するコード構文](../../features/segments/segment-code-syntax.md)

