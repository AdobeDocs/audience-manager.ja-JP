---
description: 個々の特性の詳細ページには、特性名、ID、パフォーマンス指標、特性を定義する式、特性が属するセグメント、特性監査ログなどの概要が表示されます。これらの詳細を表示するには、Audience Data／Traits を選択し、対象となる特性の名前をクリックします。
seo-description: 個々の特性の詳細ページには、特性名、ID、パフォーマンス指標、特性を定義する式、特性が属するセグメント、特性監査ログなどの概要が表示されます。これらの詳細を表示するには、Audience Data／Traits を選択し、対象となる特性の名前をクリックします。
seo-title: 特性の詳細ページ
solution: Audience Manager
title: 特性の詳細ページ
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# 特性の詳細ページ {#trait-details-page}

個々の特性の詳細ページには、特性名、ID、パフォーマンス指標、特性を定義する式、特性が属するセグメント、特性監査ログなど、特性の詳細の概要が表示されます。To view these details, go to **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** and click the name of the trait you want to work with.

## 特性管理ツール {#trait-management-tools}

特性の詳細ページの上部に、特性を管理するために使用できるツールがあります。

1. **[!UICONTROL Add New]**：このオプションを使用して、新しいルールベース特性、アルゴリズム特性またはオンボード済み特性を作成します。
2. **[!UICONTROL Edit]**：このオプションを使用して、現在の特性の設定を変更します。
3. **[!UICONTROL Delete]**：このオプションを使用して、Audience Manager アカウントから現在の特性を削除します。
4. **[!UICONTROL Marketplace Recommendations]**：このオプションを使用して、購読していない [!UICONTROL Audience Marketplace] データフィードから、表示している特性に類似した特性を見つけます。Marketplace へのナビゲート方法および類似した特性を見つける方法について詳しくは、[データ購入者向けの Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) を参照してください。

![basic-trait-information](assets/basic-trait-information.png)

## 特性情報 {#basics}

「[!UICONTROL Trait Information]」セクションには、特性の作成時に入力した必須フィールドとオプションフィールドの詳細が表示されます。特性タイプ、特性 ID、説明、データソース、その他のメタデータなどが該当します。これらの詳細情報は、特性タイプ（フォルダー、オンボード、ルールベース）によって異なります。

## Trait Graph {#trait-graph}

[!UICONTROL Trait Graph]は、選択した特性のパフォーマンス指標をわかりやすく示しています。トレンドラインにカーソルを移動すると、選択した特性の追加データが表示されます。

「[!UICONTROL Unique Trait Realizations]」は、特定の期間内にこの特性をプロファイルに追加した個別ユーザーの数を表します。「[!UICONTROL Total Trait Population]」は、現在この特性について認定されている個別ユーザーの数を表します。

* ルールベースの特性の場合、特性認定は、ユーザーがブラウザーで特性に絞り込まれるときにリアルタイムにおこなわれます。
* オンボードの特性の場合、特性認定は、受信ファイルが処理された後でおこなわれます。つまり、受信ファイルが[Audience Manager に入力されたとき](../../faq/faq-inbound-data-ingestion.md)に、特性認定がおこなわれます。
* **[!UICONTROL Unique Trait Realizations]**：特定の期間にこの特性をプロファイルに追加した個別ユーザーの数。
* **[!UICONTROL Total Trait Population]**：現在この特性で絞り込まれている個別ユーザーの数。

   ![trait-graph](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**：最初の 3 つのエントリには、特性に適合する母集団が最も大きい、上位 3 つのクロスデバイスデータソースが降順に表示されます。4 番目のエントリには、上位 3 つにないクロスデバイスデータソースから、特性に適合するその他すべての [!DNL DPUUIDs] （[!DNL CRM IDs]）の合計が表示されます。このレポートは、ページの右上にある [!UICONTROL Show Results By] ドロップダウンメニューでクロスデバイスIDを選択した場合にのみ表示されます。デフォルトのドロップダウンオプションは [!UICONTROL Device ID] で、このレポートは表示されません。

   ![trait-graph](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager では、特性に適合するクロスデバイス ID がある場合に [!UICONTROL Identity Type Breakdown] のみレポートが表示されます。

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## Trait Expression {#trait-expression}

「[!UICONTROL Trait Expression]」セクションには、ユーザーが特性について認定されるために満たさなければならない条件が表示されます。これらのルールは、[特性を作成または編集](../../features/traits/about-trait-builder.md)するときに設定されます。

![](assets/traitExpression.png)

## 特性セグメント {#trait-segments}

「[!UICONTROL Segments with this Trait]」セクションには、選択した特性が属するすべてのセグメントのリストが表示されます。セグメント名をクリックすると、そのセグメントの詳細が表示されます。

![](assets/traitSegments.png)

## 特性監査／履歴ログ {#trait-audit-history}

「[!UICONTROL Trait Expression Change History]」には、ルールベースの特性とオンボードの特性について、特性の式ルールに対する直近 10 件の変更と、その変更をおこなったユーザーが表示されます。特性に対する変更が 10 件を超える場合、**[!UICONTROL Export to CSV]**&#x200B;をクリックすると監査ログ全体をダウンロードできます。フォルダー特性やアルゴリズム特性では、監査ログは使用できません。

>[!NOTE]
>
>[!UICONTROL By User] 列に「[!UICONTROL Not Available]」と表示される場合、そのユーザーのアカウントが削除されていることを表します。

![](assets/traitHistory.png)