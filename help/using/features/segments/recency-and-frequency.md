---
description: セグメントビルダーでは、最新性と頻度を使用すると、設定された日数ごとに繰り返されるアクションに基づいて訪問者をセグメント化することができます。
seo-description: セグメントビルダーでは、最新性と頻度を使用すると、設定された日数ごとに繰り返されるアクションに基づいて訪問者をセグメント化することができます。
seo-title: 最新性と頻度
solution: Audience Manager
title: 最新性と頻度
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 最新性と頻度 {#recency-and-frequency}

[!UICONTROL Segment Builder]では、最新性と頻度を使用すると、設定された日数ごとに繰り返されるアクションに基づいて訪問者をセグメント化することができます。

Audience Manager では、[!DNL recency] と [!DNL frequency] は次のように定義されています。

* **[!UICONTROL Recency]：**&#x200B;ユーザーが 1 つ以上の特性を確認した、または特性の対象として認定された日数。
* **[!UICONTROL Frequency]：**&#x200B;ユーザーが 1 つ以上の特定を確認した、または特性の対象として認定された割合。

[!UICONTROL Recency] と [!UICONTROL Frequency] の設定は、サイト、セクションまたは特定のクリエイティブに対する実際の（または認識された）関心レベルに基づいて訪問者をセグメント化するのに役立ちます。例えば、高い最新性／頻度要件でセグメントの対象として認定されるユーザーは、それほど頻繁に訪問していないユーザーよりも、サイトまたは製品に関心がある可能性があります。

## 最新性および頻度設定の場所 {#location}

[!UICONTROL Segment Builder]では、[!UICONTROL Recency]設定と[!UICONTROL Frequency]設定は、[!UICONTROL Traits]パネルの[!UICONTROL Basic View]セクションにあります。時計アイコンをクリックして、これらのコントロールを表示します。

![](assets/recency_frequency.png)

## 制限とルール {#limitations-rules}

最新性と頻度をセグメントの特性に適用する場合は、以下の制限およびルールを確認および理解してください。

### 最新性

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
   <td colname="col1"> <p> <b>サードパーティ特性</b> </p> </td> 
   <td colname="col2"> <p>個々のサードパーティ特性またはサードパーティ特性の特性グループに対して、最新性ルールを設定することはできません。最新性と頻度は、独自の特性にのみ適用されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 頻度

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
   <td colname="col1"> <p> <b>最新性の要件</b> </p> </td> 
   <td colname="col2"> <p>最新性の要件を設定せずに、頻度の要件を設定できます。<i></i>頻度の値を設定するだけで、最新性のフィールドは空のままにします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>プロファイル結合ルール</b> </p> </td> 
   <td colname="col2"> <p><a href="../../faq/faq-profile-merge.md#trait-freq-device-rules">特性頻度、デバイスグラフ、プロファイル結合ルール</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 頻度キャップの例 {#frequency-capping}

頻度キャップ式では、特性認識の数が目標値を下回っているすべてのユーザーを含めます。以下に例を示します。

* 式 `frequency([1000T]) <= 5` の場合は、ID 「1000」の特性を認識した回数が最大 5 回（認識しなかった場合も含む）のすべてのユーザーが含まれます。
* 最新性／頻度の要件が特定の回数または日数を下回る必要がある場合は、その特性を `AND` 演算子で別の特性に結合します。前述の例を使用すると、この式は、`frequency([1000T]) <= 5 AND isSiteVisitorTrait` のように、別の特性と結合した場合に有効になります。

* 広告頻度キャップのユースケースでは、例えば次のようなセグメントルールを作成できます。`(frequency([1000T] <= 2D) >= 5)`この式では、過去 2 日間に ID 「1000」の特性を 5 回以上認識したすべてのユーザーを含めます。広告サーバーでセグメントに対して `NOT` を設定した広告サーバーにこのセグメントを送信することで、頻度キャップを設定します。この方法は、頻度キャップと同じ目的を提供しますが、[!DNL Audience Manager] でより優れたパフォーマンスを達成します。

>[!MORE_LIKE_THIS]
>
>* [セグメントビルダーのコントロール：「Traits」セクション](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [セグメント式エディターで使用するコード構文](../../features/segments/segment-code-syntax.md)

