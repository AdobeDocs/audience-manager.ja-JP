---
description: Cookie の宛先は、ユーザーのブラウザーの Cookie からデータを返したり、Cookie にデータを書き込んだりします。Cookie には、当該ページにアクセスできる他のプラットフォームで読み取ることができるデータが格納されています。[!UICONTROL Destination Builder] で Cookie の宛先を作成するには、以下の手順に従います。
seo-description: Cookie の宛先は、ユーザーのブラウザーの Cookie からデータを返したり、Cookie にデータを書き込んだりします。Cookie には、当該ページにアクセスできる他のプラットフォームで読み取ることができるデータが格納されています。[!UICONTROL Destination Builder] で Cookie の宛先を作成するには、以下の手順に従います。
seo-title: Cookie の宛先の設定
solution: Audience Manager
title: Cookie の宛先の設定
feature: 宛先の基本
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 100%

---

# Cookie の宛先の設定 {#create-cookie-destination}

Cookie の宛先はデータを返し、ユーザーのブラウザー内の Cookie に書き込みます。Cookie には、当該ページにアクセスできる他のプラットフォームで読み取ることができるデータが格納されています。[!UICONTROL Destination Builder] で Cookie の宛先を作成するには、以下の手順に従います。

<!-- create-cookie-destination.xml -->

新しい cookie の宛先を作成するには、**[!UICONTROL Audience Data > Destinations > Create New Destination]** を開き、セクションに以下のように入力します。

## 基本情報 {#basic-information}

このセクションには、Cookie の宛先の作成プロセスを開始するフィールドとオプションが含まれています。このセクションを完了するには：

1. 「**[!UICONTROL Basic Information]**」をクリックして、コントロールを表示します。
2. 宛先の名前を入力します。略語や特殊文字は使用しないでください。
3. *（オプション）*&#x200B;宛先の説明を入力します。簡潔な説明は、宛先を定義するのに効果的です。
4. 「**[!UICONTROL Category]**」リストで、「**[!UICONTROL Custom]**」を選択します。
5. **[!UICONTROL Environment]** リストで、「**[!UICONTROL Browser]**」を選択します。Android や iOS アプリなど、ネイティブモバイル環境用に cookie の宛先を設定することはできません。
6. 「**[!UICONTROL Type]**」リストで、「**[!UICONTROL Cookie]**」をクリックします。
7. *（オプション）***[!UICONTROL Auto-fill Destination Mapping]** を選択します。オプションは次のとおりです。
   * **[!UICONTROL Segment ID]**：セグメント ID を自動的に追加して宛先に送信します。
   * **[!UICONTROL Integration Code Value]**：セグメント統合コードを自動的に追加して宛先マッピングに送信します。統合コードは、顧客が作成して使用する一意の ID です。最大 255 文字に制限されています。
8. 「**[!UICONTROL Next]**」をクリックして「[!UICONTROL Configuration]」セクションに移動するか、「**[!UICONTROL Data Export Labels]**」をクリックして書き出しコントロールを宛先に適用します。

## Data Export Labels {#data-export-labels-cookies}

このセクションには、[データ書き出しコントロール](../../features/data-export-controls.md)を Cookie の宛先に適用するオプションが含まれています。データ書き出しコントロールを使用しない場合は、この手順を省略してください。このセクションを完了するには：

1. 「**[!UICONTROL Data Export Labels]**」をクリックして、コントロールを表示します。
2. 宛先に適用するデータ書き出しコントロールに対応するラベルを選択します（詳しくは、[データ書き出しラベルを宛先に追加する](/help/using/features/destinations/add-data-export-labels.md)を参照してください）。
3. 「**[!UICONTROL Save]**」をクリックします。

## 設定 {#configuration}

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
1. 「**[!UICONTROL Save]**」をクリックします。

他の設定はすべてオプションです。**[!UICONTROL Cookie Domain]** および **[!UICONTROL Publish data to]** 設定について詳しくは、[Cookie の宛先のオプション設定](/help/using/features/destinations/cookie-destination-options.md)を参照してください。

## Segment Mappings {#segments-mapping}

このセクションでは、セグメントを検索し宛先に追加することができます。このセクションを完了するには：

1. 「**[!UICONTROL Segment Mappings]**」をクリックして、コントロールを表示します。
1. **[!UICONTROL Search and Add Segments]**&#x200B;ボックスにセグメントの名前を入力するか、「**[!UICONTROL Browse All Segments]**」をクリックして使用可能なセグメントのリストを参照します。
1. 使用するセグメントが見つかったら、「**[!UICONTROL Add Selected Segments]**」をクリックします。セグメントを追加すると、[!UICONTROL Edit Mapping] ウィンドウが開きます。
1. [!UICONTROL Edit Mapping] ダイアログでは、
   * **[!UICONTROL Mapping]** を使用すると、上記の「設定」セクションで指定したキーの値を設定できます。
   * **[!UICONTROL Publish from]** を使用すると、宛先の開始日と終了日を設定できます。終了日が未指定の場合、宛先の有効期限は無期限になります。
1. 「**[!UICONTROL Save]**」をクリックします。
1. 「**[!UICONTROL Done]**」をクリックします。
