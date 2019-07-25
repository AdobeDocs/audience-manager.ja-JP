---
description: ダッシュボードを使用すると、指定した期間のパートナーの個別訪問者数を特性タイプおよびセグメント別に分類した情報を表示できます。
seo-description: ダッシュボードを使用すると、指定した期間のパートナーの個別訪問者数を特性タイプおよびセグメント別に分類した情報を表示できます。
seo-title: レポートダッシュボード
solution: Audience Manager
title: レポートダッシュボード
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# レポートダッシュボード {#reports-dashboard}

ダッシュボードを使用すると、指定した期間の個別訪問者数を特性タイプおよびセグメント別に分類した情報を表示できます。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] を使用 [!UICONTROL Role Based Access Control][!UICONTROL RBAC]して、ユーザーグループ権限を拡張 [!UICONTROL Dashboard]します。ユーザーは、表示する権限のある情報のみダッシュボードで確認できます。[!UICONTROL RBAC] 機能により、社内チームが閲覧できるレポートデータを制御することができます。

例えば、様々な広告主アカウントを管理する代理店では、広告主 A のアカウントを管理するチームが広告主 B のレポートデータを閲覧できないように、ユーザーグループの権限を設定することができます。このダッシュボードは、データ配信の問題をトラブルシューティングするために使用できます。

例えば、個別ユーザーのタイプを分類する個別ユーザー（ルールベースとオンボーディング）の分類を持つ下降またはスパイクがある場合、潜在的なデータ配信の問題をトラッキングするためのより良い足がかりとなります。If you notice a dip in total unique users and in on-boarded unique users, you can go to the [!UICONTROL On-boarding Status] report to see if there was an issue with an inbound file.

**ダッシュボードにアクセスするには：**

1. 上部のナビゲーションメニューで、「**[!UICONTROL Dashboard]**」をクリックします。
2. *（オプション* ）ドロップダウンリストからの目的の期間（"7日間」、"14日間（デフォルト）」、"30日間」または"60日間」）から目的の期間を選択します。

   Depending on the period selected, the delta change in the [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] and [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] panels displays the change in unique visitors in the audience over the period ending today vs. the prior period of the same length. 例えば、7 日を選択すると、差分は、今日までの 7 日間の個別訪問者と 7 日前までの 7 日間の個別訪問者を比較します。

   >[!NOTE]
   >
   >You can investigate a delta change that seems out of the ordinary by running a [!UICONTROL Trend] report. For example, if you see an unusually large delta change during the last seven days, you could run a [!UICONTROL Trend] report for the last 14 days (2 x 7) to better understand the numbers.

   ログインしたユーザーの権限に応じて、以下のパネルが表示されます。

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Largest Traits／Most Changed Traits](../reporting/reports-dashboard.md#largest-traits)
   * [Largest Segments／Most Changed Segments](../reporting/reports-dashboard.md#most-changed-segments)

3. *すべてのグラフの上にあるオプション* をクリック **[!UICONTROL Normalize]** すると、すべてのデータが同じスケールに表示されます。また、任意のデータポイントにマウスポインターを置くと、詳細情報を確認できます。

## Partner Uniques {#partner-uniques}

Permission Required to View: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

このパネルには、指定した期間内の個別訪問者数が表示されます。個々の色分けされた線は、個別訪問者の合計数と、アルゴリズム、ルールベースおよびオンボードの特性を使用してキャプチャされた個別訪問者数を表します。

>[!NOTE]
>
>個別訪問者数の合計は、ルールベースまたは訪問時の特性を通してキャプチャされた訪問者を表します。ただし、個別訪問者の合計数は、ルールベースおよびオンボードの特性を使用してキャプチャされた個別訪問者数の合計とは等しくなりません。同じ個別ユーザーが、これら 2 つの特性タイプのどちらかで表されることがあります。

## Largest Traits／Most Changed Traits {#largest-traits}

Permission Required to View: [!UICONTROL View Traits].

![](assets/largest_traits.png)

このパネルには、様々な特性によってキャプチャされた個別訪問者数が表示されます。

**[!UICONTROL Show]** ドロップダウンリストを使用して、様々なタイプの特性に関する情報を表示します。 [!UICONTROL All Traits][!UICONTROL Algorithmic][!UICONTROL Onboarded][!UICONTROL Rule-Based]、または.

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
   <td colname="col2"> <p>個別訪問者数に関する情報を数で並べ替えて（高から低）表示します。また、指定した期間内の個別訪問者数の変動もリスト表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Most Changed Traits</span> </p> </td> 
   <td colname="col2"> <p>個別訪問者数に関する情報を変動で並べ替えて表示します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Largest Segments／Most Changed Segments {#most-changed-segments}

Permission Required to View: [!UICONTROL View Segments].

![](assets/largest_segments.png)

このパネルには、様々なセグメントによってリアルタイムにキャプチャされた個別訪問者数が表示されます。

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
   <td colname="col2"> <p>個別訪問者数に関する情報と、指定した期間内の個別訪問者の変動を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Most Changed Segments</span> </p> </td> 
   <td colname="col2"> <p>個別訪問者数に関する情報を変動で並べ替えて表示します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

