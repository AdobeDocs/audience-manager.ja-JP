---
description: セグメント間で共有される個別ユーザーの数に関するデータを返します。
seo-description: セグメント間で共有される個別ユーザーの数に関するデータを返します。
seo-title: セグメント間重複レポート
solution: Audience Manager
title: セグメント間重複レポート
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
translation-type: tm+mt
source-git-commit: 339d5550b22949862415d2abc812217e5479c993

---


# セグメント間重複レポート{#segment-to-segment-overlap-report}

セグメント間で共有される個別ユーザーの数に関するデータを返します。

>[!NOTE]
>
>Audience Managerの重複レポートは、RBACの原則に従います。You can only see segments from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_segment_overlap.xml

 -->

## 概要

[!UICONTROL Segment-to-Segment Overlap] このレポートは、次の場合に役立ちます。

* ニーズに応じて、重複の多いまたは少ないセグメントを特定する。重複の多い特性は、ターゲット設定されたオーディエンスを提供しますが、個別訪問者は少なくなります。重複の少ない特性は、より多数の個別訪問者にリーチするうえで役に立つ可能性があります。
* 予期しない重複を検出し、その情報を使用してパフォーマンスの高いセグメントを新しく作成する。

## レポートのサンプル

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Segment Overlap] report.

>[!NOTE]
>
>[!UICONTROL Segment-to-Segment Overlap] このレポートでは、同じセグメントをそのセグメント自体と比較すると、空のフィールドが返されます。

![](assets/segment-to-segment-overlap.png)

## 個々のデータポイントの詳細

個々の点を選択すると、データの詳細がポップアップウィンドウに表示されます。クリック操作で、レポートに表示されるデータが自動的に更新されます。

## セグメント間重複データポップフィールドの定義 {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

[!UICONTROL Segment-to-Segment Overlap] レポートのポップアップには以下の指標が含まれています。この表の個別訪問者数指標は、*リアルタイムユーザー数*&#x200B;を表していることに注意してください。

| 指標 | 説明 |
|---|---|
| **[!UICONTROL Segment ID1]** | レポート結果に表示されるセグメントの、一意の数値 ID。セグメントの行 ID として表示されます。 |
| **[!UICONTROL Segment ID2]** | レポートの実行時に選択したセグメントの、一意の数値 ID。セグメントの列 ID として表示されます。 |
| **[!UICONTROL Segment Name1]** | レポート結果行に表示されるセグメントの名前。 |
| **[!UICONTROL Segment Name2]** | レポートの実行時に選択したセグメントの名前。レポート結果列に表示されます。 |
| **[!UICONTROL Overlap %]** | 重複率を取得するために、Audience Managerは次の数式を使用します。重複する個別/（ベースセグメント個別、重なっているセグメント個別、重複する個別のセグメント） |
| **[!UICONTROL Overlap Uniques]** | 比較対象のセグメント間で共有されている個別訪問者の数。 |
| **[!UICONTROL Segment Uniques1]** | セグメント 1 の個別訪問者の数。 |
| **[!UICONTROL Segment Uniques2]** | セグメント 2 の個別訪問者の数。 |

>[!MORE_LIKE_THIS]
>
>* [データスライダーを使用したレポート結果のフィルタリング](../../reporting/dynamic-reports/data-sliders.md)
>* [インタラクティブレポートで使用される図形、色、サイズ](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [レポートのアイコンとツールの説明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重複レポート：更新スケジュールと最小セグメントサイズ](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [選択した Audience Manager レポートでのデータサンプリングとエラー率...](../../reporting/report-sampling.md)
>* [重複レポートの CSV ファイル](../../reporting/dynamic-reports/overlap-csv-files.md)