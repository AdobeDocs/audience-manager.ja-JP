---
description: セグメント概要ページには、名前、セグメント内の特性、ルール、パフォーマンスデータ、宛先マッピング情報などが表示されます。
seo-description: セグメント概要ページには、名前、セグメント内の特性、ルール、パフォーマンスデータ、宛先マッピング情報などが表示されます。
seo-title: セグメント概要表示
solution: Audience Manager
title: セグメント概要表示
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# セグメント概要表示 {#segment-summary-view}

[!UICONTROL Segment Summary] ページには、名前、セグメント内の特性、ルール、パフォーマンスデータ、宛先マッピング情報などが表示されます。

メインダッシュボードのセグメント名をクリックすると、その概要ページにアクセスできます。「Summary」セクションには、以下が含まれます。

1. **[!UICONTROL Basic Information]：**&#x200B;セグメントが作成された際に指定された必須およびオプションの詳細を表示します。
2. **[!UICONTROL Segment Graph]：**&#x200B;固定の 1、7、14、30、60、90 日間隔のグラフでパフォーマンスデータを表示します。We explain segment population numbers in a [separate article](../../features/segments/segment-builder-data.md).

   ![セグメントグラフ](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]：**&#x200B;このレポートには、クロスデバイス ID の数と外部デバイスグラフ ID の数をカウントした、セグメントに適合するユーザーまたは世帯の数が表示されます。外部デバイスグラフ ID は、セグメントに適合するデバイスにリンクされています（[!UICONTROL Total Segment Population] で表示）。このレポートに示すクロスデバイス ID と外部デバイスグラフ ID は、セグメントが使用しているプロファイル結合ルールとプロファイルを結合するために使用されます。このレポートは、セグメントが使用しているプロファイル結合ルールで、クロスデバイスデータソースまたは外部デバイスグラフを選択した場合にのみ表示されます。

   ![セグメントグラフ](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager では、セグメントに適合するクロスデバイス ID がある場合に [!UICONTROL Identity Type Breakdown] のみレポートが表示されます。

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=jpn)

4. **[!UICONTROL Segment Rules]：**&#x200B;セグメントの特性を認定ルールと共にリストします。
5. **[!UICONTROL Destination Mappings]：**&#x200B;セグメントの宛先マッピングをリストします。
6. **[!UICONTROL Management Tools]：**&#x200B;セグメントを作成、編集、クローン、削除するためのコントロール。