---
description: ダッシュボードを使用すると、指定した期間のパートナーのユニーク訪問者数を特性タイプおよびセグメント別に分類した情報を表示できます。
seo-description: ダッシュボードを使用すると、指定した期間のパートナーのユニーク訪問者数を特性タイプおよびセグメント別に分類した情報を表示できます。
seo-title: レポートダッシュボード
solution: Audience Manager
title: レポートダッシュボード
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 100%

---


# レポートダッシュボード {#reports-dashboard}

ダッシュボードを使用すると、指定した期間のユニーク訪問者数を特性タイプおよびセグメント別に分類した情報を表示できます。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] は[!UICONTROL Role Based Access Control]（[!UICONTROL RBAC]）を使用して、[!UICONTROL Dashboard] へのユーザーグループ権限を拡張します。ユーザーは、表示する権限のある情報のみダッシュボードで確認できます。[!UICONTROL RBAC] 機能により、社内チームが閲覧できるレポートデータを制御することができます。

例えば、様々な広告主アカウントを管理する代理店では、広告主 A のアカウントを管理するチームが広告主 B のレポートデータを閲覧できないように、ユーザーグループの権限を設定することができます。このダッシュボードは、データ配信の問題をトラブルシューティングするために使用できます。

例えば、ユニークユーザーのタイプで分類した合計ユニークユーザー数（ルールベースとオンボードの比較）の減少またはスパイクに気づいた場合、データ配信の潜在的な問題を見つけ出すためのより優れた開始点となります。合計ユニークユーザーおよびオンボードユニークユーザーの減少に気づいた場合、[!UICONTROL On-boarding Status] レポートに移動して、受信ファイルに問題があったかどうかを確認できます。

**ダッシュボードにアクセスするには：**

1. 上部のナビゲーションメニューで、「**[!UICONTROL Dashboard]**」をクリックします。
2. *（オプション）*&#x200B;最後のレポート日からの期間（7 日、14 日（デフォルト）、30 日または 60 日）をドロップダウンリストから選択します。

   選択した期間に応じて、今日までの期間と、その前の同じ日数の期間におけるオーディエンスのユニーク訪問者数の変化が [!UICONTROL Largest Traits]／[!UICONTROL Most Changed Traits] および [!UICONTROL Largest Segments]／[!UICONTROL Most Changed Segments] パネルに変動として表示されます。例えば、7 日を選択すると、差分は、今日までの 7 日間のユニーク訪問者と 7 日前までの 7 日間のユニーク訪問者を比較します。

   >[!NOTE]
   >
   >[!UICONTROL Trend]レポートを実行することで、異常に見える変動を調査できます。例えば、過去 7 日間で非常に大きな変動を確認したら、過去 14 日間（7 x 2）の[!UICONTROL Trend]レポートを実行すると、その数字をより適切に把握できる可能性があります。

   ログインしたユーザーの権限に応じて、以下のパネルが表示されます。

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Largest Traits／Most Changed Traits](../reporting/reports-dashboard.md#largest-traits)
   * [Largest Segments／Most Changed Segments](../reporting/reports-dashboard.md#most-changed-segments)

3. *（オプション）*&#x200B;グラフの上の「**[!UICONTROL Normalize]**」をクリックすると、同じスケールですべてのデータを表示できます。また、任意のデータポイントにマウスポインターを置くと、詳細情報を確認できます。

## Partner Uniques  {#partner-uniques}

表示に必要な権限は、[!UICONTROL View All Traits] です。

![](assets/partner_uniques.png)

このパネルには、指定した期間内のユニーク訪問者数が表示されます。個々の色分けされた線は、ユニーク訪問者の合計数と、アルゴリズム、ルールベースおよびオンボードの特性を使用してキャプチャされたユニーク訪問者数を表します。

>[!NOTE]
>
>ユニーク訪問者の合計数は、ルールベースまたはオンボードの特性でキャプチャされた訪問者数を表します。ただし、ユニーク訪問者の合計数は、ルールベースおよびオンボードの特性を使用してキャプチャされたユニーク訪問者数の合計とは等しくなりません。同じ個別ユーザーが、これら 2 つの特性タイプのどちらかで表されることがあります。

## Largest Traits／Most Changed Traits  {#largest-traits}

表示に必要な権限は、[!UICONTROL View Traits] です。

![](assets/largest_traits.png)

このパネルには、様々な特性によってキャプチャされたユニーク訪問者数が表示されます。

**[!UICONTROL Show]** ドロップダウンリストを使用して、特性の様々なタイプに関する情報を表示します（[!UICONTROL All Traits]、[!UICONTROL Algorithmic]、[!UICONTROL Onboarded]、または [!UICONTROL Rule-Based]）。

このパネルには、以下のタブが含まれます。

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> タブ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Largest Traits</span> </p> </td> 
   <td colname="col2"> <p>ユニーク訪問者数に関する情報を数で並べ替えて（高から低）表示します。また、指定した期間内のユニーク訪問者数の変動もリスト表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Most Changed Traits</span> </p> </td> 
   <td colname="col2"> <p>個別訪問者数に関する情報を変動で並べ替えて表示します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Largest Segments／Most Changed Segments  {#most-changed-segments}

表示に必要な権限は、[!UICONTROL View Segments] です。

![](assets/largest_segments.png)

このパネルには、様々なセグメントによってリアルタイムにキャプチャされたユニーク訪問者数が表示されます。

このパネルには、以下のタブが含まれます。

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> タブ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Largest Segments</span> </p> </td> 
   <td colname="col2"> <p>ユニーク訪問者数に関する情報と、指定した期間内のユニーク訪問者の変動を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Most Changed Segments</span> </p> </td> 
   <td colname="col2"> <p>ユニーク訪問者数に関する情報を変動で並べ替えて表示します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

