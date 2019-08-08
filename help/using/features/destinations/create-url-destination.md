---
description: URL の宛先は、ページから宛先へのピクセル呼び出しをおこないます。Destination Builder で URL の宛先を作成するには、以下の手順に従います。
seo-description: URL の宛先は、ページから宛先へのピクセル呼び出しをおこないます。Destination Builder で URL の宛先を作成するには、以下の手順に従います。
seo-title: URL の宛先の設定
solution: Audience Manager
title: URL の宛先の設定
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# URL の宛先の設定 {#configure-url-destination}

[!DNL URL] の宛先は、ページから宛先へのピクセル呼び出しをおこないます。[!DNL URL] で [!UICONTROL Destination Builder] の宛先を作成するには、以下の手順に従います。

<!-- create-url-destination.xml -->

[!DNL URL] 新しい宛先を作成するには、以下の説明に従って、セクションに **[!UICONTROL Audience Data > Destinations > Create New Destination]** 移動してください。

## Basic Information {#basic-info}

このセクションには、URL の宛先の作成プロセスを開始するフィールドとオプションが含まれています。このセクションを完了するには：

1. 「**[!UICONTROL Basic Information]**」をクリックして、コントロールを表示します。
2. 宛先の名前を入力します。略語や特殊文字は使用しないでください。
3. *（オプション）*&#x200B;宛先の説明を入力します。簡潔な説明が、宛先を定義するのに効果的です。
4. **[!UICONTROL Category]** リストで、を選択 **[!UICONTROL Custom]**&#x200B;します。
5. リストで **[!UICONTROL Environment]** 、URLの宛先をトリガーする環境を選択します。
6. **[!UICONTROL Type]** リストで、をクリック **[!UICONTROL URL]**&#x200B;します。
7. *（オプション）* を選択 **[!UICONTROL Auto-fill Destination Mapping]**&#x200B;します。オプションは以下のとおりです。
   * **[!UICONTROL Segment ID]**：セグメント ID を自動的に追加して宛先に送信します。
   * **[!UICONTROL Integration Code Value]**:セグメント統合コードを自動的に追加して宛先マッピングに送信します。統合コードは、顧客が作成して使用する一意の識別子です。最大 255 文字に制限されています。
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

## Data Export Labels {#data-export-labels-dest}

このセクションには、[データ書き出しコントロール](../../features/data-export-controls.md)を の宛先に適用するオプションが含まれています。[!DNL URL]データ書き出しコントロールを使用しない場合は、この手順を省略してください。このセクションを完了するには：

1. 「**[!UICONTROL Data Export Labels]**」をクリックして、コントロールを表示します。
2. 宛先に適用するデータ書き出しコントロールに対応するラベルを選択します（詳しくは、[データ書き出しラベルを宛先に追加する](/help/using/features/destinations/add-data-export-labels.md)を参照してください）。
3. **[!UICONTROL Save]**&#x200B;をクリックします。

## Configuration {#configure-base-data}

This section contains options that let you set a base [!DNL URL] and data delimiters passed in by the [!DNL URL] string. このセクションはオプションです。このセクションを完了するには：

1. 「**[!UICONTROL Configuration]**」をクリックして、コントロールを表示します。
1. *（オプション）*「**[!UICONTROL Serialize]**」チェックボックスを選択します。これで、セグメントごとに別個に呼び出しをおこなうのではなく、セグメントを連続して宛先に送信できます。シリアル化はデータ転送の効率化に役立ちます。このチェックボックスを選択すると、URL と区切り文字のフィールドが表示されます。詳しくは、[標準およびシリアル化されたキー値ペア](../../features/destinations/key-value-pairs.md).
1. 「**[!UICONTROL Serialize]**」を選択した場合は、下記の URL フィールドと区切り文字フィールドも設定する必要があります。

| フィールド | 説明 |
|--- |--- |
| Base URL | The base part of a standard `HTTP` [!DNL URL] that does not change. また、ベース URL に`%ALIAS%` [プレースホルダーマクロ](../../features/destinations/destination-macros.md#destination-macros-defined)を配置する必要があります。例: `https://www.myCompany.com/%alias%...` |
| Secure URL | The base part of a secure `HTTPS` [!DNL URL] that does not change. また、ベース URL に`%ALIAS%` [プレースホルダーマクロ](../../features/destinations/destination-macros.md#destination-macros-defined)を配置する必要があります。例: `https://www.myCompany.com/%alias%...` |
| 区切り | [!DNL URL] 文字列内のセグメント変数を区切るシンボル。これは通常、コンマかセミコロンです。これについては、宛先のパートナーに確認してください。 |

## Segment Mappings {#segment-mappings}

このセクションでは、セグメントを検索し宛先に追加することができます。このセクションを完了するには：

1. 「**[!UICONTROL Segment Mappings]**」をクリックして、コントロールを表示します。
1. **[!UICONTROL Search and Add Segments]** ボックスで、セグメントの名前を入力するか、使用可能なセグメントのリスト **[!UICONTROL Browse All Segments]** を参照します。
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1.  [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**：セグメントで使用されるキー値ペアを指定します。
   * **[!UICONTROL Start Date]** および宛先の開始日と終了日を選択します。**[!UICONTROL End Date]**&#x200B;終了日が未指定の場合、宛先の有効期限は無期限になります。
1. **[!UICONTROL Done]**&#x200B;をクリックします。