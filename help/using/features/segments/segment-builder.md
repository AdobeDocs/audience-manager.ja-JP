---
description: セグメントビルダーでセグメントを作成する方法について説明します。
seo-description: セグメントビルダーでセグメントを作成する方法について説明します。
seo-title: セグメントビルダー
solution: Audience Manager
title: セグメントビルダー
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# セグメントビルダー {#segment-builder}

[!UICONTROL Segment Builder]でセグメントを作成する必須手順とオプション手順について説明します。

## ビデオデモ

まず、[Audience Manager でのセグメントの作成ビデオ](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)をご覧ください。このビデオでは、セグメントの作成プロセスに関する手順を説明します。詳しくは、以下のセクションを参照してください。

## セグメントの作成 {#create-segment}

### セグメントビルダーのセクション

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] は、[!UICONTROL Basic Information]、[!UICONTROL Traits]、[!UICONTROL Destinations Mapping] の 3 つのセクションで構成されます。セグメントを作成するには、「[!UICONTROL Basic Information]」セクションと「[!UICONTROL Traits]」セクションの必須フィールドに入力します。「[!UICONTROL Destinations Mapping]」の設定はオプションです。詳しいヘルプについては、後述の説明を参照してください。

![create-segment](assets/create-segment.png)

1. 「[Basic Information](../../features/segments/segment-builder.md#segment-builder-controls-basics)」セクションで、以下の操作をおこないます。
   * セグメントの名前を設定します。セグメント名の最大長は 255 文字です。
   * セグメントのステータスを設定します（デフォルトは「active」です）。
   * データソースを選択します。最初のドロップダウンメニューを使用して、Audience Manager のデータソース、Adobe Analytics のレポートスイート、またはその両方をフィルタリングします。次に、2 番目のドロップダウンメニューを使用して、データソースを選択します。Adobe Analytics レポートスイートを使用しない場合、データソースタイプセレクターは無効になり、デフォルトで Audience Manager データソースのみに設定されます。
   * セグメント認定に使用するプロファイル結合ルールを選択します。
   * セグメントを保存フォルダーに割り当てます。
2. 「[Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits)」セクションで、以下の操作をおこないます。
   * セグメントに追加する特性を検索して&#x200B;**[!UICONTROL Add Trait]**&#x200B;をクリックします。他の特性を追加し、特性グループを作成します。
   * **[!UICONTROL Browse All Traits]**&#x200B;をクリックして詳細検索モーダルを表示します。名前、ID、説明またはデータソースによる特性の検索。検索中にフォルダーをクリックすると、検索範囲をそのフォルダーおよびサブフォルダーに限定できます。また、特性タイプを基準に特性をフィルタリングすることもできます。
   * セグメントの作成時に有効な[特性レコメンデーション](trait-recommendations.md)を取得します。
   * 特性をクリックしてドラッグし、個別のグループを作成します。
   * グループ間にマウスポインターを当て、ブール演算子 [!UICONTROL AND]、[!UICONTROL OR]、[!UICONTROL AND NOT] を使用して関係を設定します。
   * 時計アイコンの上にマウスポインターを置き、[最新性と頻度](../../features/segments/recency-and-frequency.md)のルールを特性に追加します。
   * 特性を追加または削除して、セグメント母集団データを表示します。**[!UICONTROL Calculate Estimates]**&#x200B;をクリックすると、推定された母集団の数値が表示（または更新）されます。詳しくは、セグメントビルダーの[セグメント母集団データ](../../features/segments/segment-builder-data.md#segment-populations)を参照してください。
   * 終了したら、**[!UICONTROL Save]**&#x200B;をクリックします。
3. *（オプション）*「[宛先マッピング](../../features/segments/segment-builder.md#segment-builder-controls-destinations)」セクションでセグメントを宛先にマッピングします。
   * 宛先を検索し、**[!UICONTROL Add Destination]**&#x200B;をクリックします。宛先をセグメントに追加するには、その宛先が既に存在していなければなりません。
   * 終了したら、**[!UICONTROL Save]**&#x200B;をクリックします。

## セグメントビルダーのコントロール：「Basic Information」セクション{#segment-builder-controls-basics}

[!UICONTROL Segment Builder]では、[!UICONTROL the Basic Information]設定を使用して、新しい特性を作成したり、既存の特性を編集したりできます。新しいセグメントを作成するには、名前およびデータソースを指定して、保存フォルダーを選択します。その他のすべてのフィールドはオプションです。完了したら、「[!UICONTROL Traits]」セクションに移動します。

<!-- r_segment_basic_info_section.xml -->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>名前</b> </td> 
   <td colname="col2"> <p>セグメントに、機能や目的を表す、短く論理的な名前を設定します。略語や特殊文字は使用しないでください。セグメント名の最大長は 255 文字です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>説明</b> </td> 
   <td colname="col2"> <p>セグメントに関する追加の説明情報のフィールド。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>統合コード</b> </td> 
   <td colname="col2"> <p>ユーザー定義 ID などの会社特有の情報のフィールド。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>データソース</b> </td> 
   <td colname="col2"> <p>セグメントと特定のデータプロバイダーを関連付けます。 <p>最初のドロップダウンメニューを使用して、Audience Manager のデータソース、Adobe Analytics のレポートスイート、またはその両方をフィルタリングします。次に、2 番目のドロップダウンメニューを使用して、データソースを選択します。</p><p> Adobe Analytics レポートスイートを使用しない場合、データソースタイプセレクターは無効になり、デフォルトで Audience Manager データソースのみに設定されます。</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>プロファイル結合ルール</b> </td> 
   <td colname="col2"> <p>セグメント認定に使用するプロファイル結合ルールを選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ステータス</b> </td> 
   <td colname="col2"> <p>セグメントをアクティブまたは非アクティブにします（デフォルトではアクティブです）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>フォルダーストレージ</b> </td> 
   <td colname="col2"> <p>セグメントが属する保存フォルダーを指定します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## セグメントビルダーのコントロール：「Traits」セクション {#segment-builder-controls-traits}

[!UICONTROL Segment Builder]の [!UICONTROL Traits] セクションを使用すると、セグメントの特性を管理したり、特性グループを作成したり、認定条件を設定したりできます。セグメントに特性を追加するには、検索フィールドに特性名を入力して、「[!UICONTROL Add Trait]」をクリックします。特性を保存する（完了した場合）か、[!UICONTROL Destinations Mapping] に移動します。

<!-- r_segment_traits_section.xml -->

**前提条件：**「[!UICONTROL Basic Information]」セクションの必須フィールドに入力します。

| フィールド | 説明 |
|--- |--- |
| 基本ビュー | このセクションには、次の操作をおこなうための視覚的なコントロールがあります。 <ul><li>新しいセグメントを作成し、既存のセグメントを管理する。</li><li>セグメントから特性を削除する。</li><li>セグメントに最大 50 個の特性を追加する。</li><li>特性をドラッグアンドドロップして新しいグループを作成する。</li><li>セグメントの特性と特性グループを表示する。</li><li>ブール式、比較演算子、最新性／頻度の設定により認定条件を設定する。</li></ul> |
| コードビュー | 開発環境を開きます。この環境では、視覚的なインターフェイスの代わりにコードを使用して特性、グループ、認定要件の作成と管理ができます。このコードビューは、セグメントが次の条件に該当する場合に便利です。 <ul><li>個別のセグメントに 50 個を超える特性がある。注意：セグメント内の特性数の上限は 5000 個です。</li><li>多数の特性グループがある。</li><li>複雑な認定要件がある。</li></ul> |
| 検索 | セグメントに追加する特性を検索できます。 |
| 推奨事項 | セグメントルールに追加する類似特性についての有効なレコメンデーションを取得します。詳しくは、[特性レコメンデーション](trait-recommendations.md)を参照してください。 |
| 実際のセグメントサイズデータと推定セグメントサイズデータ | [セグメントビルダーにおける特性およびセグメント母集団データ](segment-builder-data.md)を参照してください。 |

## セグメントからの特性の削除 {#remove-traits}

セグメントの特性の管理は、セグメントの実行可能性を維持するために重要な作業です。セグメントから特性を削除する必要がある場合は、以下の手順に従ってください。

セグメントから特性を削除するには：

1. **Audience Data／Segments** に移動します。リストでスクロールするか、検索機能を使用して、目的のセグメントを特定します。
2. セグメント名をクリックして、セグメント詳細画面を開きます。
3. 「**Edit**」をクリックしてセグメントビルダーを開き、その後「**Traits**」をクリックして特性パネルを開きます。
4. 削除する特性の上にマウスポインターを置いて、X キーをクリックします。この操作により、セグメントから特性がただちに削除されます。

## セグメントビルダーのコントロール：「Destination Mappings」セクション {#segment-builder-controls-destinations}

[!UICONTROL Segment Builder]の[!UICONTROL Destinations Mapping]セクション（オプション）では、サードパーティ [!DNL cookie]、[!DNL URL]、またはサーバー間の宛先にセグメントデータを送信できます。宛先を追加するには、宛先を検索（または参照）し、宛先固有の情報を入力して、**[!UICONTROL Add Destination]**&#x200B;をクリックします。

<!-- r_segment_destinations_map.xml -->

### 前提条件

「[!UICONTROL Basic Information]」セクションと「[!UICONTROL Traits]」セクションの必須フィールドに入力します。また、宛先が存在している必要があります。

### 宛先マッピング検索ツール

**[!UICONTROL Destination Mappings]**&#x200B;パネルには、次の表に示す検索ツールがあります。

| 検索タイプ | 説明 |
|---|---|
| **宛先名別に検索** | 特定の宛先を名前で検索できます。検索するには、文字を入力します。検索語に基づいてフィールドが自動入力されます。終了したら、**[!UICONTROL Add Destination]**&#x200B;をクリックします。 |
| **すべての宛先を参照** | 使用可能な&#x200B;*すべての*&#x200B;宛先を参照します。ポップアップリストから宛先を選択し、セグメントに追加します。 |

## 宛先マッピングポップアップウィンドウのフィールド {#fields-in-dest-mappings}

[!UICONTROL Segment Builder]で宛先を選択すると、[!UICONTROL Add Destination] ダイアログが表示されます。このウィンドウには宛先とフィールドに関する静的情報が表示されます。フィールドは宛先タイプによって異なります。空のフィールドに必須の情報を入力し、宛先マッピングを設定します。

>[!NOTE]
>
>公開日はオプションです。空白にすると、宛先はアクティブになり、有効期限がなくなります。

<!-- r_add_mappings_pop.xml -->

### Cookie 宛先フィールド

「[!UICONTROL Destination Mapping]」フィールドで、データを宛先に送信するためのキーと値のペアを指定します。最初のフィールドにキー、2 番目のフィールドに値をそれぞれ入力します。Cookie 宛先ポップは次のようになります。

![](assets/cookie_modal.PNG)

### URL 宛先フィールド

「[!UICONTROL URL]」フィールドと「[!UICONTROL Secure URL]」フィールドで、宛先にデータを送るための完全な標準アドレスまたはセキュリティで保護されたアドレスを指定します。

![](assets/url_modal.PNG)

### サーバー間宛先フィールド

「[!UICONTROL Destination Value]」フィールドで、宛先にデータを送るために使用する値（キーと値のペアの一部）を指定します。

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Cookie の宛先の作成](../../features/destinations/create-cookie-destination.md)
>* [URL 宛先の作成](../../features/destinations/create-url-destination.md)

