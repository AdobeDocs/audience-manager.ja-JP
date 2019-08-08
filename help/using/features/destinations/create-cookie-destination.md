---
description: Cookie の宛先は、ユーザーのブラウザーの Cookie からデータを返したり、Cookie にデータを書き込んだりします。Cookie には、当該ページにアクセスできる他のプラットフォームで読み取ることができるデータが格納されています。次の手順に従って、[!UACROL Destination Builder]。
seo-description: Cookie の宛先は、ユーザーのブラウザーの Cookie からデータを返したり、Cookie にデータを書き込んだりします。Cookie には、当該ページにアクセスできる他のプラットフォームで読み取ることができるデータが格納されています。次の手順に従って、[!UACROL Destination Builder]。
seo-title: Cookie の宛先の設定
solution: Audience Manager
title: Cookie の宛先の設定
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Cookie の宛先の設定 {#create-cookie-destination}

Cookie の宛先は、ユーザーのブラウザーの Cookie からデータを返したり、Cookie にデータを書き込んだりします。Cookie には、当該ページにアクセスできる他のプラットフォームで読み取ることができるデータが格納されています。[!UICONTROL Destination Builder] で Cookie の宛先を作成するには、以下の手順に従います。

<!-- create-cookie-destination.xml -->

新しいcookieの宛先を作成するには、以下の説明に従って、セクションに **[!UICONTROL Audience Data > Destinations > Create New Destination]** 移動してください。

## Basic Information {#basic-information}

このセクションには、Cookie の宛先の作成プロセスを開始するフィールドとオプションが含まれています。このセクションを完了するには：

1. 「**[!UICONTROL Basic Information]**」をクリックして、コントロールを表示します。
2. 宛先の名前を入力します。略語や特殊文字は使用しないでください。
3. *（オプション）*&#x200B;宛先の説明を入力します。簡潔な説明が、宛先を定義するのに効果的です。
4. **[!UICONTROL Category]** リストで、を選択 **[!UICONTROL Custom]**&#x200B;します。
5. **[!UICONTROL Environment]** リストで、を選択 **[!UICONTROL Browser]**&#x200B;します。AndroidやiOSアプリなど、ネイティブモバイル環境用にcookieの宛先を設定することはできません。
6. **[!UICONTROL Type]** リストで、をクリック **[!UICONTROL Cookie]**&#x200B;します。
7. *（オプション）* を選択 **[!UICONTROL Auto-fill Destination Mapping]**&#x200B;します。オプションは以下のとおりです。
   * **[!UICONTROL Segment ID]**：セグメント ID を自動的に追加して宛先に送信します。
   * **[!UICONTROL Integration Code Value]**:セグメント統合コードを自動的に追加して宛先マッピングに送信します。統合コードは、顧客が作成して使用する一意の識別子です。最大 255 文字に制限されています。
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

## Data Export Labels {#data-export-labels-cookies}

このセクションには、[データ書き出しコントロール](../../features/data-export-controls.md)を Cookie の宛先に適用するオプションが含まれています。データ書き出しコントロールを使用しない場合は、この手順を省略してください。このセクションを完了するには：

1. 「**[!UICONTROL Data Export Labels]**」をクリックして、コントロールを表示します。
2. 宛先に適用するデータ書き出しコントロールに対応するラベルを選択します（詳しくは、[データ書き出しラベルを宛先に追加する](/help/using/features/destinations/add-data-export-labels.md)を参照してください）。
3. **[!UICONTROL Save]**&#x200B;をクリックします。

## Configuration {#configuration}

このセクションには、宛先の Cookie をセットアップできるフィールドとオプションが含まれています。

>[!NOTE]
>
>宛先の Cookie に書き込まれるデータは [!DNL Audience Manager] でエンコードされます。例えば、スペースは `%20` としてエンコードされ、セミコロンは `%3B` としてエンコードされます。

このセクションを完了するには：

1. 「**[!UICONTROL Configuration]**」をクリックして、コントロールを表示します。
1. Cookie の名前を入力します。略語や特殊文字は使用しないでください。
1. データ形式のオプションを選択します。これらのオプションでは、セグメントデータを宛先に送信するキー値ペアの区切り文字を選択できます。形式のオプションは次のとおりです。
   * **Single key**：キー値ペアのキーを設定できます。以下の「[!UICONTROL Segment Mappings]」セクションでセグメントを選択してから、値を設定します。
   * **Multi key**：キー値ペアのキーと値を設定できます。以下の「Segment Mappings」セクションでセグメントを選択してから、キー値ペアを作成します。これらのデータ要素について詳しくは、[標準およびシリアル化されたキー値ペア](../../features/destinations/key-value-pairs.md)を参照してください。
1. **[!UICONTROL Save]**&#x200B;をクリックします。

他の設定はすべてオプションです。For more information about the **[!UICONTROL Cookie Domain]** and **[!UICONTROL Publish data to]** settings, see [Optional Settings for Cookie Destinations](/help/using/features/destinations/cookie-destination-options.md).

## Segment Mappings {#segments-mapping}

このセクションでは、セグメントを検索し宛先に追加することができます。このセクションを完了するには：

1. 「**[!UICONTROL Segment Mappings]**」をクリックして、コントロールを表示します。
1. **[!UICONTROL Search and Add Segments]** ボックスにセグメントの名前を入力するか、をクリック **[!UICONTROL Browse All Segments]** して使用可能なセグメントのリストを参照します。
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. [!UICONTROL Edit Mapping] ダイアログ内:
   * **[!UICONTROL Mapping]「**」を使用すると、上記の「Configuration」セクションで指定したキーの値を設定できます。
   * **[!UICONTROL Publish from]「**」を使用すると、宛先の開始日と終了日を設定できます。終了日が未指定の場合、宛先の有効期限は無期限になります。
1. **[!UICONTROL Save]**&#x200B;をクリックします。
1. **[!UICONTROL Done]**&#x200B;をクリックします。