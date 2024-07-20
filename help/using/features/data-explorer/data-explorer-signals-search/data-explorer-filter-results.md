---
description: シグナルタイプに基づいてシグナル検索の結果をフィルタリングします。
seo-description: Filter the results of a signal search based on the signal type.
seo-title: Filter Search Results
title: 検索結果のフィルタリング
uuid: 7b764a5d-f8ae-4f7b-83f5-7f6c40de639b
feature: Data Explorer
exl-id: df178712-6417-4c4d-b5f8-5a8c00bfcd12
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 100%

---

# 検索結果のフィルタリング {#filter-search-results}

シグナルタイプに基づいてシグナル検索の結果をフィルタリングします。

1. [!UICONTROL Audience Data > Signals > Search]へ移動し、目的のキーと値のペアを使用して [!UICONTROL Signals Search] を実行するか、フィルターを使用して検索範囲を広げます。
1. 「**[!UICONTROL Filter by Signal Type]**」セクションで、以下のカテゴリに基づいて検索結果をフィルタリングします。

   * **[!UICONTROL Actionable log files]**：[!DNL Google] [!DNL DCM] ログファイル経由で受信したシグナル。
   * **[!DNL Adobe Analytics]**：ご使用の [!DNL Adobe Analytics] アカウントから受信したシグナル。シグナルを表示するレポートスイートを選択するには、「**[!UICONTROL Filter by report suites]**」ドロップダウンメニューを使用します。
   * **[!UICONTROL General online data]**：訪問者別に生成され、アクションにつながるログファイルと [!DNL Adobe Analytics] には含まれていないリアルタイムデータ。
   * **[!UICONTROL Onboarded records]**：バッチデータ転送で受信したデータ。シグナルを表示するデータソースを選択するには、「**[!UICONTROL Filter by data source]**」ドロップダウンメニューを使用します。

1. オプションとして、後で使用するために[検索条件を保存](../../../features/data-explorer/data-explorer-signals-search/data-explorer-save-search.md)することができます。
