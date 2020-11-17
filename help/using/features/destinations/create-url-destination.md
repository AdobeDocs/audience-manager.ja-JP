---
description: URL の宛先は、ページから宛先へのピクセル呼び出しをおこないます。Destination Builder で URL の宛先を作成するには、以下の手順に従います。
seo-description: URL の宛先は、ページから宛先へのピクセル呼び出しをおこないます。Destination Builder で URL の宛先を作成するには、以下の手順に従います。
seo-title: URL の宛先の設定
solution: Audience Manager
title: URL の宛先の設定
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 73%

---



# Webサイトの [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] makes pixel calls from a page to your [!DNL destination]. Follow these instructions to create a [!DNL URL] [!DNL destination] with [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

To create a new [!DNL URL] [!DNL destination], go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

## Basic Information {#basic-info}

This section contains fields and options that start the [!DNL URL destination] creation process. このセクションを完了するには：

1. 「**[!UICONTROL Basic Information]**」をクリックして、コントロールを表示します。
2. [!DNL destination] に名前を付けます。略語や特殊文字は使用しないでください。
3. *（オプション）*[!DNL destination] の説明を入力します。A concise description is an effective way to define or provide more information about a [!DNL destination].
4. 「**[!UICONTROL Category]**」リストで、「**[!UICONTROL Custom]**」を選択します。
5. In the **[!UICONTROL Environment]** list, select the environment in which to trigger the [!DNL URL destination].
6. 「**[!UICONTROL Type]**」リストで、「**[!UICONTROL URL]**」をクリックします。
7. *（オプション）***[!UICONTROL Auto-fill Destination Mapping]** を選択します。オプションは次のとおりです。
   * **[!UICONTROL Segment ID]**:セグメントIDをに自動的に追加および送信し [!DNL destination]ます。
   * **[!UICONTROL Integration Code Value]**：セグメント統合コードを自動的に追加して宛先マッピングに送信します。統合コードは、顧客が作成して使用する一意の識別子です。最大 255 文字に制限されています。
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

このセクションには、[データ書き出しコントロール](../../features/data-export-controls.md)を [!DNL URL] の宛先に適用するオプションが含まれています。データ書き出しコントロールを使用しない場合は、この手順を省略してください。このセクションを完了するには：

1. 「**[!UICONTROL Data Export Labels]**」をクリックして、コントロールを表示します。
2. 宛先に適用するデータ書き出しコントロールに対応するラベルを選択します（詳しくは、「[データ書き出しラベルを宛先に追加する](/help/using/features/destinations/add-data-export-labels.md)」を参照してください）。
3. 「**[!UICONTROL Save]**」をクリックします。

## Configuration {#configure-base-data}

このセクションには、[!DNL URL] 文字列で渡すベース と [!DNL URL] 文字列で渡すデータ区切り文字を設定できるオプションが含まれています。このセクションはオプションです。このセクションを完了するには：

1. 「**[!UICONTROL Configuration]**」をクリックして、コントロールを表示します。
1. *（オプション）***[!UICONTROL Serialize]** チェックボックスを選択します。This lets you send segments to a [!DNL destination] sequentially rather than making separate calls for each segment. シリアル化はデータ転送の効率化に役立ちます。このチェックボックスを選択すると、URL と区切り文字のフィールドが表示されます。詳しくは、[標準型およびシリアル型のキーと値のペア](../../features/destinations/key-value-pairs.md)を参照してください。
1. **[!UICONTROL Serialize]** を選択した場合は、下記の URL フィールドと区切り文字フィールドも設定する必要があります。

| フィールド | 説明 |
|--- |--- |
| [!UICONTROL Base URL] | 標準 `HTTP` の [!DNL URL] のうち、変更されないベース部分。また、ベース URL に`%ALIAS%` [プレースホルダーマクロ](../../features/destinations/destination-macros.md#destination-macros-defined)を配置する必要があります。例：`https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | セキュア `HTTPS` の [!DNL URL] のうち、変更されないベース部分。また、ベース URL に`%ALIAS%` [プレースホルダーマクロ](../../features/destinations/destination-macros.md#destination-macros-defined)を配置する必要があります。例：`https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | [!DNL URL] 文字列のセグメント変数を区切るシンボル。これは通常、コンマかセミコロンです。これについては、宛先のパートナーに確認してください。 |

## [!UICONTROL Segment Mappings] {#segment-mappings}

This section lets you search for and add segments to your [!UICONTROL destination]. このセクションを完了するには：

1. 「**[!UICONTROL Segment Mappings]**」をクリックして、コントロールを表示します。
1. **[!UICONTROL Search and Add Segments]**&#x200B;ボックスにセグメントの名前を入力するか、「**[!UICONTROL Browse All Segments]**」をクリックして使用可能なセグメントのリストを参照します。
1. 使用するセグメントが見つかったら、「**[!UICONTROL Add Selected Segments]**」をクリックします。セグメントを追加すると、[!UICONTROL Edit Mapping] ウィンドウが開きます。
1. [!UICONTROL Edit Mapping]：
   * **[!UICONTROL Mappings]**：セグメントで使用されるキー値ペアを指定します。
   * **[!UICONTROL Start Date]** および **[!UICONTROL End Date]**:の開始と終了日を選択し [!DNL destination]ます。 If the end date is blank, the [!DNL destination] never expires.
1. 「**[!UICONTROL Done]**」をクリックします。