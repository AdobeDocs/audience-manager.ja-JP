---
description: トレンドレポートでは、特性とセグメントに関するトレンドデータを返します。
seo-description: トレンドレポートでは、特性とセグメントに関するトレンドデータを返します。
seo-title: トレンドレポート
solution: Audience Manager
title: トレンドレポート
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: 一般レポートとトレンドレポート
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 99%

---

# トレンドレポート {#trend-reports}

トレンドレポートでは、特性とセグメントに関するトレンドデータを返します。

## 概要 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] は[!UICONTROL Role Based Access Control]（[!UICONTROL RBAC]）を使用して、[!UICONTROL Trend]レポートへのユーザーグループ権限を拡張します。ユーザーは、レポートに記載されている特性やセグメントのうち、閲覧する権限のあるものだけを表示できます。[!UICONTROL RBAC] 機能により、社内チームが閲覧できるレポートデータを制御することができます。

例えば、様々な広告主アカウントを管理する代理店では、広告主 A のアカウントを管理するチームが広告主 B のレポートデータを閲覧できないように、ユーザーグループの権限を設定することができます。

以下が必要な場合、[!UICONTROL Trend]レポートを実行します。

* 特性やセグメント別にトレンドデータをレビューする。
* 1 日、7 日、14 日、30 日、60 日、90 日間隔でトレンドを追跡する。
* 一定期間にわたって特性とセグメントのトレンドを比較する。
* 好調または低調な特性およびセグメントを特定する。
* データを（.csv 形式で）書き出してさらに分析したり共有したりする。

次の図は、[!UICONTROL Trend]レポートの主な要素の概要を示しています。

![](assets/trend_reports.png)

1. 次のオプションを設定します。
   **Report Type：** 目的のレポートタイプ（特性またはセグメント）を選択します。
   **Date Range：** レポートの日付範囲（開始日と終了日）を指定します。
   **Display Interval：**&#x200B;表示間隔（1 日、7 日、14 日、30 日、60 日、90 日のいずれか）を指定します。
1. 特性またはセグメントを名前または ID で検索します。
1. フォルダーのリストで、レポートの対象となる特性またはセグメントをドラッグし、右側の「[!UICONTROL Selections]」パネルにドロップします。
1. データをグラフ形式で表示するレポートを生成するか、レポートを CSV 形式に書き出します。

## トレンドレポートの実行 {#run-trend-report}

[!UICONTROL Trend]レポートを実行する手順を以下に示します。

<!-- 

t_working_with_trend_reports.xml

 -->

1. **[!UICONTROL Analytics]** ダッシュボードで、「**[!UICONTROL Trend Reports]**」をクリックします。
1. 「**[!UICONTROL Report Type]**」ドロップダウンリストで、目的のタイプ（**[!UICONTROL Trait]** または **[!UICONTROL Segment]**）を選択します。
1. 日付ボックスをクリックしてカレンダーを表示し、レポートの開始日と終了日を選択します。
1. 表示間隔として 1 日、7 日、14 日、30 日、60 日、90 日のいずれかを指定します。
1. 特性またはセグメントを名前または ID で検索します。
1. フォルダーのリストで、レポートの対象となる特性またはセグメントをドラッグし、右側の「[!UICONTROL Selections]」パネルにドロップします。
   * パフォーマンスを最高にするには、[!UICONTROL Trend]レポートを実行する際に対象とする特性またはセグメントの数を、一度に 20 件未満にします。
1. 表示するレポートの種類（「Traits」または「Segments」）に応じて、「**[!UICONTROL Graph Traits]**」または「**[!UICONTROL Graph Segments]**」をクリックします。これらのオプションでは、フォルダーはすべて無視され、個別に選択した特性やセグメントのみがグラフに表示されます。

   または

   「**[!UICONTROL Export to CSV]**」をクリックして、特性またはセグメントのデータとすべてのフォルダーを CSV 形式で書き出し、分析や共有ができるようにします。これにより、1 日中の範囲の [!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]、および [!UICONTROL Total Trait Population] が書き出されます。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations]は[!UICONTROL Rule-based Traits]に対してのみ計算されます。

1. （オプション）個別の特性やセグメントにマウスを移動し、各データポイントの訪問者数と日付を表示します。テーブルで列ヘッダーをクリックすると、結果が昇順または降順で並べ替えられます。

## 特性に関するトレンドレポートの結果 {#trend-report-results-traits}

[!UICONTROL Trend Report] を実行し、レポートタイプに **[!UICONTROL Trait]** を選択する場合は、次のフィルターを使用できます。

結果を [!UICONTROL Device ID] でフィルタリングする場合：

* [!UICONTROL Unique Trait Realizations] は、選択した期間において、特性を自分のプロファイルに追加した匿名デバイス訪問者の数を表します。
* [!UICONTROL Total Trait Realization] は、選択した期間内の匿名の特性適合数の合計です。
* [!UICONTROL Total Trait Population] は、プロファイルにこの特性がある匿名デバイス訪問者の数を表します。

結果を [!UICONTROL Cross-Device ID] でフィルタリングする場合：

* [!UICONTROL Unique Trait Realizations] は、選択した期間において、特性を自分のプロファイルに追加した認証済み訪問者の数を表します。
* [!UICONTROL Total Trait Realization] は、選択した期間内の認証済みの特性適合数の合計です。
* [!UICONTROL Total Trait Population] は、プロファイルにこの特性がある認証済み訪問者の数を表します。

![trend-report-traits](assets/trend-report-traits.png)

0 は [!DNL Audience Manager] がその日のデータを収集していないことを表します。空白のエントリは、その特性が存在しないことを表します。

クロスデバイス指標のしくみについて詳しくは、以下のビデオをご覧ください。

>[!VIDEO](https://docs.adobe.com/content/help/ja-JP/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## セグメントに関するトレンドレポートの結果 {#segment-report-results-traits}

[!UICONTROL Trend Report] を実行し、レポートタイプに **[!UICONTROL Segments]** を選択する場合は、次のフィルターを使用できます。

* **[!UICONTROL Real-time Segment Population]**：選択した期間内のセグメントの対象となる訪問者の数。
* **[!UICONTROL Total Segment Population]**：セグメントの対象となる訪問者の合計数。

![trend-report-segments](assets/trend-report-segments.png)
