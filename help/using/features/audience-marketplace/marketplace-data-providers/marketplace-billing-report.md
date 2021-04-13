---
description: Audience Marketplace 請求レポートを生成して、加入者ごとの前月のデータフィード使用量を表示できます。前月のレポートはいつでも作成できます。ただし、当月の 10 日以降にレポートを生成したほうがレポートが正確になります。
seo-description: Audience Marketplace 請求レポートを生成して、加入者ごとの前月のデータフィード使用量を表示できます。前月のレポートはいつでも作成できます。ただし、当月の 10 日以降にレポートを生成したほうがレポートが正確になります。
seo-title: データフィードプロバイダーに対する請求
solution: Audience Manager
title: データフィードプロバイダーに対する請求
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 100%

---

# データフィードプロバイダーに対する請求 {#billing-for-data-feed-providers}

[!DNL Audience Marketplace] 請求レポートを生成すると、サブスクリプション購入者ごとに前月のデータフィードの使用状況を確認できます。前月のレポートはいつでも作成できます。ただし、当月の 10 日以降にレポートを生成したほうがレポートが正確になります。

## 請求レポートのダウンロード  {#download-billing-report}

レポートをダウンロードするには、次の手順を実行します。

1. **[!UICONTROL Audience Marketplace > Receivables]** へ移動します。
1. 「**[!UICONTROL Generate Billing Report]**」をクリックします。

## 定義されているレポートのフィールド {#report-fields-defined}

請求レポートには以下の情報が記載されます。

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> レポートのフィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data Provider PID</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> のデータプロバイダー ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data Provider Name</span></b> </p> </td> 
   <td colname="col2"> <p>会社名または組織名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Buyer PID</span></b> </p> </td> 
   <td colname="col2"> <p>バイヤー（購読者）ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Buyer Name</span></b> </p> </td> 
   <td colname="col2"> <p>バイヤーの会社名または組織名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Feed ID</span></b> </p> </td> 
   <td colname="col2"> <p>データフィードの ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Feed Name</span></b> </p> </td> 
   <td colname="col2"> <p>データフィードの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Plan Use Cases</span></b> </p> </td> 
   <td colname="col2"> <p>販売者は、購入者がどのようにデータを使用できるかをユースケースにより制御できます。オプションは次のとおりです。 </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">セグメントと重複 </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">モデリング </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">アクティベーション </li> 
    </ul> <p><a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types">データフィードのプランタイプ</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unit of Measure</span></b> </p> </td> 
   <td colname="col2"> <p>CPM 請求か定額請求かを表します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> List Price</span></b> </p> </td> 
   <td colname="col2"> <p>各データフィードの購読料金。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Discounted Price</span></b> </p> </td> 
   <td colname="col2"> <p>割引データフィードの購読料金。詳しくは、<a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> データプロバイダーにとっての割引</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 購入点数</span></b> </p> </td> 
   <td colname="col2"> <p>フィードの価格タイプによって異なります。 </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">定額データフィード：1 のみが返されます。 </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM データフィード：CPM データフィードの実際の使用量が返されます。購読者が CPM フィードのインプレッションデータを提供していない場合、「Units」セルは空で、「Flag」セルは 1 に設定されます。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Total Cost</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> がバイヤーに請求する金額。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Billing Period</span></b> </p> </td> 
   <td colname="col2"> <p> このレポートでは、前月の末日です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Entry Date</span></b> </p> </td> 
   <td colname="col2"> <p>バイヤーが購読／使用状況情報を入力した日付。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Subscription Start Date</span></b> </p> </td> 
   <td colname="col2"> <p>バイヤーがデータフィードの購読を開始した日付。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Subscription End Date</span></b> </p> </td> 
   <td colname="col2"> <p>バイヤーがデータフィードの購読を終了した日付。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Flag</span></b> </p> </td> 
   <td colname="col2"> <p> <i>CPM フィードの場合のみ</i>。「Flag」のオプションは次のとおりです。 </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0：購読者が <span class="keyword">Audience Manager</span> に使用状況情報を報告したことを表します。 </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1：購読者が <span class="keyword">Audience Manager</span> に使用状況情報を報告していないことを表します。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [CPM データフィードの請求とインプレッション割り当て](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [定額データフィードに関する請求およびインプレッションの割り当て](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [CPM の使用状況の報告方法](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

