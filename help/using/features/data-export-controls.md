---
description: 宛先へのデータ送信がデータプライバシーやデータ使用契約に違反する場合、データ書き出しコントロールはデータ送信を防止します。
seo-description: 宛先へのデータ送信がデータプライバシーやデータ使用契約に違反する場合、データ書き出しコントロールはデータ送信を防止します。
seo-title: データ書き出しコントロール
solution: Audience Manager
title: データ書き出しコントロール
uuid: de7f3608-c0cb-4049-973a-8be54525c600
translation-type: tm+mt
source-git-commit: 302670f294574c3b56ccd16aeca8ebab8f4e8ce9

---


# データ書き出しコントロール {#data-export-controls}

[!UICONTROL Data Export Controls] データのプライバシーまたはデータの使用に違反する場合に、送信先にデータを送信できないようにします。

## 概要 {#overview}

[!UICONTROL Data Export Controls] では、 [データソース](../features/datasources-list-and-settings.md#data-sources-list-and-settings) と [リンク先を分類](../features/destinations/destinations.md)できます。適用する分類によって、データを宛先に書き出せる場合または書き出せない場合が決まります。この機能は、以下で構成されます。

* **[!UICONTROL Data Export Controls]**:データソースに *データエクスポートコントロールを設定*&#x200B;できます。データソースに設定する場合、これらのコントロールはデータソースとその特性の使用方法を制限します。
* **[!UICONTROL Data Export Labels]**:宛先に *データエクスポートラベルを設定*&#x200B;できます。宛先に設定すると、これらのラベルは宛先によるデータの使用方法を識別します。See [Add Data Export Labels to a Destination](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) to learn how to add export labels to a destination.

データソースおよび宛先に適用した分類に基づいて、書き出しコントロールは以下の操作を防止します。

* 特性がデータソースに属している場合、セグメントがマッピングされる1つまたは複数の宛先のデータエクスポートラベルと互換性のないデータソースに特性が属する場合、特性をセグメントに追加します。
For example, say a segment is mapped to a destination with the export label **[UICONTROL! This destination may enable a combination with personally identifiable information (PII)]**. Export controls stop you from adding a trait to that segment if the data source that the trait belongs to has a data export control that says **[UICONTROL! Cannot be tied to personally identifiable information (PII)]**.
* 宛先宛先にデータを送信する場合、データエクスポートラベルは、次のいずれかのデータエクスポートコントロールによってブロックされます。
   * 含まれる特性のデータソース。
   * 含まれるセグメントで使用される特性のデータソース。
   * 含まれるセグメントによって利用されるプロファイル結合ルール。
   * 含まれているセグメントのプロファイル結合ルールに使用されるデータソース。

[!UICONTROL Data Export Controls] は、すべてのAudience Managerユーザーに自動的に使用できます。ただし、書き出しコントロールをデータソースに追加するには、管理者権限が必要です。書き出しラベルを宛先に追加するには、管理者権限または宛先を作成または編集するための十分な権限が必要です。**

## コントロールおよびラベルの定義 {#controls-labels}

[!UICONTROL Data Export Controls] は、データソースおよび宛先の分類に役立つ次のコントロールを提供します。

データ配信をブロックするには、書き出しコントロールを使用してデータソースを分類し、書き出しラベルを宛先に追加する必要があります。書き出しコントロールをデータソースまたは宛先のみに適用する場合、この機能は、データ配信を制限しません。When set on both the data source *and* destination, the export controls will limit the traits you can add to a segment and prevent sending the segment members to a destination.

また、データ配信制限を有効にする前に、少なくとも 1 つの書き出しラベルが書き出しコントロールに一致する必要があります。For example, say you add the [!UICONTROL PII] export control to a data source. 次に、オンサイトターゲット設定ラベルを宛先に追加します。この場合、書き出しコントロールは、設定が一致しないので、データ配信を制限しません。However, if you add the [!UICONTROL PII] export label to the destination, the export controls will block the export.

>[!IMPORTANT]
>
>[セグメントのデータソースにデータエクスポートコントロールを配置してセグメントのエクスポートをブロックすることはできません。次のいずれかの制御を設定する必要があります。
> * セグメントで使用される特性のデータソース。
> * セグメントによって使用されるプロファイル結合ルール。
> * セグメントのプロファイル結合ルールで使用されるデータソース。


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> データソースのデータ書き出しコントロール </th> 
   <th colname="col2" class="entry"> 宛先のデータ書き出しラベル </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No restriction</span></b> </td> 
   <td colname="col2"> なし </td> 
   <td colname="col3"> デフォルトでは、新しいデータソースおよび宛先に書き出し制限が設定されていません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Cannot be tied to personally identifiable information</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> This destination may enable a combination with personally identifiable information (PII)</span></b> </td> 
   <td colname="col3">選択すると、以下のことができなくなります。 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">PII を使用する宛先にマッピングされたセグメントへの特性の追加。 </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">特性で構築したセグメントを、PIIを使用するデータソースから宛先にマップします。 </li> 
    </ul> <p>これは、多くの場合、サードパーティデータプロバイダーで必要になり、広告／メディア追跡情報を含むデータソースを使用する場合にも必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Cannot be used for on-site ad targeting</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> This destination may be used for on-site ad targeting</span></b> </td> 
   <td colname="col3">選択すると、以下のことができなくなります。 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">訪問者の Web ブラウジング履歴に基づいて広告配信をカスタマイズする宛先にマッピングされたセグメントへの特性の追加。 </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">訪問者のWeb閲覧履歴に基づいて広告配信をカスタマイズする宛先に、特性で構築されたセグメントをデータソースからマッピングします。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Cannot be used for off-site ad targeting</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> This destination may be used for off-site ad targeting</span></b> </td> 
   <td colname="col3">これらの制限が一般的に使用され、選択すると、以下のことができなくなります。 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">他のサイトのユーザーを再ターゲット化する宛先にマッピングされたセグメントへの特性の追加。 </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">特性で構築されたセグメントを、他のサイトのユーザーを再ターゲット化する宛先にデータソースからマッピングします。 </li> 
    </ul> <p>多くの場合、ソーシャルメディアプラットフォームからのデータを扱う際に必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Cannot be used for on-site personalization</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> This destination may be used for on-site ad personalization</span></b> </td> 
   <td colname="col3">選択すると、以下のことができなくなります。 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">ユーザーの興味または Web ブラウジング履歴に基づいてコンテンツをカスタマイズする宛先にマッピングされたセグメントへの特性の追加。 </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">ユーザーの興味またはWeb閲覧履歴に基づいてコンテンツをカスタマイズする宛先に、特性で構築されたセグメントをデータソースからマッピングします。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## ワークフロー {#workflow}

開始するには、データソースおよび宛先のドキュメントを確認します。これらの記事では、書き出しコントロールおよびラベルのデータソースおよび宛先への追加方法を説明しています。

* [データソースの作成](../features/manage-datasources.md#create-data-source)
* [宛先へのデータ書き出しラベルの追加](../features/destinations/manage-destinations.md#add-data-export-labels)