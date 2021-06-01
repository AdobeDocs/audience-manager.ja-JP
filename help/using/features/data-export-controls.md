---
description: 宛先へのデータ送信がデータプライバシーやデータ使用契約に違反する場合、データ書き出しコントロールはデータ送信を防止します。
seo-description: 宛先へのデータ送信がデータプライバシーやデータ使用契約に違反する場合、データ書き出しコントロールはデータ送信を防止します。
seo-title: データ書き出しコントロール
solution: Audience Manager
title: データ書き出しコントロール
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: データ書き出しコントロール
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 100%

---

# データ書き出しコントロール {#data-export-controls}

宛先へのデータ送信がデータプライバシーやデータ使用契約に違反する場合、[!UICONTROL Data Export Controls]はデータ送信を防止します。

## 概要 {#overview}

[!UICONTROL Data Export Controls]を使用すれば、[データソース](../features/datasources-list-and-settings.md#data-sources-list-and-settings)と[宛先](../features/destinations/destinations.md)を分類することができます。適用する分類によって、データを宛先に書き出せる場合または書き出せない場合が決まります。この機能は、以下で構成されます。

* **[!UICONTROL Data Export Controls]**：*データソース*&#x200B;に対してデータ書き出しコントロールを設定できます。データソースに対して設定すると、これらのコントロールがデータソースおよびその特性の使用方法を制限します。
* **[!UICONTROL Data Export Labels]**：*宛先*&#x200B;に対してデータの書き出しラベルを設置できます。宛先に対して設定すると、宛先でのデータの使用方法がこれらのラベルで識別されます。宛先へのラベルの書き出し方法について詳しくは、[宛先へのデータ書き出しラベルの追加](/help/using/features/destinations/add-data-export-labels.md)を参照してください。

データソースおよび宛先に適用した分類に基づいて、書き出しコントロールは以下の操作を防止します。

* セグメントがマッピングされている 1 つ以上の宛先で、データ書き出しラベルと互換性がないデータ書き出しコントロールを使用するデータソースに特性が属している場合、特性をセグメントに追加します。
例えば、あるセグメントが、書き出しラベル「**[!DNL This destination may enable a combination with personally identifiable information (PII)]**」を使用して宛先にマッピングされるとします。特性が属するデータソースが「**[!DNL Cannot be tied to personally identifiable information (PII)]**」というラベルの付いたデータ書き出しコントロールを使用している場合、書き出しコントロールは、そのセグメントに特性を追加するのを中止します。
* 次のいずれかに対して、データ書き出しコントロールでブロックされているデータ書き出しラベルが付いた宛先にデータを送信する場合：
   * 含まれる特性のデータソース。
   * 含まれるセグメントで使用される特性のデータソース。
   * 含まれるセグメントで使用されるプロファイル結合ルール。
   * 含まれるセグメントのプロファイル結合ルールに使用されるデータソース。

[!UICONTROL Data Export Controls] は、すべての Audience Manager ユーザーに対して自動的に使用できます。ただし、書き出しコントロールをデータソースに追加するには、管理者権限が必要です。書き出しラベルを宛先に追加するには、管理者権限または宛先を作成または編集するための十分な権限が必要です。**

## コントロールおよびラベルの定義  {#controls-labels}

[!UICONTROL Data Export Controls]は、データソースおよび宛先を分類するのに役立つ、以下のコントロールを提供します。

データ配信をブロックするには、書き出しコントロールを使用してデータソースを分類し、書き出しラベルを宛先に追加する必要があります。書き出しコントロールをデータソースまたは宛先のみに適用する場合、この機能は、データ配信を制限しません。データソース&#x200B;*と*&#x200B;宛先の両方に設定すると、書き出しコントロールは、セグメントに追加できる特性を制限し、セグメントのメンバーが宛先に送信されないようにします。

また、データ配信制限を有効にする前に、少なくとも 1 つの書き出しラベルが書き出しコントロールに一致する必要があります。例えば、[!UICONTROL PII] 書き出しコントロールをデータソースに追加するとします。次に、オンサイトでのターゲティングラベルを宛先に追加します。この場合、書き出しコントロールは、設定が一致しないので、データ配信を制限しません。ただし、[!UICONTROL PII] 書き出しラベルを宛先に追加した場合は、書き出しコントロールが機能します。

>[!IMPORTANT]
>
>セグメントのデータソースに対してデータ書き出しコントロールを設定し、セグメントのエクスポートをブロックすることはできません。次のいずれかのコントロールを設定する必要があります。
> * セグメントで使用される特性のデータソース。
> * セグメントで使用されるプロファイル結合ルール。
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
   <td colname="col1"> <b><span class="uicontrol">制限なし</span></b> </td> 
   <td colname="col2"> なし </td> 
   <td colname="col3"> デフォルトでは、新しいデータソースおよび宛先に書き出し制限が設定されていません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Cannot be tied to personally identifiable information</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol">この宛先は個人情報（PII）との組み合わせを有効にすることができます</span></b> </td> 
   <td colname="col3">選択すると、以下のことができなくなります。 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">PII を使用する宛先にマッピングされたセグメントへの特性の追加。 </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">データソースの特性を使用して構築したセグメントを、PII を使用する宛先にマッピングする。 </li> 
    </ul> <p>これは、多くの場合、サードパーティデータプロバイダーで必要になり、広告／メディア追跡情報を含むデータソースを使用する場合にも必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">オンサイト広告ターゲティングに使用することはできません</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol">この宛先はオンサイト広告ターゲティングに使用できます</span></b> </td> 
   <td colname="col3">選択すると、以下のことができなくなります。 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">訪問者の Web ブラウジング履歴に基づいて広告配信をカスタマイズする宛先にマッピングされたセグメントへの特性の追加。 </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">データベースの特性を使用して構築されたセグメントを、訪問者の Web 閲覧履歴に基づいて広告配信をカスタマイズする宛先にマッピングします。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">オフサイト広告ターゲティングに使用することはできません</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol">この宛先はオフサイト広告ターゲティングに使用できます</span></b> </td> 
   <td colname="col3">これらの制限が一般的に使用され、選択すると、以下のことができなくなります。 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">他のサイトのユーザーを再ターゲット化する宛先にマッピングされたセグメントへの特性の追加。 </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">データソースの特性を使用して構築したセグメントを、他のサイトのユーザーをリターゲティングする宛先にマッピングする。 </li> 
    </ul> <p>多くの場合、ソーシャルメディアプラットフォームからのデータを扱う際に必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">オンサイトのパーソナライズ機能に使用することはできません</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol">この宛先は、オンサイト広告パーソナライズ機能に使用できます</span></b> </td> 
   <td colname="col3">選択すると、以下のことができなくなります。 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">ユーザーの興味または Web ブラウジング履歴に基づいてコンテンツをカスタマイズする宛先にマッピングされたセグメントへの特性の追加。 </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">データベースの特性を使用して構築されたセグメントを、ユーザーの関心または Web 閲覧履歴に基づいてコンテンツをカスタマイズする宛先にマッピングします。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## ワークフロー {#workflow}

開始するには、データソースおよび宛先のドキュメントを確認します。これらの記事では、書き出しコントロールおよびラベルのデータソースおよび宛先への追加方法を説明しています。

* [データソースの作成](../features/manage-datasources.md#create-data-source)
* [宛先へのデータ書き出しラベルの追加](../features/destinations/add-data-export-labels.md)
