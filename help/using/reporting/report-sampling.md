---
description: いくつかのレポートで使用されているサンプリング方法、サンプリングのエラー率についての概要、およびサンプルデータに基づく情報が返されるレポートのリスト。
seo-description: いくつかのレポートで使用されているサンプリング方法、サンプリングのエラー率についての概要、およびサンプルデータに基づく情報が返されるレポートのリスト。
seo-title: 選択した Audience Manager レポートでのデータサンプリングとエラー率
solution: Audience Manager
title: 選択した Audience Manager レポートでのデータサンプリングとエラー率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 33d844578c5cd620f9d4c33ec931ae0778aabb07
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 74%

---


# 選択した Audience Manager レポートでのデータサンプリングとエラー率 {#data-sampling-and-error-rates-in-selected-audience-manager-reports}

いくつかのレポートで使用されているサンプリング方法、サンプリングのエラー率についての概要、およびサンプルデータに基づく情報が返されるレポートのリスト。

## データサンプリング比 {#data-sampling-ratio}

一部の [!DNL Audience Manager] レポートでは、使用可能なすべてのデータのうちサンプリングしたセットに基づいて結果が表示されます。サンプリングされたデータの比率は 1:54 です。この場合、サンプリングされたデータを使用するレポートは、54 件のうち 1 件のレコードが結果として表示されます。

これらのレポートでは、結果を生成するのに膨大な処理能力が必要なので、統計的なサンプルデータを使用します。 サンプリングにより、必要な計算量の削減、システムパフォーマンスの維持、正確な結果の入手がすべてバランスよくおこなえます。

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## エラー率 {#error-rates}

重複データを生成するレポートでは、エラーが発生する場合があります。エラーは、以下に該当するレコードの割合として表されます。

* 本来レポートに含まれないはずが、追加されている。
* 本来レポートに含まれるはずが、含まれていない。

これまでのテストとモデルから、エラー率はデータセットのレコード数に反比例して&#x200B;*減少*&#x200B;することが判明しています。レコード数が多いデータセットでは、レコード数が少ないデータセットよりエラーが少なくなります。このアサーションについて、量的な面から見てみましょう。次の表からわかるように、所定のレコード数について、レポート結果の 95% が特定のエラー率を下回っています。

| レコード数 | エラー率 |
|--- |--- |
| 500～1,000 | 95% がエラー率 42% 未満である。 |
| 1,000～1,500 | 95% がエラー率 34% 未満である。 |
| 10,000～50,000 | 95% がエラー率 14% 未満である。 |
| 50,000 | 95% がエラー率 6% 未満である。 |
| 100,000 | 95% がエラー率 4% 未満である。 |
| 500,000 以上 | 95% がエラー率 2% 未満である。 |

## Minhashサンプリング手法の使用 {#minhash}

Audience Managerは、 [Minhash](https://en.wikipedia.org/wiki/MinHash) (Minhash)サンプリング手法に基づき、One Permutation Hashing（1置換ハッシュ）データスケッチの上にある特性およびセグメント評価子を計算する新しい方法を使用します。 この新しい方法では、Jaccardの類似性見積もりの標準の見積もりよりも低い分散が生成されます。 この方法を使用するレポートについては、以下のセクションを参照してください。

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## サンプリングデータを使用するレポート {#reports-using-sampled-data}

統計的にサンプリングされたデータとMinhashサンプリング手法を使用する [!DNL Audience Manager] レポートは、次のとおりです。

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| 統計的サンプリング | ミンハッシュサンプリング法 |
|--- |--- |
| [アドレス可能なオーディエンス](../features/addressable-audiences.md)データ（顧客レベルデータとセグメントレベルデータ）。 | [重複レポート](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) （特性間、セグメント間、セグメント間） |
| [!UICONTROL Profile Merge Rule]の[合計デバイス数](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics)指標。 | [特性レコメンデーション](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) は、 [!UICONTROL Search] タブのサンプルデータと [!UICONTROL Saved Searches] | [Audience MarketplaceRecommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
