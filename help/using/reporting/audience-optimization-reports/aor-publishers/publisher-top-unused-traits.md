---
description: 上位の未使用特性は、まだセグメントのメンバーになっていない特性を、特性タイプ、データソース、パフォーマンスに基づいて散布図として表したものです。
seo-description: 上位の未使用特性は、まだセグメントのメンバーになっていない特性を、特性タイプ、データソース、パフォーマンスに基づいて散布図として表したものです。
seo-title: 上位の未使用特性
solution: Audience Manager
title: 上位の未使用特性
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 100%

---


# 上位の未使用特性 {#top-unused-traits}

上位の未使用特性は、まだセグメントのメンバーになっていない特性を、特性タイプ、データソース、パフォーマンスに基づいて散布図として表したものです。

## ユースケース {#use-cases}

[!UICONTROL Top Unused Traits]レポートを使用すると、現在セグメントにマッピングされていないファーストパーティ特性とサードパーティ特性のパフォーマンスを分析および比較することができます。このビューから、キャンペーン最適化またはまったく新しいビジネスチャンスのためにオーディエンスセグメントで使用するのに最適な特性を指摘することができます。

## 上位の未使用特性レポートの使用  {#using-the-report}

「**[!UICONTROL Data Provider Type]**」コントロールを使用して、ファーストパーティ特性とサードパーティ特性を切り替えます。「**[!UICONTROL All]**」を選択すると、ファーストパーティ特性とサードパーティ特性がレポートに表示されます。

**[!UICONTROL Impressions]** スライダーでは、返されるインプレッション数の最小値と最大値を選択できます。設定した限度を下回るまたは上回る原因となっている特性は、レポートに表示されません。

**[!UICONTROL Day Range]** コントロールと **[!UICONTROL Date Through]** コントロールを使用して、ルックバック範囲を調整します。このレポートには 30 日間のルックバック期間のみ使用できることに注意してください。

「**[!UICONTROL Order]**」ドロップダウンボックスを使用して、情報を求めている、ポートフォリオ内の Web プロパティを選択します。

「**[!UICONTROL Data Provider]**」ドロップダウンボックスで、レポートに表示する特性が含まれているデータソースを選択します。

「**[!UICONTROL Traits]**」ドロップダウンボックスを使用して、レポートに表示する特性を選択します。

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers] を有効にする際には、[Google Ad Manager（旧称 DFP）データファイルを Audience Manager に読み込む](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)の手順 3 に記載されているように、[!UICONTROL Order IDs] の記述メタデータを含める必要があります。これにより、Web プロパティの詳細が[!UICONTROL Order ID] ではなく[!UICONTROL Order]として表示されるようになります。

## 結果の解釈 {#interpreting-results}

**レポートのサンプル**

[!UICONTROL Top Unused Traits]レポートは次のようになります。レポート内でバブルをクリックすると、基になっているデータが表示されます。

追加情報については、サンプルレポートの下の表を参照してください。

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Data Provider Type</span> </p> </td> 
   <td colname="col2"> <p>選択したデータソースにファーストパーティ特性とサードパーティ特性のどちらが含まれているかを指定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Trait ID</span> </p> </td> 
   <td colname="col2"> <p>この特性の一意な ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Trait Name</span> </p> </td> 
   <td colname="col2"> <p>お客様またはデータプロバイダーによってこの特性に割り当てられた名前（英数字）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Order</span> </p> </td> 
   <td colname="col2"> <p>このレポートの対象となっている Web プロパティ。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>この特性のメンバーにインベントリが表示された回数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Trait Uniques</span> </p> </td> 
   <td colname="col2"> <p>過去 30 日間の特性メンバーの数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

レポートにおける特性の位置で、既存のオーディエンスセグメントの最適化に使用できる特性について多くのことがわかります。

Impressions 軸に関して高い位置にある特性は、キャンペーンで使用できる特性になります。インプレッション数が少ない特性の場合は、[!DNL Google Ad Manager] データに基づき、Web プロパティでこのオーディエンスにリーチする可能性は低くなります。

「[!UICONTROL Unique Trait Realizations]」軸の左側に行くほど正確な特性になり、右側に行くほどスケールを促進できる特性になります。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 配置の意味 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上</b> </p> </td> 
   <td colname="col2"> <p>インプレッション数が多く、特性適合回数が少ない。 </p> <p>これは、まだセグメントのメンバーでない非常に正確なオーディエンスです。ターゲティングの対象として検討してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下</b> </p> </td> 
   <td colname="col2"> <p>インプレッション数が少なく、特性適合回数が少ない。 </p> <p> これらの特性は、Web プロパティに対するインプレッション数に貢献していないので、除外します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上</b> </p> </td> 
   <td colname="col2"> <p>インプレッション数が多く、特性適合回数が多い。 </p> <p>まだセグメントに表されていないオーディエンスに対するリーチが高くなります。このオーディエンスは、インプレッション数が多くスケールが大きいので、ターゲティングの第一の候補になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下</b> </p> </td> 
   <td colname="col2"> <p>インプレッション数が低く、特性適合回数が多い。 </p> <p> これらの特性は、Web プロパティに対するインプレッション数に貢献していないので、除外できます。 </p> </td> 
  </tr> 
 </tbody> 
</table>
