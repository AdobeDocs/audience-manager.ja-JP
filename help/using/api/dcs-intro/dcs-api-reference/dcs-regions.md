---
description: DCS の呼び出しをおこなうには、地域 DCS サーバーのホスト名が必要です。DCS では、サイト訪問者に地理的に近いデータセンターに情報を保存するからです。間違った DCS にクエリを送信しても機能しますが、そのような呼び出しは非効率的で、応答の遅延につながるおそれがあります。DCS 要求をおこなうには、地域 ID を対応する地域ホスト名に合わせ、適切なホスト名でクエリを作成します。
seo-description: DCS の呼び出しをおこなうには、地域 DCS サーバーのホスト名が必要です。DCS では、サイト訪問者に地理的に近いデータセンターに情報を保存するからです。間違った DCS にクエリを送信しても機能しますが、そのような呼び出しは非効率的で、応答の遅延につながるおそれがあります。DCS 要求をおこなうには、地域 ID を対応する地域ホスト名に合わせ、適切なホスト名でクエリを作成します。
seo-title: DCS の地域 ID、場所、ホスト名
solution: Audience Manager
title: DCS の地域 ID、場所、ホスト名
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS の地域 ID、場所、ホスト名 {#dcs-region-ids-locations-and-host-names}

[!UICONTROL DCS] の呼び出しをおこなうには、地域 [!UICONTROL DCS] サーバーのホスト名が必要です。[!UICONTROL DCS] では、サイト訪問者に地理的に近いデータセンターに情報を保存するからです。間違った [!UICONTROL DCS] にクエリを送信しても機能しますが、そのような呼び出しは非効率的で、応答の遅延につながるおそれがあります。[!UICONTROL DCS] 要求をおこなうには、地域 ID を対応する地域ホスト名に合わせ、適切なホスト名でクエリを作成します。

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
   <td colname="col3"> <p> <code> ind1. demdex. net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL API] また、使用可能 [!UICONTROL DCS] な領域のリストを取得する方法もあります。[DCS 地域 API メソッド](../../../api/rest-api-main/aam-api-dcs-regions.md)を参照してください。