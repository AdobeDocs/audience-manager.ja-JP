---
description: 宛先のランディングページには、URL、Cookie、サーバー間の各種宛先がすべて一覧表示されます。ここでは、宛先の作成、編集、検索、レポート作成をおこなえます。ランディングページには、Audience Data／Destinations でアクセスできます。
seo-description: 宛先のランディングページには、URL、Cookie、サーバー間の各種宛先がすべて一覧表示されます。ここでは、宛先の作成、編集、検索、レポート作成をおこなえます。ランディングページには、Audience Data／Destinations でアクセスできます。
seo-title: 宛先の管理
solution: Audience Manager
title: 宛先の管理
uuid: 6b66ff42-0075-49a7-a58f-7f8ea2295fdc
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# 宛先の管理 {#manage-destinations}

[!UICONTROL Destination] ランディングページには、すべて [!DNL URL]のCookie、cookieおよびサーバー間宛先が一覧表示されます。ここでは、宛先の作成、編集、検索、レポート作成をおこなえます。ランディングページがあり **[!UICONTROL Audience Data > Destinations]**&#x200B;ます。

## デフォルトのランディングページ {#default-landing-page}

<!-- destinations-home.xml -->

デフォルトのランディングページには、タイプに基づいて宛先が表示されます。次の4つのタブを使用して、宛先をフィルターできます。

* **すべて**:に、すべてのタイプの宛先を表示します。
* **Adobe Experience Cloud**:により、他のAdobe Experience Cloudソリューションにデータを送信する宛先が表示されます。現在、サポートされているオプションはAdobe Analyticsのみです。See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **統合プラットフォーム**:に、ユーザーベースの宛先とデバイスベースの宛先（別名サーバー間宛先）を示します。現在、ユーザーベースの宛先は、選択した顧客のみが利用できる機能です。
* **カスタム**:cookieおよびURLの宛先を表示します。


![](assets/destinations-landing.png)

## アドレス可能なオーディエンスのランディングページ {#audiences-landing-page}

サーバー間宛先のオーディエンスデータと一致率を確認するには、を選択 **[!UICONTROL Integrated Platforms > Device-Based]**&#x200B;します。

表示される情報について詳しくは [、アドレス可能なオーディエンスインターフェイス](/help/using/features/addressable-audiences.md#addressable-audience-interface)を参照してください。

![](/help/using/features/assets/addressable-audiences-landing.png)

## URL の宛先の設定 {#configure-url-destination}

[!DNL URL] の宛先は、ページから宛先へのピクセル呼び出しをおこないます。[!DNL URL] で [!UICONTROL Destination Builder] の宛先を作成するには、以下の手順に従います。

<!-- create-url-destination.xml -->

[!DNL URL] 新しい宛先を作成するには、以下の説明に従って、セクションに **[!UICONTROL Audience Data > Destinations > Create New Destination]** 移動してください。

### Basic Information {#basic-info}

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

### Data Export Labels {#data-export-labels-dest}

このセクションには、[データ書き出しコントロール](../../features/data-export-controls.md)を の宛先に適用するオプションが含まれています。[!DNL URL]データ書き出しコントロールを使用しない場合は、この手順を省略してください。このセクションを完了するには：

1. 「**[!UICONTROL Data Export Labels]**」をクリックして、コントロールを表示します。
2. 宛先に適用するデータ書き出しコントロールに対応するラベルを選択します（詳しくは、[データ書き出しラベルを宛先に追加する](../../features/destinations/manage-destinations.md#add-data-export-labels)を参照してください）。
3. **[!UICONTROL Save]**&#x200B;をクリックします。

### Configuration {#configure-base-data}

This section contains options that let you set a base [!DNL URL] and data delimiters passed in by the [!DNL URL] string. このセクションはオプションです。このセクションを完了するには：

1. 「**[!UICONTROL Configuration]**」をクリックして、コントロールを表示します。
1. *（オプション）*「**[!UICONTROL Serialize]**」チェックボックスを選択します。これで、セグメントごとに別個に呼び出しをおこなうのではなく、セグメントを連続して宛先に送信できます。シリアル化はデータ転送の効率化に役立ちます。このチェックボックスを選択すると、URL と区切り文字のフィールドが表示されます。詳しくは、[標準およびシリアル化されたキー値ペア](../../features/destinations/key-value-pairs.md).
1. 「**[!UICONTROL Serialize]**」を選択した場合は、下記の URL フィールドと区切り文字フィールドも設定する必要があります。

| フィールド | 説明 |
|--- |--- |
| Base URL | The base part of a standard `HTTP` [!DNL URL] that does not change. また、ベース URL に`%ALIAS%` [プレースホルダーマクロ](../../features/destinations/destination-macros.md#destination-macros-defined)を配置する必要があります。例: `https://www.myCompany.com/%alias%...` |
| Secure URL | The base part of a secure `HTTPS` [!DNL URL] that does not change. また、ベース URL に`%ALIAS%` [プレースホルダーマクロ](../../features/destinations/destination-macros.md#destination-macros-defined)を配置する必要があります。例: `https://www.myCompany.com/%alias%...` |
| 区切り | [!DNL URL] 文字列内のセグメント変数を区切るシンボル。これは通常、コンマかセミコロンです。これについては、宛先のパートナーに確認してください。 |

### Segment Mappings {#segment-mappings}

このセクションでは、セグメントを検索し宛先に追加することができます。このセクションを完了するには：

1. 「**[!UICONTROL Segment Mappings]**」をクリックして、コントロールを表示します。
1. **[!UICONTROL Search and Add Segments]** ボックスで、セグメントの名前を入力するか、使用可能なセグメントのリスト **[!UICONTROL Browse All Segments]** を参照します。
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1.  [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**：セグメントで使用されるキー値ペアを指定します。
   * **[!UICONTROL Start Date]** および宛先の開始日と終了日を選択します。**[!UICONTROL End Date]**&#x200B;終了日が未指定の場合、宛先の有効期限は無期限になります。
1. **[!UICONTROL Done]**&#x200B;をクリックします。

## サーバー間宛先のセグメントの追加または編集 {#add-edit-segments}

You can only add or edit segments for a server-to-server ([!DNL S2S]) destination. 宛先を作成 [!DNL S2S] すること [!UICONTROL Destination Builder]はできません。[!DNL S2S] 宛先を設定するには、コンサルタントにお問い合わせください。[!DNL S2S] リンク先のセグメントを追加または編集するには、次の手順に従います。

<!-- destination-s2s-edit.xml -->

[!DNL S2S] 宛先のセグメントマッピングを追加または編集するには:

1. 移動 **[!UICONTROL Audience Data > Destinations]**&#x200B;先&#x200B;**統合プラットフォーム/デバイスベース** を選択し、操作 [!DNL S2S] する宛先を見つけます。
2. 「[!UICONTROL Action]」列で鉛筆アイコンをクリックして、宛先を編集します。
   * **[!UICONTROL Search and Add Segments]** ボックスで、セグメントの名前を入力するか、使用可能なセグメントのリスト **[!UICONTROL Browse All Segments]** を参照します。
   * Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
   *  [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**:この宛先で使用される [キーと値のペア](../../features/destinations/key-value-pairs.md) の値を設定します。
      * **[!UICONTROL Start Date]** および宛先の開始日と終了日を選択します。**[!UICONTROL End Date]**&#x200B;終了日が未指定の場合、宛先の有効期限は無期限になります。
3. Click **[!UICONTROL Save]** and then click **[!UICONTROL Done]**.

## 宛先へのデータ書き出しラベルの追加 {#add-data-export-labels}

[!DNL Data Export Labels]はデータソースで設定された [!DNL Export Controls] と連携します。[!DNL Data Export Labels] によって、セグメントへの制限された特性の追加や、宛先へのセグメントデータの送信が防止されます。You can set multiple export labels to a new or existing [!DNL cookie] or [!DNL URL] destination.

>[!NOTE]
>
>書き出しラベルを追加するには、管理者権限&#x200B;*または*&#x200B;宛先の作成や編集をおこなうための十分な権限が必要です。

<!-- t_export_labels.xml -->

書き出しラベルを宛先に追加するには：

1. **[!UICONTROL Audience Data]**&#x200B;クリックします。
   * For new destinations: Click **[!UICONTROL Create New Destination]**. データ書き出しラベルを選択する前に、「[!UICONTROL Basic Information]」セクションに入力します。See [Create a Cookie Destination](../../features/destinations/manage-destinations.md#create-cookie-destination) or [Create a URL Destination](../../features/destinations/manage-destinations.md#configure-url-destination) for information.
   * 既存の宛先の場合：「[!DNL Search]」ボックスを使用して宛先を検索するか、リストをスクロールし、宛先名をクリックして開きます。
1. [!DNL Data Export Label] を選択します。書き出し制限を設定しない場合は、チェックボックスをオフにします。書き出しラベルには次のようなオプションがあります。
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >書き出し制限は、データソースに[書き出しコントロールの照合](../../features/data-export-controls.md)が設定されていないと機能しません。
1. **[!UICONTROL Save]**&#x200B;をクリックします。

>[!MORE_LIKE_THIS]
>
>* [データソースの作成](../../features/manage-datasources.md#create-data-source)

