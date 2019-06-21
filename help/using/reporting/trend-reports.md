---
description: トレンドレポートでは、特性とセグメントに関するトレンドデータを返します。
seo-description: トレンドレポートでは、特性とセグメントに関するトレンドデータを返します。
seo-title: トレンドレポート
solution: Audience Manager
title: トレンドレポート
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# トレンドレポート{#trend-reports}

トレンドレポートでは、特性とセグメントに関するトレンドデータを返します。

## 概要 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] を使用 [!UICONTROL Role Based Access Control][!UICONTROL RBAC]して、ユーザーグループの権限を [!UICONTROL Trend] レポートに拡張します。ユーザーは、レポートに記載されている特性やセグメントのうち、閲覧する権限のあるものだけを表示できます。[!UICONTROL RBAC] 機能により、社内チームが閲覧できるレポートデータを制御することができます。

例えば、様々な広告主アカウントを管理する代理店では、広告主 A のアカウントを管理するチームが広告主 B のレポートデータを閲覧できないように、ユーザーグループの権限を設定することができます。

Run a [!UICONTROL Trend] report when you need to:

* 特性やセグメント別にトレンドデータをレビューする。
* 1 日、7 日、14 日、30 日、60 日、90 日間隔でトレンドを追跡する。
* 一定期間にわたって特性とセグメントのトレンドを比較する。
* 好調または低調な特性およびセグメントを特定する。
* データを（.csv 形式で）書き出してさらに分析したり共有したりする。

The following illustration provides a high-level overview of key elements in the [!UICONTROL Trend] report.

![](assets/trend_reports.png)

1. 次のオプションを設定します。

   **Report Type：** 目的のレポートタイプ（特性またはセグメント）を選択します。

   **Date Range：** レポートの日付範囲（開始日と終了日）を指定します。

   **Display Interval：** 表示間隔（1 日、7 日、14 日、30 日、60 日、90 日のいずれか）を指定します。

2. 特性またはセグメントを名前または ID で検索します。
3. フォルダーのリストで、レポートの対象となる特性またはセグメントをドラッグし、右側の「[!UICONTROL Selections]」パネルにドロップします。
4. データをグラフ形式で表示するレポートを生成するか、レポートを CSV 形式に書き出します。

## トレンドレポートの実行 {#run-trend-report}

This procedure describes how to run a [!UICONTROL Trend] report.

<!-- 

t_working_with_trend_reports.xml

 -->

1. **[!UICONTROL Analytics]** ダッシュボードで、をクリック **[!UICONTROL Trend Reports]** します。
1. **[!UICONTROL Report Type]** ドロップダウンリストから、目的のタイプを選択します。 **[!UICONTROL Trait]****[!UICONTROL Segment]** または
1. 日付ボックスをクリックしてカレンダーを表示し、レポートの開始日と終了日を選択します。
1. 表示間隔として 1 日、7 日、14 日、30 日、60 日、90 日のいずれかを指定します。
1. 特性またはセグメントを名前または ID で検索します。
1. フォルダーのリストで、レポートの対象となる特性またはセグメントをドラッグし、右側の「[!UICONTROL Selections]」パネルにドロップします。

   For best performance, run a [!UICONTROL Trend] report on fewer than 20 traits or segments at a time.
1. Click **[!UICONTROL Graph Traits]** or **[!UICONTROL Graph Segments]**, depending on which type of report you are viewing (Traits or Segments).

   これらのオプションでは、フォルダーはすべて無視され、個別に選択した特性やセグメントのみがグラフに表示されます。

   または

   「**[!UICONTROL Export to CSV]**」をクリックして、特性またはセグメントのデータとすべてのフォルダーを CSV 形式で書き出し、分析や共有ができるようにします。This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] に対してのみ計算されます。[!UICONTROL Rule-based Traits]

1. （オプション）個別の特性やセグメントにマウスを移動し、各データポイントの訪問者数と日付を表示します。

   テーブルで列ヘッダーをクリックすると、結果が昇順または降順で並べ替えられます。

[!UICONTROL Trended Trait] レポートの場合、ゼロはその日のデータを収集し [!DNL Audience Manager] なかったことを示します。空白のエントリは、その特性が存在しないことを表します。以下の例は、両方の種類のエントリの例です。

![](assets/trended_data.png)
