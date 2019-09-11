---
description: 個々の特性の詳細ページには、特性名、ID、パフォーマンス指標、特性を定義する式、特性が属するセグメント、特性監査ログなどの概要が表示されます。これらの詳細を表示するには、Audience Data／Traits を選択し、対象となる特性の名前をクリックします。
seo-description: 個々の特性の詳細ページには、特性名、ID、パフォーマンス指標、特性を定義する式、特性が属するセグメント、特性監査ログなどの概要が表示されます。これらの詳細を表示するには、Audience Data／Traits を選択し、対象となる特性の名前をクリックします。
seo-title: 特性の詳細ページ
solution: Audience Manager
title: 特性の詳細ページ
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# 特性の詳細ページ {#trait-details-page}

個々の特性の詳細ページには、特性名、ID、パフォーマンス指標、特性を定義する式、特性が属するセグメント、特性監査ログなどの概要が表示されます。これらの詳細を表示するには、[!UICONTROL Audience Data > Traits]を選択し、対象となる特性の名前をクリックします。

## Basic Information {#basics}

「[!UICONTROL Basic Information]」セクションには、特性の作成時に入力した必須フィールドとオプションフィールドの詳細が表示されます。特性タイプ、特性 ID、説明、データソース、その他のメタデータなどが該当します。これらの詳細情報は、特性タイプ（フォルダー、オンボード、ルールベース）によって異なります。

![](assets/basicInfo.png)

## 特性グラフ {#trait-graph}

[!UICONTROL Trait Graph]は、選択した特性のパフォーマンス指標をわかりやすく示しています。トレンドラインにカーソルを移動すると、選択した特性の追加データが表示されます。

「[!UICONTROL Unique Trait Realizations]」は、特定の期間内にこの特性をプロファイルに追加した個別ユーザーの数を表します。「[!UICONTROL Total Trait Population]」は、現在この特性について認定されている個別ユーザーの数を表します。

* ルールベースの特性の場合、特性認定は、ユーザーがブラウザーで特性に絞り込まれるときにリアルタイムにおこなわれます。
* オンボードの特性の場合、特性認定は、受信ファイルが処理された後でおこなわれます。つまり、受信ファイルが[Audience Manager に入力されたとき](../../faq/faq-inbound-data-ingestion.md)に、特性認定がおこなわれます。
* **[!UICONTROL Unique Trait Realizations]**：特定の期間にこの特性をプロファイルに追加した個別ユーザーの数。
* **[!UICONTROL Total Trait Population]**:この特性に対して現在選定されている個別ユーザーの数。

   ![特性グラフ](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**:最初の3つのエントリには、上位3つのデバイスのデータソースが表示されます。このデータソースは、特性の資格を持つ上位の3つのデバイスのデータソースを表示します。4番目のエントリには、上位3つにないクロスデバイスデータソースから、特性に修飾されるその他 [!DNL DPUUIDs] のすべての[!DNL CRM IDs]（）の合計が表示されます。このレポートは、ページの右上にあるドロップダウンメニューで [!UICONTROL Show Results By] クロスデバイスIDを選択した場合にのみ表示されます。デフォルトのドロップダウンオプションは、 [!UICONTROL Device ID]このレポートは表示されません。

   ![特性グラフ](assets/trait-identity.png)
   > [!NOTE]
   > Audience Managerでは、特性に対応するクロスデバイスIDがある場合に [!UICONTROL Identity Type Breakdown] のみレポートが表示されます。

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=jpn)

## 特性式 {#trait-expression}

「[!UICONTROL Trait Expression]」セクションには、ユーザーが特性について認定されるために満たさなければならない条件が表示されます。これらのルールは、[特性を作成または編集](../../features/traits/about-trait-builder.md)するときに設定されます。

![](assets/traitExpression.png)

## 特性セグメント {#trait-segments}

「[!UICONTROL Segments with this Trait]」セクションには、選択した特性が属するすべてのセグメントのリストが表示されます。セグメント名をクリックすると、そのセグメントの詳細が表示されます。

![](assets/traitSegments.png)

## 特性監査／履歴ログ {#trait-audit-history}

「[!UICONTROL Trait Expression Change History]」には、ルールベースの特性とオンボードの特性について、特性の式ルールに対する直近 10 件の変更と、その変更をおこなったユーザーが表示されます。特性に対する変更が 10 件を超える場合、「**[!UICONTROL Export to CSV]**」をクリックすると監査ログ全体をダウンロードできます。フォルダー特性やアルゴリズム特性では、監査ログは使用できません。

>[!NOTE]
>
>[!UICONTROL By User] 列に「[!UICONTROL Not Available]」と表示される場合、そのユーザーのアカウントが削除されていることを表します。

![](assets/traitHistory.png)