---
description: キー値ペアは関連する要素（キーと値）で構成されます。キーは、データセットを定義する定数（例：性別、色、価格など）です。値は、そのセットに属する変数（例：男性／女性、緑、100 など）です。Destination Builder では、キー値ペアの形式でデータを送信します。
seo-description: キー値ペアは関連する要素（キーと値）で構成されます。キーは、データセットを定義する定数（例：性別、色、価格など）です。値は、そのセットに属する変数（例：男性／女性、緑、100 など）です。Destination Builder では、キー値ペアの形式でデータを送信します。
seo-title: 標準型およびシリアル型のキー値ペア
solution: Audience Manager
title: 標準型およびシリアル型のキー値ペア
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Destination Basics
translation-type: ht
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: ht
source-wordcount: '602'
ht-degree: 100%

---


# 標準型およびシリアル型のキー値ペア {#standard-and-serial-key-value-pairs}

キー値ペアは関連する要素（キーと値）で構成されます。キーは、データセットを定義する定数（例：性別、色、価格など）です。値は、そのセットに属する変数（例：男性／女性、緑、100 など）です。[!UICONTROL Destination Builder] では、キー値ペアの形式でデータを送信します。

## 基本的なキーと値のペア {#basic-key-value-pairs}

完全な形式の、基本的なキーと値のペアは次のようになります。

* `gender = male`
* `color = green`
* `price > 100`

## 標準型およびシリアル型のキー値ペア {#standard-serial-key-value-pairs}

宛先はキーと値のデータを *`standard`* または *`serialized`* 形式で受け取ります。

* **標準型のキーと値のペア：**&#x200B;宛先データをそれぞれ別個のキーと値のペアとして設定します。各キーは、明示的に指定されます（異なる値を定義するために再利用される場合でも）。
* **シリアル型の値のペア：**&#x200B;複数の値が 1 つのキーと値のペアにまとめられます。シリアル型のキーと値のペアでは、特殊なインジケーターにより、このキーと値のセットの中にある値が区切られます。

標準型とシリアル型のどちらのキーと値のペアでも、1 つ以上の値を受け入れることができます。標準およびシリアル化されたキー値形式の例を次の表に示します。

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フォーマット </th>
   <th colname="col2" class="entry"> 1 つのキーと値のペア </th>
   <th colname="col3" class="entry"> 複数のキーと値のペア </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>標準</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>シリアル型</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## デリミターとセパレーター {#delimiters-separators}

キーと値の中間の値と、キーと値の間を区切る文字は、*`delimiters`* および *`separators`* です。これは、セグメントをシリアル形式で宛先に送信する場合に特に重要です。シリアル化により、複数の値を 1 つのキーで渡し、キーと値のペアを結合できるようになります。デリミターとセパレーターは次のように定義されます。

* **キーと値のセパレーター：**&#x200B;キーと値のペアの中のキーと値を区切ります。
* **キーと値のデリミター：**&#x200B;キーと値のペアの組を区切ります。
* **シリアルセパレーター：**&#x200B;シリアル型のキーと値のペアの組の中にある複数の値を区切ります。

## 例 {#examples}

[!UICONTROL Destination Builder]では、キーと値のデータを複数の形式で設定できます。各タイプの例を紹介します。

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> キーと値のペアの例 </th> 
   <th colname="col2" class="entry"> 例 </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>標準的な単一キー</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>キーと値のペアの単純なセット。この例には次の要素があります。 </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">キー：X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">値：1、2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">セパレーター：= </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">キーと値のデリミター：&amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>複数のキーと値のペア</b>（非シリアル型） </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>複数のキーと値の組。個別のキーと値の組で値を渡します。この例には次の要素があります。 </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">キー：X、Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">値：1、2、3、4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">セパレーター：= </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">キーと値のデリミター：&amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>シリアル型の単一キー</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>1 つのキーと値の組。複数の値を 1 つのキーで渡します。このキーには複数の値があるので、「シリアル化されたキーと値のペア」と呼ばれています。この例には次の要素があります。 </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">キー：X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">値：1、2、3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">セパレーター：= </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">シリアル区切り文字：セミコロン </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>複数のキーと値のペア</b>（シリアル型） </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>複数のキーと値のペアのセット。複数の値を個別のキーで渡します。この例には次の要素があります。 </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">キー：X、Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">値：1、2、3、4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">セパレーター：= </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">区切り：&amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">シリアル区切り文字：セミコロン </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 宛先のシリアル化 {#destination-serialized}

宛先のシリアル化では、複数の特性を結合して単一の文字列にし、その情報を宛先に送信します。

<!-- c_dest_serialized.xml -->

シリアル化されたデータの送信は、複数の特性が同時にではなく連続して処理されるので、効率性の向上に役立ちます。これにより、追加のリクエストに応答する前に、データを受信し処理して返すのに十分な時間が宛先サーバーに提供されます。

### サポートされる宛先

[!DNL Audience Manager] では、データをシリアル化して、対象となるほとんどあらゆる宛先に送信できます。ただし、この機能を使用する前に、宛先 [!DNL URL] と、必須またはオプションのマクロの挿入位置を知っておく必要があります。宛先パートナーから、マクロの位置に関する情報を入手します。詳しくは、[宛先マクロの定義](../../features/destinations/destination-macros.md#destination-macros-defined)を参照してください。