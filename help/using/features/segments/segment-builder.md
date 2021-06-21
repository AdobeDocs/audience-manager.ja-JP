---
description: セグメントビルダーでセグメントを作成する方法について説明します。
seo-description: セグメントビルダーでセグメントを作成する方法について説明します。
seo-title: セグメントビルダー
solution: Audience Manager
title: セグメントビルダー
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: セグメント
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 100%

---

# [!UICONTROL Segment Builder] {#segment-builder}

[!UICONTROL Segment Builder] でセグメントを作成する必須手順とオプション手順について説明します。

## ビデオデモ

まず、[Audience Manager でのセグメントの作成ビデオ](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)をご覧ください。このビデオでは、セグメントの作成プロセスに関する手順を説明します。詳しくは、以下のセクションを参照してください。

## [!UICONTROL Segment] の作成 {#create-segment}

### セグメントビルダーのセクション

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] は、[!UICONTROL Basic Information]、[!UICONTROL Traits]、[!UICONTROL Destinations Mapping] の 3 つのセクションで構成されます。[!UICONTROL segment] を作成するには、「[!UICONTROL Basic Information]」セクションと「[!UICONTROL Traits]」セクションの必須フィールドを比較します。「[!UICONTROL Destinations Mapping]」の設定はオプションです。詳しいヘルプについては、後述の説明を参照してください。

1. 「[基本情報](../../features/segments/segment-builder.md#segment-builder-controls-basics)」セクションで、以下の操作をおこないます。

   ![create-segment](assets/create-segment.png)

   * [!UICONTROL segment] に名前を付けます。[!UICONTROL segment] 名の最大長は 255 文字です。
   * [!UICONTROL segment] のステータスを設定します（デフォルトは「active」です）。
   * [!UICONTROL data source] を選択します。最初のドロップダウンメニューを使用して、Audience Manager の [!UICONTROL data sources]、Adobe Analytics のレポートスイート、またはその両方をフィルタリングします。次に、2 番目のドロップダウンメニューを使用して、[!UICONTROL data source] を選択します。Adobe Analytics レポートスイートを使用しない場合、[!UICONTROL data source] タイプセレクターは無効になり、デフォルトで Audience Manager データソースのみに設定されます。
   * [!UICONTROL segment] 認定に使用する [!UICONTROL profile merge rule] を選択します。
   * [!UICONTROL segment] を保存フォルダーに割り当てます。

1. 「[特性](../../features/segments/segment-builder.md#segment-builder-controls-traits)」セクションで、以下の操作をおこないます。
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * セグメントに追加する [!UICONTROL trait] を検索して、「**[!UICONTROL Add Trait]**」をクリックします。他の [!UICONTROL trait] を追加し、[!UICONTROL trait] グループを作成します。
   * 「**[!UICONTROL Browse All Traits]**」をクリックして [!UICONTROL Advanced Search] モーダルを表示します名前、ID、説明、または [!UICONTROL traits] で [!UICONTROL data source] を検索します。検索中にフォルダーをクリックすると、検索範囲をそのフォルダーおよびサブフォルダーに限定できます。[!UICONTROL traits]（[!UICONTROL Folder Trait]、[!UICONTROL Rule-based]、[!UICONTROL Onboarded] および [!UICONTROL Algorithmic]）や母集団タイプ（[デバイス ID](../../reference/ids-in-aam.md) および[クロスデバイス ID](../../reference/ids-in-aam.md)）で [!UICONTROL trait type] をフィルタリングできます。
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * [!UICONTROL segment] の作成時に有効な[特性レコメンデーション](trait-recommendations.md)を取得します。
   * [!UICONTROL traits] をクリックしてドラッグし、個別のグループを作成します。
   * グループ間にマウスポインターを当て、ブール演算子 [!UICONTROL AND]、[!UICONTROL OR]、[!UICONTROL AND NOT] を使用して関係を設定します。
   * 時計アイコンの上にマウスポインターを置き、[最新性と頻度](../../features/segments/recency-and-frequency.md)のルールを [!UICONTROL trait] に追加します。
   * [!UICONTROL traits] を追加または削除して、セグメント母集団データを表示します。**[!UICONTROL Calculate Estimates]** をクリックすると、推定された母集団の数値が表示（または更新）されます。詳しくは、[!UICONTROL Segment Builder] の[セグメント母集団データ](../../features/segments/segment-builder-data.md#segment-populations)を参照してください。
   * 終了したら、「**[!UICONTROL Save]**」をクリックします。

1. *（オプション）*「[Mapping](../../features/segments/segment-builder.md#segment-builder-controls-destinations)」セクションで [!UICONTROL segment] を [!UICONTROL destination] にマッピングします。
   * [!UICONTROL destination] を検索し、「**[!UICONTROL Add Destination]**」をクリックします。[!UICONTROL destination] を [!UICONTROL segment] に追加するには、その宛先が既に存在していなければなりません。
   * 終了したら、「**[!UICONTROL Save]**」をクリックします。

クロスデバイス指標のしくみについて詳しくは、以下のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] コントロール：[!UICONTROL Basic Information] セクション {#segment-builder-controls-basics}

[!UICONTROL Segment Builder] では、[!UICONTROL the Basic Information] 設定を使用して、新しい特性を作成したり、既存の特性を編集したりできます。新しい [!UICONTROL segment] を作成するには、名前および [!UICONTROL data source] を指定して、保存フォルダーを選択します。その他のすべてのフィールドはオプションです。完了したら、「[!UICONTROL Traits]」セクションに移動します。

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

## [!UICONTROL Segment Builder] コントロール：[!UICONTROL Traits] セクション {#segment-builder-controls-traits}

[!UICONTROL Segment Builder] の [!UICONTROL Traits] セクションを使用すると、[!UICONTROL segment] の [!UICONTROL traits] を管理、[!UICONTROL trait] グループを作成、および認定条件を設定できます。[!UICONTROL segment] に [!UICONTROL trait] を追加するには、検索フィールドに [!UICONTROL trait] 名を入力して、「[!UICONTROL Add Trait]」をクリックします。[!UICONTROL trait] を保存する（完了した場合）か、[!UICONTROL Destinations Mapping] に移動します。

<!-- r_segment_traits_section.xml-->

**前提条件：**「[!UICONTROL Basic Information]」セクションの必須フィールドに入力します。

| フィールド | 説明 |
|--- |--- |
| **[!UICONTROL Basic View]** | このセクションには、次の操作をおこなうための視覚的なコントロールがあります。 <ul><li>新しい [!UICONTROL segments] を作成し、既存のセグメントを管理します。</li><li>[!UICONTROL segment] から [!UICONTROL traits] を削除します。</li><li>最大 50 の [!UICONTROL traits] を [!UICONTROL segment] に追加できます。</li><li>[!UICONTROL traits] をドラッグアンドドロップして新しいグループを作成します。</li><li>[!UICONTROL segment] の [!UICONTROL traits] および [!UICONTROL trait] グループを表示します。</li><li>ブール式、比較演算子、最新性／頻度の設定により認定条件を設定する。</li></ul> |
| **[!UICONTROL Code View]** | 開発環境を開きます。この環境では、視覚的なインターフェイスの代わりにコードを使用して、[!UICONTROL traits] グループ、認定要件の作成と管理ができます。このコードビューは、[!UICONTROL segments] が次の条件に該当する場合に便利です。 <ul><li>個別 [!UICONTROL segment] に [!UICONTROL traits] が 50 より多く含まれる。注意：[!UICONTROL Segments] は 5000 個の [!UICONTROL traits]（最大）に制限されます。</li><li>多くの [!UICONTROL trait] グループを含んでいる。</li><li>複雑な認定要件がある。</li></ul> |
| 検索 | [!UICONTROL segment] に追加する [!UICONTROL traits] を検索できます。 |
| 推奨事項 | ファーストパーティ [!UICONTROL traits] および購読している [!UICONTROL Audience Marketplace] データフィードから、類似した [!UICONTROL traits] のライブレコメンデーションを取得します。これらのレコメンデーションを [!UICONTROL segment] ルールに追加して、オーディエンスを拡大します。詳しくは、[特性レコメンデーション](trait-recommendations.md)を参照してください。 |
| **[!UICONTROL Marketplace Recommendations]** | 購読していない [!UICONTROL Audience Marketplace] データフィードから、類似した [!UICONTROL traits] のライブレコメンデーションを取得します。詳しくは、[特性レコメンデーション](trait-recommendations.md)を参照してください。 |
| 実際の [!UICONTROL Segment] サイズデータと推定セグメントサイズデータ | [セグメントビルダーにおける特性およびセグメント母集団データ](segment-builder-data.md)を参照してください。 |

## [!UICONTROL Segment] から [!UICONTROL Traits] を削除します {#remove-traits}

[!UICONTROL segments] の [!UICONTROL traits] の管理は、[!UICONTROL segments] の実行可能性を維持するために重要な作業です。[!UICONTROL segment] から [!UICONTROL traits] を削除する必要がある場合は、以下の手順に従います。

[!UICONTROL segment] から [!UICONTROL traits] を削除するには：

1. **[!UICONTROL Audience Data > Segments]** へ移動します。リストでスクロールするか、検索機能を使用して、目的の [!UICONTROL segment] を特定します。
2. [!UICONTROL segment] 名をクリックして、[!UICONTROL segment] 詳細画面を開きます。
3. 「**編集**」をクリックして [!UICONTROL Segment Builder] を開き、その後「**特性**」をクリックして [!UICONTROL traits] パネルを開きます。
4. 削除する [!UICONTROL trait] の上にマウスポインターを置いて、X キーをクリックします。この操作により、ただちに [!UICONTROL segment] から [!UICONTROL trait] が削除されます。

## [!UICONTROL Segment Builder] コントロール：[!UICONTROL Destinations Mappings] セクション {#segment-builder-controls-destinations}

[!UICONTROL Segment Builder] の [!UICONTROL Destinations Mapping] セクション（オプション）では、サードパーティの [!DNL cookie]、[!DNL URL]、または [!UICONTROL server-to-server destination] に [!UICONTROL segment] データを送信できます。[!UICONTROL destination] を追加するには、[!UICONTROL destination] を検索（または参照）し、[!UICONTROL destination] 固有の情報を入力して、「**[!UICONTROL Add Destination]**」をクリックします。

<!-- r_segment_destinations_map.xml -->

### 前提条件

「[!UICONTROL Basic Information]」セクションと「[!UICONTROL Traits]」セクションの必須フィールドに入力します。また、宛先が存在している必要があります。

### [!UICONTROL Destination Mappings] 検索ツール

**[!UICONTROL Destination Mappings]** パネルには、次の表に示す検索ツールがあります。

| 検索タイプ | 説明 |
|---|---|
| **[!UICONTROL Search by Destination Name]** | 特定の [!UICONTROL destination] を名前で検索できます。検索するには、文字を入力します。検索語に基づいてフィールドが自動入力されます。終了したら、「**[!UICONTROL Add Destination]**」をクリックします。 |
| **[!UICONTROL Browse All Destinations]** | 使用可能な&#x200B;*すべての* [!UICONTROL destinations] を参照します。ポップアップリストから [!UICONTROL destinations] を選択し、[!UICONTROL segment] に追加します。 |

## [!UICONTROL Destination Mappings] ポップアップウィンドウのフィールド {#fields-in-dest-mappings}

[!UICONTROL Segment Builder] で [!UICONTROL destination] を選択すると、[!UICONTROL Add Destination] ダイアログが表示されます。このウィンドウには [!UICONTROL destination] とフィールドに関する静的情報が表示されます。フィールドは [!UICONTROL destination] タイプによって異なります。空のフィールドに必須の情報を入力し、[!UICONTROL destination mapping] を設定します。

>[!NOTE]
>
>公開日はオプションです。空白にすると、宛先はアクティブになり、有効期限がなくなります。

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] フィールド

「[!UICONTROL Destination Mapping]」フィールドで、データを [!UICONTROL destination] に送信するためのキーと値のペアを指定します。最初のフィールドにキー、2 番目のフィールドに値をそれぞれ入力します。[!UICONTROL cookie destination] ポップは次のようになります。

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] フィールド

「[!UICONTROL URL]」フィールドと「[!UICONTROL Secure URL]」フィールドで、[!UICONTROL destination] にデータを送るための完全な標準アドレスまたはセキュリティで保護されたアドレスを指定します。

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] フィールド

「[!UICONTROL Destination Value]」フィールドで、[!UICONTROL destination] にデータを送るために使用する値（キーと値のペアの一部）を指定します。

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Cookie の宛先の作成](../../features/destinations/create-cookie-destination.md)
* [URL 宛先の作成](../../features/destinations/create-url-destination.md)

