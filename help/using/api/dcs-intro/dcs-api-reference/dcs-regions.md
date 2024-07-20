---
description: DCS の呼び出しをおこなうには、地域 DCS サーバーのホスト名が必要です。DCS では、サイト訪問者に地理的に近いデータセンターに情報を保存するからです。間違った DCS にクエリを送信しても機能しますが、そのような呼び出しは非効率的で、応答の遅延につながるおそれがあります。DCS リクエストをおこなうには、地域 ID を対応する地域ホスト名に合わせ、適切なホスト名でクエリを作成します。
seo-description: The regional DCS server host name is required to make calls to the DCS. This is because the DCS stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong DCS, but these calls are inefficient and can delay the response. To make a DCS request, match the region ID to its corresponding regional host name and form your query with the proper host name.
seo-title: DCS Region IDs, Locations, and Host Names
solution: Audience Manager
title: DCS の地域 ID、場所、ホスト名
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 100%

---

# DCS の地域 ID、場所、ホスト名 {#dcs-region-ids-locations-and-host-names}

[!DNL DCS] の呼び出しをおこなうには、地域 [!DNL DCS] サーバーのホスト名が必要です。[!DNL DCS] では、サイト訪問者に地理的に近いデータセンターに情報を保存するからです。間違った [!DNL DCS] にクエリを送信しても機能しますが、そのような呼び出しは非効率的で、応答の遅延につながるおそれがあります。[!DNL DCS] 要求をおこなうには、地域 ID を対応する地域ホスト名に合わせ、適切なホスト名でクエリを作成します。

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS 地域 ID（dcs_region） </th> 
   <th colname="col2" class="entry"> 地域（場所） </th> 
   <th colname="col3" class="entry"> ホスト名 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>東南アジア（シンガポール） </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 4 </p> </td> 
   <td colname="col2"> <p>南アメリカ（サンパウロ、ブラジル） </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>ヨーロッパ（ダブリン、アイルランド） </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>米国東部（バージニア、米国） </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>南太平洋地域／オセアニア（シドニー、オーストラリア） </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>米国西部（オレゴン、米国） </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>アジア（東京、日本） </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID 12 </p> </td> 
   <td colname="col2"> <p>インド </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL API] メソッドを使用して、利用可能な [!DNL DCS] 地域のリストを取得することもできます。[DCS 地域 API メソッド](../../../api/rest-api-main/aam-api-dcs-regions.md)を参照してください。
