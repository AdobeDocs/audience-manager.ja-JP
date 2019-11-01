---
description: セグメント概要ページには、名前、セグメント内の特性、ルール、パフォーマンスデータ、宛先マッピング情報などが表示されます。
seo-description: セグメント概要ページには、名前、セグメント内の特性、ルール、パフォーマンスデータ、宛先マッピング情報などが表示されます。
seo-title: セグメントの詳細ページ
solution: Audience Manager
title: セグメントの詳細ページ
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: IDタイプの分類， IDの分類，オーディエンスIDレポート
translation-type: tm+mt
source-git-commit: 51f38819bfbc72c2588f63a63fb8ba2e963919ff

---


# セグメントの詳細ページ {#segment-summary-view}

個々のセグメントの詳細ページには、セグメント名、ID、パフォーマンス指標、セグメントを定義するルール、宛先マッピングなど、セグメントの詳細の概要が表示されます。 To view these details, go to **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Segments]** and click the name of the segment you want to work with.

## セグメント管理ツール {#segment-management-tools}

セグメントの詳細ページの上部には、セグメントの管理に使用できるツールがあります。

1. **[!UICONTROL Add New]**:このオプションを使用して、をアクティブにし、新 [!UICONTROL Segment Builder] しいセグメントを作成します。
2. **[!UICONTROL Edit]**:このオプションを使用して、現在のセグメントの設定を変更します。
3. **[!UICONTROL Duplicate]**:このオプションを使用して、現在のセグメントのコピーを作成します。
4. **[!UICONTROL Delete]**:このオプションを使用して、Audience Managerアカウントから現在のセグメントを削除します。
5. **[!UICONTROL Marketplace Recommendations]**:このオプションを使用すると、購読していないデータフィードから、表示しているセグ [!UICONTROL Audience Marketplace] メントと類似したセグメントを検索できます。 Marketplace内で [Marketplaceをナビゲートし](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) 、類似のセグメントを見つける方法については、Audience Marketplace for Data Buyersを参照してください。

![基本セグメント情報](assets/basic-segment-information.png)

## セグメント情報 {#basics}

セグメント管理ツールの下に、次のセグメント情報が表示されます。

1. **[!UICONTROL Basic Information]：**&#x200B;セグメントが作成された際に指定された必須およびオプションの詳細を表示します。これらのフ [ィールドの意味について詳しくは、「セグメントビルダー](segment-builder.md) 」を参照してください。
2. **[!UICONTROL Segment Graph]：**&#x200B;固定の 1、7、14、30、60、90 日間隔のグラフでパフォーマンスデータを表示します。セグメント母集団の数については、[別の記事](../../features/segments/segment-builder-data.md)で説明します。

   ![セグメントグラフ](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]：**&#x200B;このレポートには、クロスデバイス ID の数と外部デバイスグラフ ID の数をカウントした、セグメントに適合するユーザーまたは世帯の数が表示されます。外部デバイスグラフ ID は、セグメントに適合するデバイスにリンクされています（[!UICONTROL Total Segment Population] で表示）。このレポートに示すクロスデバイス ID と外部デバイスグラフ ID は、セグメントが使用しているプロファイル結合ルールとプロファイルを結合するために使用されます。このレポートは、セグメントが使用しているプロファイル結合ルールで、クロスデバイスデータソースまたは外部デバイスグラフを選択した場合にのみ表示されます。

   ![セグメントグラフ](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager では、セグメントに適合するクロスデバイス ID がある場合に [!UICONTROL Identity Type Breakdown] のみレポートが表示されます。

   の概要については、以下のビデオをご覧くださ [!UICONTROL Identity Type Breakdown]い。
   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=jpn)

4. **[!UICONTROL Segment Rules]：**&#x200B;セグメントの特性を認定ルールと共にリストします。
5. **[!UICONTROL Destination Mappings]：**&#x200B;セグメントの宛先マッピングをリストします。
6. **[!UICONTROL Management Tools]：**&#x200B;セグメントを作成、編集、クローン、削除するためのコントロール。