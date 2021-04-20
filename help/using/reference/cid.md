---
description: d_dpid および d_dpuuid の代わりに d_cid または d_cid_ic を使用するようにコードを更新します。DPID および DPUUID 変数は引き続き機能しますが、これらは既に廃止されています。DPID や DPUUID の、d_ プレフィックスが付かないバージョンも同様です。
seo-description: d_dpid および d_dpuuid の代わりに d_cid または d_cid_ic を使用するようにコードを更新します。DPID および DPUUID 変数は引き続き機能しますが、これらは既に廃止されています。DPID や DPUUID の、d_ プレフィックスが付かないバージョンも同様です。
seo-title: DPID と DPUUID に代わる CID
solution: Audience Manager
title: DPID と DPUUID に代わる CID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: Reference
exl-id: 18e6b1db-fe51-4560-9458-8d65474d2506
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 100%

---

# DPID と DPUUID に代わる CID {#cid-replaces-dpid-and-dpuuid}

`d_dpid` や `d_dpuuid` の代わりに `d_cid` または `d_cid_ic` を使用するようにコードを更新してください。DPID および DPUUID 変数は引き続き機能しますが、これらは既に廃止されています。DPID や DPUUID の、`d_ prefix`が付かないバージョンも同様です。

## DPID と DPUUID：復習 {#dpid-dpuuid-review}

DPID と DPUUID は、データプロバイダー ID とユーザー ID で構成されるキー値ペアです。これらのキー値ペアは、プロバイダー ID をユーザー ID にリンクするためのものです。これらはイベント呼び出し、受信同期イベント、ID 呼び出しの場合にデータの一部として送信されます。これらがなければ、[!DNL Audience Manager] などのサービスや機能は、ID を照合し同期させる方法がありません。これらの変数には、以下のように、`d_` プレフィックスが付く場合も付かない場合もあります。なお、コードの&#x200B;*斜体*&#x200B;の部分には実際の情報が入ります。

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数 </th> 
   <th colname="col2" class="entry"> 構文 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>データプロバイダー ID（DPID） </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>データプロバイダー一意のユーザー ID（DPUUID） </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

これらのキー値ペアはまだ機能しますが、廃止されています。代わりに CID または CID_IC を使用するようにコードを更新してください。

## CID と CID_IC：概要  {#cid-cidic-about}

CID および CID_IC キー値ペアは DPID と DPUUID に取って代わるものです。これらは DPID や DPUUID と同じ機能を提供しますが、データプロバイダー ID（または統合コード）とユーザー ID が 1 つのキー値ペアに含まれているので、より効率的です。それぞれのキー値ペアでは、以下がおこなわれます。

* キーとそれに関連する値が = 記号で区切られます。
* 非印字 ASCII 文字 %01 で値が区切られます。

`d_cid` と `d_cid_ic` では以下の構文を使用します。なお、コードの&#x200B;*斜体*&#x200B;の部分には実際の情報が入ります。

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数 </th> 
   <th colname="col2" class="entry"> 構文 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>顧客 ID（CID） </p> </td> 
   <td colname="col2"> <p> <code>d_cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>顧客 ID 統合コード（CID_IC） </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> <span class="term"> integration code</span> は、データソース ID の代わりに使用できる代替 ID で、<span class="keyword">Audience Manager</span> によって割り当てられます。統合コードを設定する必要がある場合は、<a href="../features/manage-datasources.md#create-data-source">データソースの作成</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

また、[宣言された ID の URL 変数および構文](../features/declared-ids.md#variables-and-syntax)も参照してください。

>[!NOTE]
>
>統合コードは、独自のデータソースとアクセス可能なグローバル [共有データソース](../features/datasources-list-and-settings.md#settings-menu-options)に使用することができます。例えば、モバイル識別子データソースを扱う際に統合コードを使用できます。次の統合コードを以下の指定どおりに使用します。

* **DSID_20914**（GAID 用）：Android オペレーティングシステムを搭載したデバイスを表します。
* **DSID_20915**（IDFA 用）：iOS オペレーティングシステムを搭載したデバイスを表します。

**例**

次の表にイベントタイプ別に例を示します。

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Event Type </th> 
   <th colname="col2" class="entry"> 例 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>イベント </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">新規: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">廃止：<code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>受信同期（IBS） </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">新規: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">廃止：<code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID（ID）の生成 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">新規: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">廃止：<code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

各呼び出しには、次のように、複数の `d_cid` および `d_cid_ic` キー値ペアを含めることもできます｡

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## 開発チーム向けの重要な考慮事項 {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>項目 </p> </th> 
   <th colname="col2" class="entry"> <p>説明 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>URLエンコード </p> </td> 
   <td colname="col2"> <p>開発チームは、CID キー値ペアの次の変数に URL エンコーディングを適用する<i>必要</i>があります。 </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>注意：ユーザー ID と統合コードを URL エンコードして<i>から</i>、連結して文字列にする必要があります。これは、2 つの変数を区切っている ASCII 文字 %01 を URL エンコーディングで表現してはいけないからです。 </p> </p> <p>URL エンコーディングによって、+ や = などの予約済みの文字や安全でない文字を含んだユーザー ID や統合コードをサーバーに正しく送信できるようになります。 </p> <p><a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external">ASCII エンコーディング表</a>を参考にしてください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>グローバル共有データソースへの統合コードの使用 </p> </td> 
   <td colname="col2"> <p>統合コードは、独自のデータソースとアクセス可能なグローバル <a href="../features/datasources-list-and-settings.md#settings-menu-options">共有データソース</a>に使用することができます。例えば、モバイル識別子データソースを扱う際に統合コードを使用できます。次の統合コードを以下の指定どおりに使用します。 </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_20914</b>（GAID 用）：Android オペレーティングシステムを搭載したデバイスを表します。 </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b>（IDFA 用）：iOS オペレーティングシステムを搭載したデバイスを表します。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
