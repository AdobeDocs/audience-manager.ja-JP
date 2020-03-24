---
description: Audience Manager では、特性認定（特性の満足）の処理方法は特性のタイプによって異なります。特性認定について詳しくは、以下の表を参照してください。
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: Audience Manager では、特性認定（特性の満足）の処理方法は特性のタイプによって異なります。特性認定について詳しくは、以下の表を参照してください。
seo-title: 特性認定に関するリファレンス
solution: Audience Manager
title: 特性認定に関するリファレンス
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 40ac91af26ed4a95492dde872288dc2e9059cdf9

---


# 特性認定に関するリファレンス {#trait-qualification-reference}

Audience Manager では、特性認定（特性の満足）の処理方法は特性のタイプによって異なります。特性認定について詳しくは、以下の表を参照してください。

## 特性タイプ別の特性認定 {#trait-type}

| 特性タイプ | 資格条件 |
|---|---|
| ルールベースの特性 | 特性認定は、ユーザーがブラウザーで特性について認定されるとリアルタイムで発生します。ユーザーのルールベースの特性認定は、お客様が UI で[その特性を作成してから](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)約 4 時間後に始まります。ルールベースの特性では、広告頻度キャップやその他のユースケース向けに[最新性と頻度](../segments/recency-and-frequency.md)のコントロールを使用できます。 |
| オンボードの特性 | 特性認定は受信ファイルの処理後に発生します。つまり、受信ファイルが[Audience Manager にインポート](../../faq/faq-inbound-data-ingestion.md)された後に特性認定が発生します。オンボードの特性を作成してから受信ファイルをアップロードして処理するまでに、約 4 時間待つ必要があります。オンボードの特性では、ユーザープロファイルごとの最大認定数は 1 件です。 |
| アルゴリズム特性 | アルゴリズム特性では、ユーザープロファイルごとの最大認定数は 1 件です。 |
| フォルダー特性 | フォルダー特性では、含まれる特性の特性認定が累積します。Read [Folder Traits: About](about-folder-traits.md) for more information. |
| アクティブオーディエンス特性とデータソース同期特性 | An [!UICONTROL Active Audience] trait contains all of the devices under management in your Audience Manager account. [!UICONTROL Data Source Synced Traits] は、データソースと関連付けられているすべてのユーザーを追跡します。詳しくは、[アクティブオーディエンス特性とデータソース同期特性](client-activity-synced-audience-traits.md)を参照してください。 |

## Unique Trait Realizations と Total Trait Population {#unique-trait-realizations}

![独特形質実現](assets/trait-graph.png)

[!UICONTROL Unique Trait Realizations]は、様々な期間において、特性を自分のプロファイルに追加した訪問者の数を表します。

[!UICONTROL Total Trait Population]は、プロファイルにこの特性がある訪問者の数を表します。

これらの数字については次のように考えます。上の図で、[特性の詳細](../../features/traits/trait-details-page.md)ビューの「90,173」は、前日にプロパティを訪問したアクティブなデバイスの数を表します。[!UICONTROL Total Trait Population] は 55,757 ですが、これは現在この特性の対象として認定されているユーザーの数を表します。[!UICONTROL Total Trait Population] の数は、セグメント化／ターゲティングに使用できるユーザーの合計数を表しています。通常、ユーザーが特性の一部となっている期間は 120 日間です。

2 つの母集団の計算にはそれぞれ異なる 2 つの演算ジョブを実行しているので、[!UICONTROL Total Trait Population] は常に [!UICONTROL Unique Trait Realizations] より 24 時間遅れることになります。In the graph above, you can see about 90,400 [!UICONTROL Unique Trait Realizations] and a [!UICONTROL Total Trait Population] of about 90,300 for February 5th. 次の日に、90,400 件のプロファイルが [!UICONTROL Total Trait Population] に加算されます。

つまり、現時点で 10,000 人の訪問者があった場合、この訪問者数は翌日の [!UICONTROL Unique Trait Realizations] に反映されますが、[!UICONTROL Total Trait Population] に反映されるのはその 24 時間後になります。

特性の配分の変更は、セグメントの母集団に反映されます。

## リアルタイムセグメントの訪問者数と合計セグメントの訪問者数 {#real-time-segment}

![独特形質実現](assets/segment-graph.png)

選択し [!UICONTROL Real-time Segment Population] たセグメントに対して資格を持ち、プロパティに達したデバイスの数を、選択した時間間隔内にカウントします。

選択し [!UICONTROL Total Segment Population] た期間内に、選択したセグメントに対して資格を持つデバイスの数をカウントします。 このレ [!UICONTROL 1 Day] ポートは、最新のセグメント訪問者数を表します。

これらの数字については次のように考えます。上の図で、 [セグメ [ントの詳細](../../features/segments/segment-summary-view.md) ]ビューの9,993は、昨日プロパティを訪問し、セグメントの資格を得たアクティブなデバイスの数を表します。 699,532 [!UICONTROL Total Segment Population] の数値は、このセグメントに対して現在認定されているデバイスの合計数を表します。 The [!UICONTROL Total Segment Population] figure is meant to show the total number of devices that could be used for segmentation/targeting.

2 つの母集団の計算にはそれぞれ異なる 2 つの演算ジョブを実行しているので、[!UICONTROL Total Segment Population] は常に [!UICONTROL Real-time Segment Population] より 24 時間遅れることになります。In the graph above, you can see a 8,116 [!UICONTROL Real-time Segment Population] and a [!UICONTROL Total Segment Population] of 742,000 for February 2nd. 次の日に、8,116 件のプロファイルが [!UICONTROL Total Segment Population] に加算されます。

つまり、現時点で 10,000 人の訪問者があった場合、この訪問者数は翌日の [!UICONTROL Real-time Segment Population] に反映されますが、[!UICONTROL Total Segment Population] に反映されるのはその 24 時間後になります。

## 特性認定の上限 {#trait-qualification-limit}

各ユーザープロファイルには、それが認証済みプロファイル（[DPUUID](../../reference/ids-in-aam.md)）とデバイス ID（[UUID](../../reference/ids-in-aam.md)）のどちらであっても、150,000 の特性認定制限が適用されます。DPUUID は [!DNL Audience Manager] の特定のインスタンスに固有のものですが、UUID は [!DNL Audience Manager] プラットフォーム全体で共有されます。[!UICONTROL UUID] の場合、特性認定の保存時には公平性ポリシーが適用されます。所定のアルゴリズムにより、[!DNL Audience Manager] のすべてのインスタンスで、[!UICONTROL UUID] プロファイルの均等配分ができます。
