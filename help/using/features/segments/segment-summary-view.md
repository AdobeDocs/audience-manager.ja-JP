---
description: セグメント概要ページには、名前、セグメント内の特性、ルール、パフォーマンスデータ、宛先マッピング情報などが表示されます。
seo-description: セグメント概要ページには、名前、セグメント内の特性、ルール、パフォーマンスデータ、宛先マッピング情報などが表示されます。
seo-title: セグメントの詳細ページ
solution: Audience Manager
title: セグメントの詳細ページ
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 100%

---


# セグメントの詳細ページ {#segment-summary-view}

個々のセグメントの詳細ページには、セグメント名、ID、パフォーマンス指標、セグメントを定義するルール、宛先マッピングなど、セグメントの詳細の概要が表示されます。これらの詳細を表示するには、**[!UICONTROL Audience Data]**／**[!UICONTROL Segments]** を選択し、対象となるセグメントの名前をクリックします。

## セグメント管理ツール {#segment-management-tools}

セグメントの詳細ページの上部に、セグメントを管理するために使用できるツールがあります。

1. **[!UICONTROL Add New]**：このオプションを使用して、[!UICONTROL Segment Builder] をアクティブ化し、新規セグメントを作成します。
2. **[!UICONTROL Edit]**：このオプションを使用して、現在のセグメントの設定を変更します。
3. **[!UICONTROL Duplicate]**：このオプションを使用して、現在のセグメントのコピーを作成します。
4. **[!UICONTROL Delete]**：このオプションを使用して、Audience Manager アカウントから現在のセグメントを削除します。
5. **[!UICONTROL Marketplace Recommendations]**：このオプションを使用して、購読していない [!UICONTROL Audience Marketplace] データフィードから、表示しているセグメントに類似したセグメントを見つけます。Marketplace へのナビゲート方法および類似したセグメントを見つける方法について詳しくは、[データ購入者向けの Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) を参照してください。

![basic-segment-information](assets/basic-segment-information.png)

## セグメント情報 {#basics}

セグメント管理ツールの下部に、次のセグメント情報が表示されます。

1. **[!UICONTROL Basic Information]：**&#x200B;セグメントが作成された際に指定された必須およびオプションの詳細を表示します。これらのフィールドが意味することの詳細な概要については、[セグメントビルダー](segment-builder.md)を参照してください。
2. **[!UICONTROL Segment Graph]：**&#x200B;固定の 1、7、14、30、60、90 日間隔のグラフでパフォーマンスデータを表示します。セグメント母集団の数については、[別の記事](../../features/segments/segment-builder-data.md)で説明します。

   ![セグメントグラフ](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]：**&#x200B;このレポートには、クロスデバイス ID の数と外部デバイスグラフ ID の数をカウントした、セグメントに適合するユーザーまたは世帯の数が表示されます。外部デバイスグラフ ID は、セグメントに適合するデバイスにリンクされています（[!UICONTROL Total Segment Population] で表示）。このレポートに示すクロスデバイス ID と外部デバイスグラフ ID は、セグメントが使用しているプロファイル結合ルールとプロファイルを結合するために使用されます。このレポートは、セグメントが使用しているプロファイル結合ルールで、クロスデバイスデータソースまたは外部デバイスグラフを選択した場合にのみ表示されます。

   ![セグメントグラフ](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager では、セグメントに適合するクロスデバイス ID がある場合に [!UICONTROL Identity Type Breakdown] のみレポートが表示されます。

   [!UICONTROL Identity Type Breakdown] の概要については、以下のビデオをご覧ください。
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]：**&#x200B;セグメントの特性を資格認定ルールと共にリストします。
5. **[!UICONTROL Destination Mappings]：**&#x200B;セグメントの宛先マッピングをリストします。
6. **[!UICONTROL Management Tools]：**&#x200B;セグメントを作成、編集、複製、削除するためのコントロール。