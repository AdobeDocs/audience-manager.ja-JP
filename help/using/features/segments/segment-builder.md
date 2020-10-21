---
description: セグメントビルダーでセグメントを作成する方法について説明します。
seo-description: セグメントビルダーでセグメントを作成する方法について説明します。
seo-title: セグメントビルダー
solution: Audience Manager
title: セグメントビルダー
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 44%

---


# [!UICONTROL Segment Builder] {#segment-builder}

[!UICONTROL Segment Builder]でセグメントを作成する必須手順とオプション手順について説明します。

## ビデオデモ

まず、[Audience Manager でのセグメントの作成ビデオ](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)をご覧ください。このビデオでは、セグメントの作成プロセスに関する手順を説明します。詳しくは、以下のセクションを参照してください。

## 指標をさらに制限する [!UICONTROL Segment] {#create-segment}

### セグメントビルダーのセクション

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] は、[!UICONTROL Basic Information]、[!UICONTROL Traits]、[!UICONTROL Destinations Mapping] の 3 つのセクションで構成されます。To create a [!UICONTROL segment], complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. 「[!UICONTROL Destinations Mapping]」の設定はオプションです。詳しいヘルプについては、後述の説明を参照してください。

1. 「[Basic Information](../../features/segments/segment-builder.md#segment-builder-controls-basics)」セクションで、以下の操作をおこないます。

   ![create-segment](assets/create-segment.png)

   * [!UICONTROL segment] に名前を付けます。The maximum length of a [!UICONTROL segment] name is 255 characters.
   * Set the [!UICONTROL segment] status (active is default).
   * を選択し [!UICONTROL data source]ます。 Use the first drop-down menu to filter between Audience Manager [!UICONTROL data sources], Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your [!UICONTROL data source]. If you are not using Adobe Analytics report suites, the [!UICONTROL data source] type selector is disabled and defaulted to Audience Manager data sources only.
   * クオリフィケ [!UICONTROL profile merge rule] ーションに使用するオ [!UICONTROL segment] プションを選択します。
   * Assign the [!UICONTROL segment] to a storage folder.

1. 「[Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits)」セクションで、以下の操作をおこないます。
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Search for the [!UICONTROL trait] you want to add to a segment and click **[!UICONTROL Add Trait]**. Add another [!UICONTROL trait] to create a [!UICONTROL trait] group.
   * Bring up the [!UICONTROL Advanced Search] modal by clicking **[!UICONTROL Browse All Traits]**. 名前、ID、説明、 [!UICONTROL traits] またはで検索 [!UICONTROL data source]します。 検索中にフォルダーをクリックすると、検索範囲をそのフォルダーおよびサブフォルダーに限定できます。You can also filter [!UICONTROL traits] by [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded], and [!UICONTROL Algorithmic]) or population type ([Device ID](../../reference/ids-in-aam.md) and [Cross-Device ID](../../reference/ids-in-aam.md)).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Get live [trait recommendations](trait-recommendations.md) as you build your [!UICONTROL segment].
   * Click and drag [!UICONTROL traits] to create separate groups.
   * グループ間にマウスポインターを当て、ブール演算子 [!UICONTROL AND]、[!UICONTROL OR]、[!UICONTROL AND NOT] を使用して関係を設定します。
   * Hover over the clock icon to add [recency and frequency](../../features/segments/recency-and-frequency.md) rules to the [!UICONTROL trait].
   * View segment population data as you add or remove [!UICONTROL traits]. **[!UICONTROL Calculate Estimates]**&#x200B;をクリックすると、推定された母集団の数値が表示（または更新）されます。Read more about [segment population data](../../features/segments/segment-builder-data.md#segment-populations) in the [!UICONTROL Segment Builder].
   * 終了したら、「**[!UICONTROL Save]**」をクリックします。

1. *（オプション）* 「 [!UICONTROL segment] 宛先マッピング [!UICONTROL destination] 」セクション [](../../features/segments/segment-builder.md#segment-builder-controls-destinations) のにをマッピングします。
   * Search for the [!UICONTROL destination] and click **[!UICONTROL Add Destination]**. Note, the [!UICONTROL destination] must already exist before you can add it to a [!UICONTROL segment].
   * 終了したら、「**[!UICONTROL Save]**」をクリックします。

クロスデバイス指標のしくみについて詳しくは、以下のビデオをご覧ください。

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## [!UICONTROL Segment Builder] コントロール： [!UICONTROL Basic Information] セクション {#segment-builder-controls-basics}

[!UICONTROL Segment Builder]では、[!UICONTROL the Basic Information]設定を使用して、新しい特性を作成したり、既存の特性を編集したりできます。To create a new [!UICONTROL segment], provide a name, a [!UICONTROL data source], and select a storage folder. その他のすべてのフィールドはオプションです。完了したら、「[!UICONTROL Traits]」セクションに移動します。

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| フィールド | 説明 |
---------|----------
| **[!UICONTROL Name]** | セグメントに、機能や目的を表す、短く論理的な名前を設定します。略語や特殊文字は使用しないでください。セグメント名の最大長は 255 文字です。 |
| **[!UICONTROL Description]** | セグメントに関する追加の説明情報のフィールド。 |
| **[!UICONTROL Integration Code]** | ユーザー定義 ID などの会社特有の情報のフィールド。 |
| **[!UICONTROL Data Source]** | セグメントと特定のデータプロバイダーを関連付けます。<br>最初のドロップダウンメニューを使用して、Audience Manager のデータソース、Adobe Analytics のレポートスイート、またはその両方をフィルタリングします。次に、2 番目のドロップダウンメニューを使用して、データソースを選択します。<br>Adobe Analytics レポートスイートを使用しない場合、データソースタイプセレクターは無効になり、デフォルトで Audience Manager データソースのみに設定されます。 |
| **[!UICONTROL Profile Merge Rule]** | セグメント認定に使用するプロファイル結合ルールを選択します。 |
| **[!UICONTROL Status]** | セグメントをアクティブまたは非アクティブにします（デフォルトではアクティブです）。 |
| **フォルダーストレージ** | セグメントが属する保存フォルダーを指定します。 |

## [!UICONTROL Segment Builder] コントロール： [!UICONTROL Traits] セクション {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], the [!UICONTROL Traits] section lets you manage [!UICONTROL traits] in a [!UICONTROL segment], create [!UICONTROL trait] groups, and set qualification criteria. To add a [!UICONTROL trait] to a [!UICONTROL segment], type the [!UICONTROL trait] name in the search field and click [!UICONTROL Add Trait]. Save the [!UICONTROL trait] (if finished) or move on to [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**前提条件：**「[!UICONTROL Basic Information]」セクションの必須フィールドに入力します。

| フィールド | 説明 |
|--- |--- |
| **[!UICONTROL Basic View]** | このセクションには、次の操作をおこなうための視覚的なコントロールがあります。 <ul><li>Build new and manage existing [!UICONTROL segments].</li><li>から削除 [!UICONTROL traits] し [!UICONTROL segment]ます。</li><li>最大50追加個（最大）からaまでの数 [!UICONTROL traits] を指定でき [!UICONTROL segment]ます。</li><li>Drag and drop [!UICONTROL traits] to create new groups.</li><li>表示 [!UICONTROL traits] と [!UICONTROL trait] グループを作成 [!UICONTROL segment]します。</li><li>ブール式、比較演算子、最新性／頻度の設定により認定条件を設定する。</li></ul> |
| **[!UICONTROL Code View]** | Opens a development environment that lets you create and manage [!UICONTROL traits], groups, and qualification requirements with code instead of the visual interface. The code view is useful if your [!UICONTROL segments]: <ul><li>1つの個人に50を超え [!UICONTROL traits] るデータを含め [!UICONTROL segment]る。 注意： [!UICONTROL Segments] は5000 [!UICONTROL traits] （最大）に制限されます。</li><li>Contain many [!UICONTROL trait] groups.</li><li>複雑な認定要件がある。</li></ul> |
| 検索 | Helps you find [!UICONTROL traits] to add to a [!UICONTROL segment]. |
| 推奨事項 | Get live recommendations for similar [!UICONTROL traits], from your first-party [!UICONTROL traits] and [!UICONTROL Audience Marketplace] data feeds that you are subscribed to. Add these recommendations to the [!UICONTROL segment] rule to expand your audience. 詳しくは、[特性レコメンデーション](trait-recommendations.md)を参照してください。 |
| **[!UICONTROL Marketplace Recommendations]** | Get live recommendations for similar [!UICONTROL traits], from [!UICONTROL Audience Marketplace] data feeds that you are not subscribed to. 詳しくは、[特性レコメンデーション](trait-recommendations.md)を参照してください。 |
| Real and Estimated [!UICONTROL Segment] Size Data | [セグメントビルダーにおける特性およびセグメント母集団データ](segment-builder-data.md)を参照してください。 |

## Folio Builder [!UICONTROL Traits] から [!UICONTROL Segment] {#remove-traits}

Managing the [!UICONTROL traits] in your [!UICONTROL segments] is an important part of keeping [!UICONTROL segments] viable. Follow these steps if you need to remove [!UICONTROL traits] from a [!UICONTROL segment].

から削除 [!UICONTROL traits] するに [!UICONTROL segment]は：

1. **[!UICONTROL Audience Data > Segments]** へ移動します。Scroll through the list or use the search feature to find the [!UICONTROL segment] you want to work with.
2. Click the [!UICONTROL segment] name to open the [!UICONTROL segment] details screen.
3. Click **Edit** to open [!UICONTROL Segment Builder] and then click **Traits** to open the [!UICONTROL traits] panel.
4. Hover over the [!UICONTROL trait] you want to delete and then click the X. This action immediately removes the [!UICONTROL trait] from your [!UICONTROL segment].

## [!UICONTROL Segment Builder] コントロール： [!UICONTROL Destinations Mappings] セクション {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], the optional [!UICONTROL Destinations Mapping] section lets you send [!UICONTROL segment] data to a third-party [!DNL cookie], [!DNL URL], or [!UICONTROL server-to-server destination]. To add a [!UICONTROL destination], search (or browse) for a [!UICONTROL destination], provide [!UICONTROL destination] specific information, and click **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### 前提条件

「[!UICONTROL Basic Information]」セクションと「[!UICONTROL Traits]」セクションの必須フィールドに入力します。また、宛先が存在している必要があります。

### [!UICONTROL Destination Mappings] 検索ツール

**[!UICONTROL Destination Mappings]**&#x200B;パネルには、次の表に示す検索ツールがあります。

| 検索タイプ | 説明 |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Lets you search for a specific [!UICONTROL destination] by name. 検索するには、文字を入力します。検索語に基づいてフィールドが自動入力されます。終了したら、「**[!UICONTROL Add Destination]**」をクリックします。 |
| **[!UICONTROL Browse All Destinations]** | Browse a list of *all* [!UICONTROL destinations] available to you. Select and add [!UICONTROL destinations] to your [!UICONTROL segment] from the popup list. |

## Fields in the [!UICONTROL Destination Mappings] Pop-up Windows {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], the [!UICONTROL Add Destination] dialog appears after you select a [!UICONTROL destination]. This window displays static information about the [!UICONTROL destination] and fields that vary depending on the [!UICONTROL destination] type. Provide the required information in the empty fields to set up a [!UICONTROL destination mapping].

>[!NOTE]
>
>公開日はオプションです。空白にすると、宛先はアクティブになり、有効期限がなくなります。

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] フィールド

In the [!UICONTROL Destination Mapping] fields, specify the key-value pairs used to send data to the [!UICONTROL destination]. 最初のフィールドにキー、2 番目のフィールドに値をそれぞれ入力します。Your [!UICONTROL cookie destination] pop could look similar to this:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] フィールド

In the [!UICONTROL URL] and [!UICONTROL Secure URL] fields, specify the complete standard or secure address used to send data to the [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] フィールド

In the [!UICONTROL Destination Value] field specify the value (part of a key-value pair) used to send data to the [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Cookie の宛先の作成](../../features/destinations/create-cookie-destination.md)
>* [URL 宛先の作成](../../features/destinations/create-url-destination.md)

