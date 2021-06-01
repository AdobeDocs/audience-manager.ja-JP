---
description: データ書き出しラベルは、データソースに設定する書き出しコントロールと連携して動作します。データ書き出しラベルによって、セグメントへの制限された特性の追加や、宛先へのセグメントデータの送信が防止されます。Cookie や URL の新規または既存の宛先に複数の書き出しラベルを設定できます。
seo-description: データ書き出しラベルは、データソースに設定する書き出しコントロールと連携して動作します。データ書き出しラベルによって、セグメントへの制限された特性の追加や、宛先へのセグメントデータの送信が防止されます。Cookie や URL の新規または既存の宛先に複数の書き出しラベルを設定できます。
seo-title: サーバー間宛先のセグメントの追加または編集
solution: Audience Manager
title: サーバー間宛先のセグメントの追加または編集
feature: 宛先の基本
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '260'
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
