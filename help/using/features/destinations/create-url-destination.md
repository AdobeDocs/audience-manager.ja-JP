---
description: URL の宛先は、ページから宛先へのピクセル呼び出しをおこないます。Destination Builder で URL の宛先を作成するには、以下の手順に従います。
seo-description: URL の宛先は、ページから宛先へのピクセル呼び出しをおこないます。Destination Builder で URL の宛先を作成するには、以下の手順に従います。
seo-title: URL の宛先の設定
solution: Audience Manager
title: URL の宛先の設定
translation-type: ht
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# URL の宛先の設定 {#configure-url-destination}

[!DNL URL] の宛先は、ページから宛先へのピクセル呼び出しをおこないます。[!DNL URL] で [!UICONTROL Destination Builder] の宛先を作成するには、以下の手順に従います。

<!-- create-url-destination.xml -->

新しい [!DNL URL] の宛先を作成するには、**[!UICONTROL Audience Data > Destinations > Create New Destination]** を開き、セクションに以下のように入力します。

## Basic Information {#basic-info}

このセクションには、URL の宛先の作成プロセスを開始するフィールドとオプションが含まれています。このセクションを完了するには：

1. 「**[!UICONTROL Basic Information]**」をクリックして、コントロールを表示します。
2. 宛先の名前を入力します。略語や特殊文字は使用しないでください。
3. *（オプション）*&#x200B;宛先の説明を入力します。簡潔な説明が、宛先を定義するのに効果的です。
4. 「**[!UICONTROL Category]**」リストで、「**[!UICONTROL Custom]**」を選択します。
5. **[!UICONTROL Environment]**&#x200B;リストで、URLの宛先をトリガーする環境を選択します。
6. 「**[!UICONTROL Type]**」リストで、「**[!UICONTROL URL]**」をクリックします。
7. *（オプション）***[!UICONTROL Auto-fill Destination Mapping]** を選択します。オプションは以下のとおりです。
   * **[!UICONTROL Segment ID]**：セグメント ID を自動的に追加して宛先に送信します。
   * **[!UICONTROL Integration Code Value]**：セグメント統合コードを自動的に追加して宛先マッピングに送信します。統合コードは、顧客が作成して使用する一意の識別子です。最大 255 文字に制限されています。
8. 「**[!UICONTROL Next]**」をクリックして「[!UICONTROL Configuration]」セクションに移動するか、「**[!UICONTROL Data Export Labels]**」をクリックして書き出しコントロールを宛先に適用します。

## Data Export Labels {#data-export-labels-dest}

このセクションには、[データ書き出しコントロール](../../features/data-export-controls.md)を [!DNL URL] の宛先に適用するオプションが含まれています。データ書き出しコントロールを使用しない場合は、この手順を省略してください。このセクションを完了するには：

1. 「**[!UICONTROL Data Export Labels]**」をクリックして、コントロールを表示します。
2. 宛先に適用するデータ書き出しコントロールに対応するラベルを選択します（詳しくは、「[データ書き出しラベルを宛先に追加する](/help/using/features/destinations/add-data-export-labels.md)」を参照してください）。
3. 「**[!UICONTROL Save]**」をクリックします。

## Configuration {#configure-base-data}

このセクションには、[!DNL URL] 文字列で渡すベース と [!DNL URL] 文字列で渡すデータ区切り文字を設定できるオプションが含まれています。このセクションはオプションです。このセクションを完了するには：

1. 「**[!UICONTROL Configuration]**」をクリックして、コントロールを表示します。
1. *（オプション）***[!UICONTROL Serialize]** チェックボックスを選択します。これで、セグメントごとに別個に呼び出しをおこなうのではなく、セグメントを連続して宛先に送信できます。シリアル化はデータ転送の効率化に役立ちます。このチェックボックスを選択すると、URL と区切り文字のフィールドが表示されます。詳しくは、[標準型およびシリアル型のキーと値のペア](../../features/destinations/key-value-pairs.md)を参照してください。
1. **[!UICONTROL Serialize]** を選択した場合は、下記の URL フィールドと区切り文字フィールドも設定する必要があります。

| フィールド | 説明 |
|--- |--- |
| Base URL | 標準 `HTTP` の [!DNL URL] のうち、変更されないベース部分。また、ベース URL に`%ALIAS%` [プレースホルダーマクロ](../../features/destinations/destination-macros.md#destination-macros-defined)を配置する必要があります。例：`https://www.myCompany.com/%alias%...` |
| Secure URL | セキュア `HTTPS` の [!DNL URL] のうち、変更されないベース部分。また、ベース URL に`%ALIAS%` [プレースホルダーマクロ](../../features/destinations/destination-macros.md#destination-macros-defined)を配置する必要があります。例：`https://www.myCompany.com/%alias%...` |
| 区切り | [!DNL URL] 文字列のセグメント変数を区切るシンボル。これは通常、コンマかセミコロンです。これについては、宛先のパートナーに確認してください。 |

## Segment Mappings {#segment-mappings}

このセクションでは、セグメントを検索し宛先に追加することができます。このセクションを完了するには：

1. 「**[!UICONTROL Segment Mappings]**」をクリックして、コントロールを表示します。
1. **[!UICONTROL Search and Add Segments]**&#x200B;ボックスにセグメントの名前を入力するか、「**[!UICONTROL Browse All Segments]**」をクリックして使用可能なセグメントのリストを参照します。
1. 使用するセグメントが見つかったら、「**[!UICONTROL Add Selected Segments]**」をクリックします。セグメントを追加すると、[!UICONTROL Edit Mapping] ウィンドウが開きます。
1. [!UICONTROL Edit Mapping]：
   * **[!UICONTROL Mappings]**：セグメントで使用されるキー値ペアを指定します。
   * **[!UICONTROL Start Date]** および **[!UICONTROL End Date]**：宛先の開始日と終了日を選択します。終了日が未指定の場合、宛先の有効期限は無期限になります。
1. 「**[!UICONTROL Done]**」をクリックします。