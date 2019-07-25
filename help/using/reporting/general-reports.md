---
description: 汎用レポートは、特性、セグメントおよび送信先に関するパフォーマンスデータを返します。
seo-description: Audience Managerの一般レポートは、特性、セグメントおよび送信先に関するパフォーマンスデータを返します。
seo-title: Audience Managerの一般的なレポート
solution: Audience Manager
title: 一般レポート
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# 汎用レポート{#general-reports}

[!UICONTROL General] 特性データが特性、セグメントおよび送信先に返されます。

## 概要 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] を使用 [!UICONTROL Role Based Access Control][!UICONTROL RBAC]して、ユーザーグループの権限を [!UICONTROL General] レポートに拡張します。ユーザーは、レポートに記載されている特性やセグメントのうち、閲覧する権限のあるものだけを表示できます。[!UICONTROL RBAC] 機能により、社内チームが閲覧できるレポートデータを制御することができます。例えば、様々な広告主アカウントを管理する代理店では、広告主 A のアカウントを管理するチームが広告主 B のレポートデータを閲覧できないように、ユーザーグループの権限を設定することができます。

Run a [!UICONTROL General] report when you need to:

* 特性、セグメントまたは出力先でパフォーマンスを確認する。
* 1、7、14、30、60、90 日間およびライフタイム期間でインプレッション数（合計および個別）を追跡する。
* 合計および個別の読み込み数を確認する。
* 特性とセグメントのパフォーマンスを比較する。
* 強いまたは弱いパフォーマンス特性およびセグメントを特定したり、需要を分析したり、サードパーティレポートでデータの読み込み／実行を比較したりする。
* データを（.csv 形式で）書き出してさらに分析したり共有したりする。

The following illustration provides a high-level overview of key elements in the [!UICONTROL General] report.

![](assets/general_reports.png)

1. 次のオプションを設定します。

   * **Report Type：**&#x200B;目的のレポートタイプ（Trait、Segment、Destination のいずれか）を選択します。

   * **For Dates Through：**&#x200B;レポートの日付範囲を指定します。

2. 名前または ID で、特性、セグメントまたは宛先を検索します。
3. フォルダーのリストで、レポートの対象となる特性、セグメントまたは宛先をドラッグし、右側の「[!UICONTROL Selections]」パネルにドロップします。
4. 書き出し可能な表の形式で表示するレポートを生成します。

## 一般レポートの実行 {#run-general-report}

This section describes how to run a [!UICONTROL General] report and set time and other performance options.

<!-- 

t_run_general_report.xml

 -->

1. **[!UICONTROL Analytics]** ダッシュボードで、をクリック **[!UICONTROL General Reports]**&#x200B;します。
1. 「**[!UICONTROL Report Type]**」ドロップダウンリストで、目的のタイプ（Trait、Segment または Destination）を選択します。
1. *条件付き* クリック:日付ボックスをクリックしてカレンダーを表示し、今日以外の日付を指定する場合はレポートの終了日を選択します。
1. 名前または ID で、特性、セグメントまたは宛先を検索します。
1. フォルダーのリストで、レポートの対象となる特性、セグメントまたは宛先をドラッグし、右側の「[!UICONTROL Selections]」パネルにドロップします。
1. **[!UICONTROL Run Report]**&#x200B;をクリックします。

   結果が書き出し可能な表形式で表示されます。列ヘッダーをクリックすると、結果が昇順または降順で並べ替えられます。
1. Select the desired option button at the top of the report to filter data by performance ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], or [!UICONTROL Total Trait Population]) or by time (1, 7, 14, 30, 60, 90-day range or lifetime).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] に対してのみ計算されます。[!UICONTROL Rule-based Traits]

1. *オプション* のクリック **[!UICONTROL Export to CSV]**。This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

## 一般レポートの結果の説明 {#general-reports-explained}

The numbers in the [!UICONTROL General Reports] are generated directly from our [!UICONTROL User Profile Store]. 結果には、これらのレポートの数値が生成されたときに [!DNL Audience Manager] のバックエンドに含まれていたユーザー数が反映されています。

* これらの数値には、過度のトラフィックの訪問者 ID は含まれません。ボットからのトラフィックは、アドビのバックエイドシステムに到達する前にフィルタリングされます。また、一部のボットトラフィックは、バックエンドで毎週実行されるクリーンアップジョブの間に破棄されます。
* If you onboard data via inbound processing keyed off the [!DNL Audience Manager] UUID, and these IDs include users that are no longer active in our system, these inactive [!DNL Audience Manager] UUIDs never reach the [!UICONTROL User Profile Store] and are not reported.
* [!UICONTROL Total Trait Realizations] に対してのみ計算されます。[!UICONTROL Rule-based Traits]

## 特性に関する一般レポートの結果 {#general-report-results-traits}

一般レポートを実行しレポートタイプとして **[!UICONTROL Trait]** を選択する場合は、次の指標が使用可能です。

**Unique Trait Realizations**

この指標は、選択した時間範囲内で特性の対象として認定された   [Audience Manager の一意のユーザー ID（UUID）](../reference/ids-in-aam.md)のユニーク数を表します。例えば、ユーザーが 10 月 1 日にホームページに 3 回訪問した場合、「Unique Trait Realizations」は 1 になります。

**Total Trait Realizations**

この指標は、選択した時間範囲内で特性が起動された合計回数を表します。例えば、ユーザーがホームページに訪問した後、技術ニュースとスポーツニュースのセクションに移動した場合、「Total Trait Realizations」は 3、「Unique Trait Realizations」は 1 として一般レポートに表示されます。

**合計特性母集団**

この指標は、特性の対象として現在認定されている Audience Manager UUID の合計数を表します。この数により、セグメント化とターゲット設定に使用できるユーザーの総数を把握できます。通常、ユーザーが特性の一部となっている期間は   [120 日間](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)です。例えば、ユーザーが今日ホームページに 3 回訪問した後、戻ってこなかった場合、今から 120 日後までは、ユーザーはこの母集団内のユーザーのままです。120 日が経過したら、母集団から削除されます。「Unique Trait Realizations」と「Total Trait Population」の違いに関するその他の例については、[特性の絞り込みに関するリファレンス](../features/traits/trait-qualification-reference.md)を参照してください。

次の図は、Trait レポートタイプの一般レポートを実行した結果を示しています。

![](assets/general_reports_metrics.png)

## セグメントに関する一般レポートの結果 {#general-report-results-segments}

一般レポートを実行しレポートタイプとして **[!UICONTROL Segment]** を選択する場合は、次の指標が使用可能です。

**Real-time Segment Population**

この指標は、指定した時間範囲内でリアルタイムで認識され、また Audience Manager で認識された時点でセグメントの対象として認定された個別訪問者の実際の数を表します。

**セグメント母集団の総数**

この指標は、選択したルックバック期間内にセグメントの対象として認定された Audience Manager UUID の合計数を表します。1 日の「セグメント母集団の総数」は、ターゲット設定のための最も正確なユーザーベースを表します。

>[!NOTE]
>
>Select **[!UICONTROL Include Destination Mappings]** to see a breakdown of segment population for activated destinations.

次の図は、Segment レポートタイプの一般レポートを実行した結果を示しています。

![](assets/general_reports_segment_metrics.png)

## 宛先に関する一般レポートの結果 {#general-report-results-destinations}

一般レポートを実行しレポートタイプとして **[!UICONTROL Destination]** を選択する場合は、次の指標が使用可能です。

**Real-time Segment Population**

この指標は、指定した時間範囲内でリアルタイムで認識され、また Audience Manager で認識された時点でセグメントの対象として認定された個別訪問者の実際の数を表します。

**セグメント母集団の総数**

この指標は、ルックバック期間内にセグメントに属していて、宛先に送信された Audience Manager UUID の合計数を表します。

次の図は、Destination レポートタイプの一般レポートを実行した結果を示しています。

![](assets/general_reports_destinations.png)
