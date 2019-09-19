---
description: 一般レポートは、特性、セグメントおよび宛先に関するパフォーマンスデータを返します。
seo-description: Audience Manager の一般レポートは、特性、セグメントおよび宛先に関するパフォーマンスデータを返します。
seo-title: Audience Manager の一般的なレポート
solution: Audience Manager
title: 一般レポート
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
translation-type: ht
source-git-commit: 1c626c770208150d209d93f666b581113ada8de9

---


# 一般レポート{#general-reports}

[!UICONTROL General]は、特性、セグメントおよび宛先に関するパフォーマンスデータを返します。

## 概要 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] は[!UICONTROL Role Based Access Control]（[!UICONTROL RBAC]）を使用して、[!UICONTROL General]レポートへのユーザーグループ権限を拡張します。ユーザーは、レポートに記載されている特性やセグメントのうち、閲覧する権限のあるものだけを表示できます。[!UICONTROL RBAC] 機能により、社内チームが閲覧できるレポートデータを制御することができます。例えば、様々な広告主アカウントを管理する代理店では、広告主 A のアカウントを管理するチームが広告主 B のレポートデータを閲覧できないように、ユーザーグループの権限を設定することができます。

以下が必要な場合、[!UICONTROL General]レポートを実行します。

* 特性、セグメントまたは出力先でパフォーマンスを確認する。
* 1、7、14、30、60、90 日間隔でインプレッション数（合計および個別）を追跡する。
* 合計および個別の読み込み数を確認する。
* 特性とセグメントのパフォーマンスを比較する。
* 強いまたは弱いパフォーマンス特性およびセグメントを特定したり、需要を分析したり、サードパーティレポートでデータの読み込み／実行を比較したりする。
* データを（.csv 形式で）書き出してさらに分析したり共有したりする。

次の図は、[!UICONTROL General]レポートの主な要素の概要を示しています。

![](assets/general_reports.png)

1. 次のオプションを設定します。

   * **Report Type：**&#x200B;目的のレポートタイプ（Trait、Segment、Destination のいずれか）を選択します。

   * **For Dates Through：**&#x200B;レポートの日付範囲を指定します。

2. 名前または ID で、特性、セグメントまたは宛先を検索します。
3. フォルダーのリストで、レポートの対象となる特性、セグメントまたは宛先をドラッグし、右側の「[!UICONTROL Selections]」パネルにドロップします。
4. 書き出し可能な表の形式で表示するレポートを生成します。

## 一般レポートの実行 {#run-general-report}

この節では、[!UICONTROL General]の実行方法と、時間および他のパフォーマンスオプションの設定方法を説明します。

<!-- 

t_run_general_report.xml

 -->

1. **[!UICONTROL Analytics]** ダッシュボードで、「**[!UICONTROL General Reports]**」をクリックします。
1. 「**[!UICONTROL Report Type]**」ドロップダウンリストで、目的のタイプ（特性、セグメント、宛先）を選択します。
1. *（オプション）*&#x200B;当日以外の日付を終了日として指定する場合、日付ボックスをクリックしてカレンダーを表示し、終了日を選択します。
1. 名前または ID で、特性、セグメントまたは宛先を検索します。
1. フォルダーのリストで、レポートの対象となる特性、セグメントまたは宛先をドラッグし、右側の「[!UICONTROL Selections]」パネルにドロップします。
1. 「**[!UICONTROL Run Report]**」をクリックします。

   結果が書き出し可能な表形式で表示されます。列ヘッダーをクリックすると、結果が昇順または降順で並べ替えられます。
1. レポートの上部にある目的のオプションボタンを選択して、データをパフォーマンス（[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]、または [!UICONTROL Total Trait Population]）または時間（1 日、7 日、14 日、30 日、60 日、90 日の範囲）を基準にフィルタリングできます。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations]は[!UICONTROL Rule-based Traits]に対してのみ計算されます。

1. *（オプション）*「**[!UICONTROL Export to CSV]**」をクリックします。これにより、1 日中の範囲の [!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]、および [!UICONTROL Total Trait Population] が書き出されます。

## 一般レポートの結果の説明 {#general-reports-explained}

[!UICONTROL General Reports]の数字は、[!UICONTROL User Profile Store]から直接生成されます。結果には、これらのレポートの数値が生成されたときに [!DNL Audience Manager] のバックエンドに含まれていたユーザー数が反映されています。

* これらの数値には、過度のトラフィックの訪問者 ID は含まれません。ボットからのトラフィックは、アドビのバックエイドシステムに到達する前にフィルタリングされます。また、一部のボットトラフィックは、バックエンドで毎週実行されるクリーンアップジョブの間に破棄されます。
* [!DNL Audience Manager] UUID で識別されるデータを受信処理を介してオンボーディングする場合、アドビのシステムでアクティブでなくなったユーザーがこれらの ID に含まれていれば、これらの非アクティブな [!DNL Audience Manager] UUID は、[!UICONTROL User Profile Store]に到達せず、報告もされません。
* [!UICONTROL Total Trait Realizations]は[!UICONTROL Rule-based Traits]に対してのみ計算されます。

## 特性に関する一般レポートの結果 {#general-report-results-traits}

一般レポートを実行し、レポートタイプに **[!UICONTROL Trait]** を選択する場合は、次の指標が使用可能です。

**Unique Trait Realizations**

この指標は、選択した時間範囲内で特性の対象として認定された[Audience Manager の一意のユーザー ID（UUID）](../reference/ids-in-aam.md)のユニーク数を表します。例えば、ユーザーが 10 月 1 日にホームページに 3 回訪問した場合、「Unique Trait Realizations」は 1 になります。

**Total Trait Realizations**

この指標は、選択した時間範囲内で特性が起動された合計回数を表します。例えば、ユーザーがホームページに訪問した後、技術ニュースとスポーツニュースのセクションに移動した場合、「Total Trait Realizations」は 3、「Unique Trait Realizations」は 1 として一般レポートに表示されます。

**Total Trait Population**

この指標は、特性の対象として現在認定されている Audience Manager UUID の合計数を表します。この数により、セグメント化とターゲティングに使用できるユーザーの総数を把握できます。通常、ユーザーが特性の一部となっている期間は[120 日間](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)です。例えば、ユーザーが今日ホームページに 3 回訪問した後、戻ってこなかった場合、今から 120 日後までは、ユーザーはこの母集団内のユーザーのままです。120 日が経過したら、母集団から削除されます。「Unique Trait Realizations」と「Total Trait Population」の違いに関するその他の例については、[特性認定に関するリファレンス](../features/traits/trait-qualification-reference.md)を参照してください。

次の図は、Trait レポートタイプの一般レポートを実行した結果を示しています。

![](assets/general_reports_metrics.png)

## セグメントに関する一般レポートの結果 {#general-report-results-segments}

一般レポートを実行し、レポートタイプに **[!UICONTROL Segment]** を選択する場合は、次の指標が使用可能です。

**Real-time Segment Population**

この指標は、指定した時間範囲内にリアルタイムで認識され、また Audience Manager で認識された時点でセグメントの対象として認定された個別訪問者の実際の数を表します。

**Total Segment Population**

この指標は、選択したルックバック期間内にセグメントの対象として認定された Audience Manager UUID の合計数を表します。1 日の「セグメント母集団の総数」は、ターゲティングのための最も正確なユーザーベースを表します。

>[!NOTE]
>
>アクティブ化された宛先のセグメント母集団の内訳を表示するには、「**[!UICONTROL Include Destination Mappings]**」を選択します。

次の図は、Segment レポートタイプの一般レポートを実行した結果を示しています。

![](assets/general_reports_segment_metrics.png)

## 宛先に関する一般レポートの結果 {#general-report-results-destinations}

一般レポートを実行し、レポートタイプに **[!UICONTROL Destination]** を選択する場合は、次の指標が使用可能です。

**Real-time Segment Population**

この指標は、指定した時間範囲内にリアルタイムで認識され、また Audience Manager で認識された時点でセグメントの対象として認定された個別訪問者の実際の数を表します。

**Total Segment Population**

この指標は、ルックバック期間内にセグメントに属していて、宛先に送信された Audience Manager UUID の合計数を表します。

次の図は、Destination レポートタイプの一般レポートを実行した結果を示しています。

![](assets/general_reports_destinations.png)
