---
description: すべてのファーストパーティおよびサードパーティ特性で共有される個別ユーザーの数に関するデータを返します。
seo-description: すべてのファーストパーティおよびサードパーティ特性で共有される個別ユーザーの数に関するデータを返します。
seo-title: 特性間重複レポート
solution: Audience Manager
title: 特性間重複レポート
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
translation-type: tm+mt
source-git-commit: c05541df2d0dfc8753b06eaa8f2baee9bc6c2a16

---


# 特性間重複レポート{#trait-to-trait-overlap-report}

すべてのファーストパーティおよびサードパーティ特性で共有される個別ユーザーの数に関するデータを返します。

>[!NOTE]
>
>Audience Manager の重複レポートは、RBAC の原則に従います。自分が属している [RBAC ユーザーグループ](/help/using/features/administration/administration-overview.md) に基づき、自分がアクセスできるデータソースからの特性のみを確認できます。

<!-- 

c_overlap_reports.xml

 -->

## 概要

[!UICONTROL Trait-to-Trait Overlap]レポートは、すべての独自特性とサードパーティ特性の間で共有される個別ユーザーの割合に関するデータを返します。最適化ツールとして、このレポートは以下に役立ちます。

* ニーズに応じて、重複の多いまたは少ないセグメントを作成する。重複の多い特性は、ターゲット設定されたオーディエンスを提供しますが、個別訪問者は少なくなります。重複の少ない特性は、より多数の個別訪問者にリーチするうえで役に立つ可能性があります。
* サードパーティ特性データを検証する。類似するファーストパーティ特性とサードパーティ特性の間の重複が非常に多い場合は、データパートナーからの特性が正確で信頼できるものであることを示します。反対に、重複が少ない場合は、サードパーティ特性が、類似するファーストパーティ特性と同じ情報を実際には含んでいない可能性があることを示唆します。
* 特性間の予期しない重複を検出し、その情報を使用して革新的なセグメントを作成する。

## レポートのサンプル

次の図は、[!UICONTROL Trait-to-Trait Overlap]レポートの要素の概要を示しています。

>[!NOTE]
>
>[!UICONTROL Trait-to-Trait Overlap]レポートは、同じ特性同士を比較すると、空のフィールドを返します。

![](assets/trait-to-trait-overlap.png)

## 個々のデータポイントの詳細

個々の点を選択すると、データの詳細がポップアップウィンドウに表示されます。クリック操作で、レポートに表示されるデータが自動的に更新されます。

## 特性間重複データポップフィールドの定義 {#field-definitions}

個別のデータポイントをクリックしたときにポップアップウィンドウに表示される指標について説明します。

<!-- 

r_t2t_data_pop.xml

 -->

[!UICONTROL Trait-to-Trait Overlap]レポートのポップアップには、以下の指標が含まれています。この表の個別訪問者数指標は、*リアルタイムユーザー数*&#x200B;を表していることに注意してください。

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlap %</span></b> </td> 
   <td colname="col2"> 比較対象の特性間での個別重複率（「Overlap Uniques」/「Trait Uniques」）を表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> データソースタイプ</span></b> </td> 
   <td colname="col2">特性が属するデータソースのタイプを定義します。 次のいずれかになります。 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">First-party（自分の特性）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Third-party（外部のデータパートナー／ベンダー）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重複する特性ID</span></b> </td> 
   <td colname="col2"> 重複する特性の一意の数値ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重複する特性名</span></b> </td> 
   <td colname="col2"> 重複する特性の名前。 </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 特性ID 2</span></b> </td> 
   <td colname="col2"> ベースデータソース内の特性の一意の数値ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特性名2</span></b> </td> 
   <td colname="col2"> ベースデータソース内の特性の名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlap Uniques</span></b> </td> 
   <td colname="col2"> <p>重複率を取得するために、Audience Manager は次の数式を使用します。</p> <p>重複する固有数/（基本特性固有数+重複する特性固有 — 重複する固有数）</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重複する特性固有</span></b> </td> 
   <td colname="col2"> 重なり合う特性からの個別訪問者数。 </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 基本特性固有</span></b> </td> 
   <td colname="col2"> 基本特性からの個別訪問者数。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [データスライダーを使用したレポート結果のフィルタリング](../../reporting/dynamic-reports/data-sliders.md)
>* [動的レポートで使用される図形、色、サイズ](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [レポートのアイコンとツールの説明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重複レポート：更新スケジュールと最小セグメントサイズ](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [選択した Audience Manager レポートでのデータサンプリングとエラー率...](../../reporting/report-sampling.md)
>* [重複レポートの CSV ファイル](../../reporting/dynamic-reports/overlap-csv-files.md)