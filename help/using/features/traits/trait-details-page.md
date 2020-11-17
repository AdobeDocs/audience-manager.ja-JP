---
description: 個々の特性の詳細ページには、特性名、ID、パフォーマンス指標、特性を定義する式、特性が属するセグメント、特性監査ログなどの概要が表示されます。これらの詳細を表示するには、Audience Data／Traits を選択し、対象となる特性の名前をクリックします。
seo-description: 個々の特性の詳細ページには、特性名、ID、パフォーマンス指標、特性を定義する式、特性が属するセグメント、特性監査ログなどの概要が表示されます。これらの詳細を表示するには、Audience Data／Traits を選択し、対象となる特性の名前をクリックします。
seo-title: 特性の詳細ページ
solution: Audience Manager
title: 特性の詳細ページ
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 27%

---


# [!UICONTROL Trait] 詳細ページ {#trait-details-page}

The details page for an individual [!UICONTROL trait] provides an overview of the [!UICONTROL trait] details, such as the [!UICONTROL trait] name, ID, performance metrics, expressions that define the [!UICONTROL trait], segments it belongs to, and the [!UICONTROL trait] audit log. To view these details, go to **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** and click the name of the [!UICONTROL trait] you want to work with.

## [!UICONTROL Trait] 管理ツール {#trait-management-tools}

The top of the [!UICONTROL trait] details page hosts the tools that you can use to manage your [!UICONTROL traits]:

1. **[!UICONTROL Add New]**:このオプションを使用して、新規 [!UICONTROL rule-based]、 [!UICONTROL algorithmic]またはを作成し [!UICONTROL onboarded traits]ます。
2. **[!UICONTROL Edit]**:現在の設定を変更するには、このオプションを使用し [!UICONTROL trait]ます。
3. **[!UICONTROL Delete]**:このオプションを使用して、Audience Managerアカウント [!UICONTROL trait] から現在のを削除します。
4. **[!UICONTROL Marketplace Recommendations]**:このオプションは、登録され [!UICONTROL traits] ていないデータ料金から、表示している [!UICONTROL Audience Marketplace] ものと同様に使用できます。  へのナビゲート方法および類似した特性を見つける方法について詳しくは、[データ購入者向けの Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) を参照してください。[!UICONTROL Marketplace]

![basic-trait-information](assets/basic-trait-information.png)

## [!UICONTROL Trait] 情報 {#basics}

The [!UICONTROL Trait Information] section shows details about required and optional fields you completed when building the [!UICONTROL trait]. 例えば、 [!UICONTROL trait] タイプ、 [!UICONTROL trait] ID、説明、その他のメタデータ [!UICONTROL data source]が含まれます。 これらの詳細は、 [!UICONTROL trait] タイプ([!UICONTROL folder]、 [!UICONTROL onboarded]または [!UICONTROL rule-based])によって異なります。

## [!UICONTROL Trait Graph] {#trait-graph}

The [!UICONTROL Trait Graph] provides at-a-glance performance metrics for your selected [!UICONTROL trait]. Hold your cursor over a trend line to see additional data for the selected [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] は、特定の期間にこれをプロファイル [!UICONTROL trait] に追加した個別ユーザーの数を表します。 The [!UICONTROL Total Trait Population] indicates the number of unique users currently qualified for this [!UICONTROL trait].

For [!UICONTROL rule-based traits], [!UICONTROL trait] qualification happens in real-time, as users qualify for a [!UICONTROL trait] in their browser.

例え [!UICONTROL onboarded traits]ば、受信ファイルの処理後に認定が行われます。つまり、受信ファイルがAudience Managerに [!UICONTROL trait] 送られ、認定が行われるとき [](../../faq/faq-inbound-data-ingestion.md)[!UICONTROL trait] 。

に次の情報 [!UICONTROL Trait Graph] が表示されます。

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**:認証済みプロファイルのデータを収集してい [!UICONTROL traits] る対象の結果を表示するには、このオプションを選択します。 このオプションを選択すると、レポートにはデータのみが表示され、 [!UICONTROL Cross-Device ID] レポートにはデータは表示されません [!UICONTROL Device ID] 。
   * **[!UICONTROL Device ID]**:デバイスプロファイルのデータを収集してい [!UICONTROL traits] る対象の結果を表示するには、このオプションを選択します。 このオプションを選択すると、レポートにはデータのみが表示され、 [!UICONTROL Device ID] レポートにはデータは表示されません [!UICONTROL Cross-Device ID] 。

      ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**:特定の期間にこれをプロファイル [!UICONTROL trait] に追加した個別ユーザーの数です。
* **[!UICONTROL Total Trait Population]**:現在この条件を満たす個別ユーザーの数 [!UICONTROL trait]。

* **[!UICONTROL Identity Type Breakdown]**:最初の3つのエントリは、その条件を満たす訪問者数 [!UICONTROL cross-device data sources] が最も多い上位3つを降順 [!UICONTROL trait]で示します。 The fourth entry shows the sum of all the other [!DNL DPUUIDs] ([!DNL CRM IDs]) that qualified for the [!UICONTROL trait], from the [!UICONTROL cross-device data sources] that are not in the top three. This report appears only if you select [!UICONTROL Cross-device ID] in the [!UICONTROL Show Results By] drop-down menu at the top right side of the page. デフォルトのドロップダウンオプションは [!UICONTROL Device ID] で、このレポートは表示されません。

   ![trait-graph](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager only displays the [!UICONTROL Identity Type Breakdown] report if you have [!UICONTROL cross-device] IDs qualified for the [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] 式 {#trait-expression}

The [!UICONTROL Trait Expression] section shows you the criteria users must meet to qualify for the [!UICONTROL trait]. これらのルールは、[特性を作成または編集](../../features/traits/about-trait-builder.md)するときに設定されます。

![](assets/traitExpression.png)

## [!UICONTROL Trait] セグメント {#trait-segments}

The [!UICONTROL Segments with this Trait] section lists all the segments the selected [!UICONTROL trait] belongs to. セグメント名をクリックすると、そのセグメントの詳細が表示されます。

![](assets/traitSegments.png)

## [!UICONTROL Trait] 監査/履歴ログ {#trait-audit-history}

For [!UICONTROL rule-based] and [!UICONTROL onboarded traits], the [!UICONTROL Trait Expression Change History] shows you the last 10 changes made to [!UICONTROL trait] expression rules and who made them. If your [!UICONTROL trait] has more than 10 changes, click **[!UICONTROL Export to CSV]** to download the entire audit log. またはで監査ログを使用でき [!UICONTROL folder] ません [!UICONTROL algorithmic traits]。

>[!NOTE]
>
>[!UICONTROL By User] 列に「[!UICONTROL Not Available]」と表示される場合、そのユーザーのアカウントが削除されていることを表します。

![](assets/traitHistory.png)