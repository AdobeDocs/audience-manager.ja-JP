---
description: セグメント概要ページには、名前、セグメント内の特性、ルール、パフォーマンスデータ、宛先マッピング情報などが表示されます。
seo-description: セグメント概要ページには、名前、セグメント内の特性、ルール、パフォーマンスデータ、宛先マッピング情報などが表示されます。
seo-title: セグメント概要表示
solution: Audience Manager
title: セグメント概要表示
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
translation-type: tm+mt
source-git-commit: aadcafe10d452a0abc02a430485a373c6c80cdc5

---


# セグメント概要表示 {#segment-summary-view}

[!UICONTROL Segment Summary] ページには、名前、セグメント内の特性、ルール、パフォーマンスデータ、宛先マッピング情報などが表示されます。

メインダッシュボードのセグメント名をクリックすると、その概要ページにアクセスできます。「Summary」セクションには、以下が含まれます。

1. **[!UICONTROL Basic Information]：**&#x200B;セグメントが作成された際に指定された必須およびオプションの詳細を表示します。
1. **[!UICONTROL Segment Graph]：**&#x200B;固定の 1、7、14、30、60、90 日およびセグメントライフタイム間隔で、グラフでパフォーマンスデータを表示します。セグメント母集団の数については、[別のドキュメント](../../features/segments/segment-builder-data.md)で説明します。

   ![セグメントグラフ](assets/segment-graph.png)

1. **[!UICONTROL Identity Type Breakdown ]:** このレポートには、セグメントの資格を持つ人または世帯の数が表示されます。この訪問者数は、セグメントの資格を持つデバイスにリンクされているデバイスIDまたは外部デバイスグラフIDの数をカウントして表示されます（ [!UICONTROL Total Segment Population]表示される）。このレポートに示すクロスデバイスIDと外部デバイスグラフIDは、セグメントが使用しているプロファイル結合ルールとプロファイルを結合するために使用されます。このレポートは、セグメントの結合ルールでクロスデバイスデータソースまたは外部デバイスグラフを選択した場合にのみ表示されます。

   ![セグメントグラフ](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Managerでは、セグメントに対応するクロスデバイスIDがある場合に [!UICONTROL Identity Type Breakdown] のみレポートが表示されます。

1. **[!UICONTROL Segment Rules]：**&#x200B;セグメントの特性を認定ルールと共にリストします。
1. **[!UICONTROL Destination Mappings]：**&#x200B;セグメントの宛先マッピングをリストします。
1. **[!UICONTROL Management Tools]：**&#x200B;セグメントを作成、編集、クローン、削除するためのコントロール。