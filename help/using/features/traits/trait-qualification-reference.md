---
description: Audience Manager では、特性認定（特性の満足）の処理方法は特性のタイプによって異なります。特性認定について詳しくは、以下の表を参照してください。
keywords: trait qualification;特性適合;個別の特性適合;UTR;Total Trait Population;TTP
seo-description: Audience Manager では、特性認定（特性の満足）の処理方法は特性のタイプによって異なります。特性認定について詳しくは、以下の表を参照してください。
seo-title: 特性認定に関するリファレンス
solution: Audience Manager
title: 特性認定に関するリファレンス
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# 特性認定に関するリファレンス {#trait-qualification-reference}

Audience Manager では、特性認定（特性の満足）の処理方法は特性のタイプによって異なります。特性認定について詳しくは、以下の表を参照してください。

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
   <td colname="col2"> <p>特性認定は、ユーザーがブラウザーで特性について認定されるとリアルタイムで発生します。ユーザーのルールベースの特性認定は、お客様が UI で<a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits">その特性を作成してから</a>約 4 時間後に始まります。 </p> <p>ルールベースの特性では、広告頻度キャップやその他のユースケース向けに<a href="../../features/segments/recency-and-frequency.md">最新性と頻度</a>のコントロールを使用できます。 </p> </td> 
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

## Unique Trait Realizations と Total Trait Population {#unique-trait-realizations}

![](assets/utr-ttp1.png)

**[!UICONTROL Unique Trait Realizations]**&#x200B;は、様々な期間において、特性を自分のプロファイルに追加した訪問者の数を表します。

**[!UICONTROL Total Trait Population]**&#x200B;は、プロファイルにこの特性がある訪問者の数を表します。

これらの数字については次のように考えます。上の図で、[特性の詳細](../../features/traits/trait-details-page.md)ビューの「181」は、前日にプロパティを訪問したアクティブなデバイスの数を表します。[!UICONTROL Total Trait Population] は 1,595 ですが、これは現在この特性の対象として認定されているユーザーの数を表します。[!UICONTROL Total Trait Population] の数は、セグメント化／ターゲティングに使用できるユーザーの合計数を表しています。通常、ユーザーが特性の一部となっている期間は 120 日間です。

2 つの母集団の計算にはそれぞれ異なる 2 つの演算ジョブを実行しているので、[!UICONTROL Total Trait Population] は常に [!UICONTROL Unique Trait Realizations] より 24 時間遅れることになります。上のグラフでは、2 月 11 日時点での [!UICONTROL Unique Trait Realizations] は 175、[!UICONTROL Total Trait Population] は 6 となっています。次の日に、175 件のプロファイルが [!UICONTROL Total Trait Population] に加算されます。

つまり、現時点で 10,000 人の訪問者があった場合、この訪問者数は翌日の [!UICONTROL Unique Trait Realizations] に反映されますが、[!UICONTROL Total Trait Population] に反映されるのはその 24 時間後になります。

## 特性認定の上限 {#trait-qualification-limit}

各ユーザープロファイルには、それが認証済みプロファイル（[DPUUID](../../reference/ids-in-aam.md)）とデバイス ID（[UUID](../../reference/ids-in-aam.md)）のどちらであっても、150,000 の特性認定制限が適用されます。DPUUID は [!DNL Audience Manager] の特定のインスタンスに固有のものですが、UUID は [!DNL Audience Manager] プラットフォーム全体で共有されます。[!UICONTROL UUID] の場合、特性認定の保存時には公平性ポリシーが適用されます。所定のアルゴリズムにより、[!DNL Audience Manager] のすべてのインスタンスで、[!UICONTROL UUID] プロファイルの均等配分ができます。
