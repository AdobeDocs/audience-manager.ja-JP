---
description: データ書き出しラベルは、データソースに設定する書き出しコントロールと連携して動作します。データ書き出しラベルによって、セグメントへの制限された特性の追加や、宛先へのセグメントデータの送信が防止されます。Cookie や URL の新規または既存の宛先に複数の書き出しラベルを設定できます。
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: サーバー間宛先のセグメントの追加または編集
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
TQID: https://experienceleague.adobe.com/3bcMGBGMb4HtnPA8yFvO4UzfGXmpvM2Drs427ztfWDc
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: c138d302-73f0-4186-93ea-10c4ba52f943
  - id: e7029888-c8b0-46a7-849a-cf132a1559bf
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 202
ht-degree: 100%

---

# サーバー間宛先のセグメントの追加または編集 {#add-edit-segments}

サーバー間（[!DNL S2S]）の宛先については、セグメントの追加または編集のみできます。[[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md)で [!DNL S2S] の宛先を作成することはできません。[!DNL S2S] の宛先をセットアップする場合は、担当のコンサルタントにお問い合わせください。[!DNL S2S] の宛先のセグメントを追加または編集するには、以下の手順に従います。

<!-- destination-s2s-edit.xml -->

[!DNL S2S] の宛先のセグメントマッピングを追加または編集するには：

1. **[!UICONTROL Audience Data > Destinations]** へ移動します。**Integrated Platforms／Device-Based** を選択し、[!DNL S2S] の宛先を見つけます。
2. 「[!UICONTROL Action]」列で鉛筆アイコンをクリックして、宛先を編集します。
   * **[!UICONTROL Search and Add Segments]**&#x200B;ボックスにセグメントの名前を入力するか、「**[!UICONTROL Browse All Segments]**」をクリックして使用可能なセグメントのリストを参照します。
   * 使用するセグメントが見つかったら、「**[!UICONTROL Add Selected Segments]**」をクリックします。セグメントを追加すると、[!UICONTROL Edit Mapping] ウィンドウが開きます。
   * [!UICONTROL Edit Mapping]：
      * **[!UICONTROL Mappings]**：この宛先で使用される[キーと値のペア](../../features/destinations/key-value-pairs.md)の値を設定します。
      * **[!UICONTROL Start Date]** および **[!UICONTROL End Date]**：宛先の開始日と終了日を選択します。終了日が未指定の場合、宛先の有効期限は無期限になります。
3. 「**[!UICONTROL Save]**」、「**[!UICONTROL Done]**」の順にクリックします。
