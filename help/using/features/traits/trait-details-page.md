---
description: 個別の特性の詳細ページは、特性名、ID、パフォーマンス指標、特性を定義する式、属するセグメントおよび特性監査ログなどの、情報の概要を提供します。これらの詳細を表示するには、Audience Data／Traits を選択し、対象となる特性の名前をクリックします。
seo-description: 個別の特性の詳細ページは、特性名、ID、パフォーマンス指標、特性を定義する式、属するセグメントおよび特性監査ログなどの、情報の概要を提供します。これらの詳細を表示するには、Audience Data／Traits を選択し、対象となる特性の名前をクリックします。
seo-title: 特性の詳細ページ
solution: Audience Manager
title: 特性の詳細ページ
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# 特性の詳細ページ {#trait-details-page}

個々の特性の詳細ページには、特性名、ID、パフォーマンス指標、特性を定義する式、特性が属するセグメント、特性監査ログなどの概要が表示されます。To vew these details, go to [!UICONTROL Audience Data > Traits] and click the name of the trait you want to work with.

## Basic Information {#basics}

「[!UICONTROL Basic Information]」セクションには、特性の作成時に入力した必須フィールドとオプションフィールドの詳細が表示されます。特性タイプ、特性ID、説明、データソースなどのメタデータが含まれます。これらの詳細情報は、特性タイプ（フォルダー、オンボード、ルールベース）によって異なります。

![](assets/basicInfo.png)

## 特性グラフ {#trait-graph}

The [!UICONTROL Trait Graph] provides at-a-glance performance metrics for your selected trait. トレンドラインにカーソルを移動すると、選択した特性の追加データが表示されます。

「[!UICONTROL Unique Trait Realizations]」は、特定の期間内にこの特性をプロファイルに追加した個別ユーザーの数を表します。The [!UICONTROL Total Trait Population] indicates the number of unique users currently qualified for this trait.

* ルールベースの特性の場合、特性の絞り込みは、ユーザーがブラウザーで特性に絞り込まれるときにリアルタイムにおこなわれます。
* オンボードの特性の場合、特性の絞り込みは、受信ファイルが処理された後でおこなわれます。つまり、受信ファイルが[Audience Manager に入力されたとき](../../faq/faq-inbound-data-ingestion.md)に、特性の絞り込みがおこなわれます。
* **ユニーク特性再分析**:特定の期間にこの特性をプロファイルに追加した個別ユーザーの数。
* **特性母集団の合計**:この特性に対して現在選定されている個別ユーザーの数。

![](assets/traitGraph.png)

## 特性式 {#trait-expression}

「[!UICONTROL Trait Expression]」セクションには、ユーザーが特性について認定されるために満たさなければならない条件が表示されます。These rules are set when you [create or edit a trait](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## 特性セグメント {#trait-segments}

[!UICONTROL Segments with this Trait] このセクションでは、選択した特性が属するすべてのセグメントを一覧表示します。セグメント名をクリックすると、そのセグメントの詳細が表示されます。

![](assets/traitSegments.png)

## 特性監査／履歴ログ {#trait-audit-history}

「[!UICONTROL Trait Expression Change History]」には、ルールベースの特性とオンボードの特性について、特性の式ルールに対する直近 10 件の変更と、その変更をおこなったユーザーが表示されます。特性に対する変更が 10 件を超える場合、「**[!UICONTROL Export to CSV]**」をクリックすると監査ログ全体をダウンロードできます。フォルダー特性やアルゴリズム特性では、監査ログは使用できません。

>[!NOTE]
>
>[!UICONTROL Not Available] という [!UICONTROL By User] 列は、そのユーザーのアカウントが削除されたことを意味します。

![](assets/traitHistory.png)