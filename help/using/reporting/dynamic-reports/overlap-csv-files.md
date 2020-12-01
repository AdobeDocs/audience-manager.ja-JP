---
description: 重複レポートがレコード数の上限（100 万件）に達した場合は、そのレポートの .csv ファイルを請求することができます。「Unexpected error has occurred」というメッセージが表示された場合、レポートは、この制限に達している可能性があります。カスタマーケアに連絡して、圧縮した .csv ファイルを請求してください。このファイルを独自のデータベースシステムにインポートして操作することができます。セグメント間、セグメント／特性間、特性間の重複レポートのファイルが入手可能です。
seo-description: 重複レポートがレコード数の上限（100 万件）に達した場合は、そのレポートの .csv ファイルを請求することができます。「Unexpected error has occurred」というメッセージが表示された場合、レポートは、この制限に達している可能性があります。カスタマーケアに連絡して、圧縮した .csv ファイルを請求してください。このファイルを独自のデータベースシステムにインポートして操作することができます。セグメント間、セグメント／特性間、特性間の重複レポートのファイルが入手可能です。
seo-title: 重複レポートの CSV ファイル
solution: Audience Manager
title: 重複レポートの CSV ファイル
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
feature: overlap reports
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 100%

---


# 重複レポートの CSV ファイル {#csv-files-for-overlap-reports}

重複レポートがレコード数の上限（100 万件）に達した場合は、そのレポートの .csv ファイルを請求することができます。「Unexpected error has occurred」というメッセージが表示された場合、レポートは、この制限に達している可能性があります。カスタマーケアに連絡して、圧縮した .csv ファイルを請求してください。このファイルを独自のデータベースシステムにインポートして操作することができます。セグメント間、セグメント／特性間、特性間の重複レポートのファイルが入手可能です。

## ファイル名のメタデータ {#file-name-metadata}

次の表は、重複 .csv ファイルの命名規則とファイル拡張子の一覧と説明です。以下の例で、*斜体*&#x200B;の部分には実際の情報が入ります。

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> メタデータの要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ファイル拡張子 </p> </td> 
   <td colname="col2"> <p>重複レポートファイルは gzip 形式で圧縮され、ファイル拡張子は <code> .gz</code> になります。解凍後は <code> .csv</code> 拡張子をファイルに追加する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイル名 </p> </td> 
   <td colname="col2"> <p>ファイル名の構文は次のとおりです。 </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">セグメント間ファイル：<code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">セグメント／特性間ファイル：<code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">特性間ファイル：<code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日付範囲 </p> </td> 
   <td colname="col2"> <p>レポートの日付範囲は 5 桁の ID で表されます。 </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code>：7 日間のレポート。 </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code>：30 日間のレポート。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>複数のファイル </p> </td> 
   <td colname="col2"> <p>レポートに複数のファイルがある場合、ファイル名の最後の桁を増加させます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>例 </p> </td> 
   <td colname="col2"> <p>レポートが 1 つの場合のファイル名の例： </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">7 日間のファイル（1 つ）：<code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">30 日間のファイル（1 つ）：<code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>複数のファイルがあるレポートのファイル名の例： </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## ファイルコンテンツ {#file-contents}

ファイル内では、文字列データは二重引用符で囲まれます。以下のモックデータを参照してください。これは短く画面内に収まるように切り捨てられています。

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## セグメント間レポートのレコード  {#segment-segment-records}

[セグメント間重複レポート](segment-segment-overlap-report.md)のデータファイルには、次のレコードが含まれています。

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ラベル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id1</code> </p> </td> 
   <td colname="col2"> <p>ベースラインセグメントと比較するセグメントの ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>ベースラインセグメントと比較するセグメントの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>ベースラインセグメントの ID。ベースラインセグメントは、他のセグメントとの比較に使用するセグメントです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>他のセグメントと比較するベースラインセグメントの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>7 日および 30 日のルックバック間隔でレポートを生成できます。<code> rangeid</code> は以下の時間間隔に対応します。 </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code> ：7 日 </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code> ：30 日 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>レポートの処理日。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques1</code> </p> </td> 
   <td colname="col2"> <p>ベースラインセグメントと比較するセグメントの個別ユーザーの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>ベースラインセグメントの個別ユーザーの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>ベースラインセグメントと、比較の対象となる他のセグメントとの間の、重複する個別ユーザーの合計数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>ベースラインセグメントと、比較の対象となる他のセグメントとの間の、重複する個別ユーザーの割合。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## セグメント - 特性間レポートのレコード  {#segment-trait-records}

[セグメント - 特性間重複レポート](segment-trait-overlap-report.md)のデータファイルには、次のレコードがあります。

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ラベル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_id</code> </p> </td> 
   <td colname="col2"> <p>特性 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>特性名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>データプロバイダー ID。ID には次のものがあります。 </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1st Party</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>データプロバイダーの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>7 日および 30 日のルックバック間隔でレポートを生成できます。<code> rangeid</code> は以下の時間間隔に対応します。 </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code> ：7 日 </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code> ：30 日 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>レポートの処理日。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques</code> </p> </td> 
   <td colname="col2"> <p>選択したセグメントの個別ユーザーの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>特性内の個別ユーザーの数。UI レポートでは、ヒートマップの結果で特性の上にカーソルを移動すると、ポップアップウィンドウにこの数字が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>選択したセグメントと特性の間で共有されている個別ユーザーの数。UI レポートでは、ヒートマップの結果で特性の上にカーソルを移動すると、ポップアップウィンドウにこの数字が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>特性とセグメントの間で重複する個別ユーザーの割合。UI レポートでは、ヒートマップの結果で特性の上にカーソルを移動すると、ポップアップウィンドウにこの数字が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>セグメントと特性の間で重複する個別ユーザーの割合。UI レポートでは、ヒートマップの結果で特性の上にカーソルを移動すると、ポップアップウィンドウにこの数字が表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 特性間レポートのレコード  {#trait-trait-records}

[特性間重複レポート](trait-trait-overlap-report.md)には、次のレコードがあります。

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ラベル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_id</code> </p> </td> 
   <td colname="col2"> <p>ベースライン特性と比較する特性の ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
   <td colname="col2"> <p>ベースライン特性と比較する特性の名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>ベースライン特性の ID。ベースライン特性は、他の特性と比較する特性です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>他の特性との比較に使用するベースラインの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>データプロバイダー ID。ID には次のものがあります。 </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1st Party</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>データプロバイダーの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>7 日および 30 日のルックバック間隔でレポートを生成できます。<code> rangeid</code> は以下の時間間隔に対応します。 </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code> ：7 日 </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code> ：30 日 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>レポートの処理日。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>選択した特性の間で共有されている個別ユーザーの数。UI レポートでは、ヒートマップの結果で特性の上にカーソルを移動すると、ポップアップウィンドウにこの数字が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>ベース特性の個別ユーザーの数。UI レポートでは、ヒートマップの結果で特性の上にカーソルを移動すると、ポップアップウィンドウにこの数字が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>選択した特性の間で共有されている個別ユーザーの数。UI レポートでは、ヒートマップの結果で特性の上にカーソルを移動すると、ポップアップウィンドウにこの数字が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>選択した特性の間で重複する個別ユーザーの割合。UI レポートでは、ヒートマップの結果で特性の上にカーソルを移動すると、ポップアップウィンドウにこの数字が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>選択した特性の間で重複する個別ユーザーの割合。UI レポートでは、ヒートマップの結果で特性の上にカーソルを移動すると、ポップアップウィンドウにこの数字が表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>
