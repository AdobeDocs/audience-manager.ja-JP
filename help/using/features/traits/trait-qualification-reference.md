---
description: Audience Manager では、特性の絞り込み（特性の満足）の処理方法は特性のタイプによって異なります。特性の絞り込みについて詳しくは、以下の表を参照してください。
keywords: 特性認定;特性適合;一意の特性適合;UTR;合計特性母集団;TTP
seo-description: Audience Manager では、特性の絞り込み（特性の満足）の処理方法は特性のタイプによって異なります。特性の絞り込みについて詳しくは、以下の表を参照してください。
seo-title: 特性認定に関するリファレンス
solution: Audience Manager
title: 特性認定に関するリファレンス
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# 特性の絞り込みに関するリファレンス {#trait-qualification-reference}

Audience Manager では、特性の絞り込み（特性の満足）の処理方法は特性のタイプによって異なります。特性の絞り込みについて詳しくは、以下の表を参照してください。

## 特性タイプ別の特性認定 {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 特性タイプ </th> 
   <th colname="col2" class="entry"> 認定条件 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ルールベースの特性 </p> </td> 
   <td colname="col2"> <p>特性認定は、ユーザーがブラウザーで特性について認定されるとリアルタイムで発生します。お客様のユーザーのルールベースの特性認定は、お客様が UI で<a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits">その特性を作成してから</a>約 4 時間後に始まります。 </p> <p>ルールベースの特性では、広告頻度キャップやその他のユースケース向けに<a href="../../features/segments/recency-and-frequency.md">最新性と頻度</a>のコントロールを使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>オンボードの特性 </p> </td> 
   <td colname="col2"> <p>特性認定は受信ファイルの処理後に発生します。つまり、受信ファイルが<a href="../../faq/faq-inbound-data-ingestion.md">Audience Manager にインポート</a>された後に特性認定が発生します。 </p> <p> オンボードの特性では、ユーザープロファイルごとの最大認定数は 1 件です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アルゴリズム特性 </p> </td> 
   <td colname="col2"> <p>アルゴリズム特性では、ユーザープロファイルごとの最大認定数は 1 件です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>フォルダー特性 </p> </td> 
   <td colname="col2"> <p>フォルダー特性では、含まれる特性の特性認定が累積します。 </p> <p>詳しくは、<a href="../../features/traits/about-folder-traits.md">フォルダー特性について</a>を参照してください。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>アクティブオーディエンス特性とデータソース同期特性 </p> </td> 
   <td colname="col2"> <p><span class="wintitle">アクティブオーディエンス</span>特性には、<span class="wintitle">Audience Manager</span> アカウントで管理下にあるすべてのデバイスが含まれています。 </p> <p><span class="wintitle">データソース同期特性</span>では、データソースに関連付けられているすべてのユーザーを追跡します。 </p> <p>詳しくは、<a href="../../features/traits/client-activity-synced-audience-traits.md">アクティブオーディエンス特性とデータソース同期特性</a>を参照してください。 </p> </td>
  </tr>
 </tbody>
</table>

## 個別の特性満足数と特性ユーザー総数 {#unique-trait-realizations}

![](assets/utr-ttp1.png)

The **[!UICONTROL Unique Trait Realizations]** count the number of your visitors that have added the trait to their profile, within different time ranges.

The **[!UICONTROL Total Trait Population]** represents the number of your visitors that have this trait on their profile.

これらの数字については次のように考えます。上の図で、「[Trait Details](../../features/traits/trait-details-page.md)」ビューの「181」は、前日にプロパティを訪問したアクティブなデバイスの数を表します。The [!UICONTROL Total Trait Population] of 1,595 represents the amount of users currently qualified for this trait. [!UICONTROL Total Trait Population] の数は、セグメント化／ターゲティングに使用できるユーザーの合計数を表しています。通常、ユーザーが特性の一部となっている期間は 120 日間です。

Because we run two different computational jobs to calculate the two populations, the [!UICONTROL Total Trait Population] always lags behind the [!UICONTROL Unique Trait Realizations] by 24 hours. In the graph above, you can see 175 [!UICONTROL Unique Trait Realizations] and a [!UICONTROL Total Trait Population] of 6 for February 11. The 175 profiles are added to the [!UICONTROL Total Trait Population] on the following day.

つまり、現時点で 10,000 人の訪問者があった場合、この訪問者数は翌日の [!UICONTROL Unique Trait Realizations] に反映されますが、[!UICONTROL Total Trait Population] に反映されるのはその 24 時間後になります。

## 特性認定の上限 {#trait-qualification-limit}

各ユーザープロファイルには、それが認証済みプロファイル（[DPUUID](../../reference/ids-in-aam.md)）とデバイス ID（[UUID](../../reference/ids-in-aam.md)）のどちらであっても、150,000 の特性認定制限が適用されます。DPUUID は [!DNL Audience Manager] の特定のインスタンスに固有のものですが、UUID は [!DNL Audience Manager] プラットフォーム全体で共有されます。[!UICONTROL UUID]ここでは、特徴的条件を保存する際に公平性ポリシーを適用します。An algorithm ensures that an equal share of the [!UICONTROL UUID] profile is made available for every instance of [!DNL Audience Manager].
