---
description: このドキュメントでは、Audience Manager の一般データ保護規則（GDPR）に関する細かな規定を扱っており、GDPR 要求を Audience Manager に送信する方法も示しています。
seo-description: このドキュメントでは、Audience Manager の一般データ保護規則（GDPR）に関する細かな規定を扱っており、GDPR 要求を Audience Manager に送信する方法も示しています。
seo-title: Audience Manager の GDPR 対応
solution: Audience Manager
keywords: GDPR UI、GDPR API
title: Audience Manager の GDPR 対応
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: ht
source-git-commit: b32283a6cb3d001f0a1fc85f3e63fba651f32760

---


# Audience Manager の GDPR 対応 {#gdpr-in-audience-manager}

このドキュメントでは、Audience Manager の一般データ保護規則（GDPR）に関する細かな規定を扱っており、GDPR 要求を Audience Manager に送信する方法も示しています。

## Experience Cloud の GDPR ドキュメント {#gdpr-documentation}

Audience Manager の詳細を読む前に、次のリンクから、欧州における一般データ保護規則（GDPR）に関連する Experience Cloud の資料に目を通すことをお勧めします。

* [GDPR がビジネスに与える影響](https://www.adobe.com/jp/privacy/general-data-protection-regulation.html)
* [GDPR に関するホワイトペーパー](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [GDPR 関連の用語](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

以下の節では、Audience Manager に対する GDPR の影響、および Audience Manager に GDPR 要求を送信する方法について説明します。

## GDPR 要求のタイプと GDPR 要求の方法 {#types-of-gdpr-requests}

Audience Manager のお客様は、**プライバシーサービス UI**（[こちらの UI リンク](https://gdprui.cloud.adobe.io/)  および[こちらのドキュメント](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)）、または&#x200B;**プライバシーサービス API**（[こちらのドキュメント](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)および[こちらの API リファレンス](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)）のいずれかから、顧客データにアクセスまたは顧客データを削除する個別の GDPR 要求を送信できます。**[Audience Manager 識別子](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**&#x200B;セクションの説明に沿って、要求時に Audience Manager 識別子（ID）と対応する名前空間 ID（データソース ID）を送信できます。ご質問がある場合は、カスタマーケア（gdprsupport@adobe.com）にお問い合わせください。

## データへのアクセス{#access-data}

顧客の GDPR 要求は、受領後 30 日以内に処理することが掲げられていることを踏まえ、アドビでは、お客様からのデータアクセス要求をできるだけ早急に処理するよう努めています。

**リクエスト**

**プライバシーサービス UI**（[こちらの UI リンク](https://gdprui.cloud.adobe.io/)および[こちらのドキュメント](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)）、または&#x200B;**プライバシーサービス API**（[こちらのドキュメント](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)および[こちらの API リファレンス](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)）からデータアクセス要求を記録できます。いずれの場合も、送信するデータアクセス要求の Audience Manager 識別子が記述された JSON をアップロードする必要があります。整形式の JSON がどのように表示されるかを確認するには、**[JSON のサンプルをダウンロード](assets/access_request.json)**&#x200B;できます。

**応答**

データアクセス要求への応答には、特性とセグメントの合計数に関するサマリ、特性の種類、特性とセグメントの説明、およびそれぞれデータソース名が含まれます。アクセス応答には、ファーストパーティデータと共に、データ管理者がアクセスできるセカンドパーティおよびサードパーティのデータも含まれます。複数のデバイスにまたがる CRM ID や顧客の Cookie ID などの[!UICONTROL declared IDs] が GDPR 要求で送信された場合、関連付けられたすべてのデバイス（1 つの宣言済み ID につき最大 100 個のデバイス）からのアクセス応答も含まれます。

**応答ステータス**

Audience Manager からの応答でエラーが発生した場合、それらは応答内のエラーコードで示されます。[エラーコードのリスト](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)で返されるエラーの詳細を確認できます。

**応答の例**

以下がアクセス応答の一例となります。この例では、Cookie ID がデータ主体の ID です。それらはいくつかの特性に適合しており、いくつかのセグメントに属しています。Cookie ID はモバイル ID と関連付けられています。この例には使用している電話についてのメタデータも含まれています。

```
{
  "id": "45338264191156397602180946733455975613",
  "namespace": {
    "id": 0,
    "integration code": "",
    "data provider name": "Demdex, Inc",
    "type": "COOKIE"
  },
  "warnings": [{
    "title": "Device Data",
    "description": "Contains data from all users of this device"
  }],
  "data": {
    "traits": [{
      "name": "Website Visitors",
      "type": "1st party",
      "description": "All Active Visitors",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Interested in Italian Holidays",
      "type": "1st party",
      "description": "Query string contains holidays/bella_italia",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Lifestyle>Recreational>Garden Party",
      "type": "3rd party",
      "description": "Survey respondents that have expressed an interest in hosting garden parties",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:36"
    }],
    "segments": [{
      "name": "test",
      "description": "Interested in Photography",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "false"
    }, {
      "name": "Traveler and Frequent Flier",
      "description": "",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }, {
      "name": "Interested in Sports",
      "description": "",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }]
  },
  "links": [{
    "id": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2",
    "namespace": {
      "id": 20914,
      "integration code": "DSID_20914",
      "data provider name": "Google",
      "type": "MOBILE"
    },
    "linking datetime": "2018-04-10 17:00:37"
  }],
  "deviceMetadata": {
    "hardware": "Mobile Phone",
    "manufacturer": "Samsung",
    "marketing name": "Galaxy S8 Plus",
    "model": "",
    "os name": "Android",
    "os version": "7.0",
    "vendor": "Samsung"
  }
}
```

下の表は、データアクセス応答内で返されるすべてのフィールドの説明を含んでおり、順序は上記の応答コードに示したとおりです。

<table id="table_DF08231257F64588B98BD71A088C50DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>フィールド </p> </th> 
   <th colname="col2" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>リストされるデータのユーザー ID。これは GDPR データアクセス要求で指定した IDまたは指定した宣言済み ID のいずれかと関連付けられている ID のどちらかとなります。ID タイプについては、<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids">Audience Manager 識別子</a>セクションで説明しています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>データソースとも呼ばれます。<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids">Audience Manager 識別子</a>セクションを参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>名前空間／データソースの ID。指定できるすべての値については、<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids">Audience Manager 識別子（ID）</a>セクションを参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> integration code </code> </p> </td> 
   <td colname="col2"> <p>統合コードは、データソースのわかりやすい名前で、データソース ID を使用するより簡単にデータソースの追跡をおこなうことができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name </code> </p> </td> 
   <td colname="col2"> <p>データソースの所有者の名前。 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">ファーストパーティデータの場合、これは顧客自身の企業名となります。 </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">セカンドパーティデータの場合、これはパートナー企業の名前となります。 </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">サードパーティデータの場合、データパートナーの名前となります。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>GDPR データアクセスを要請した ID のタイプ。指定できるタイプについては、<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids">Audience Manager 識別子</a>セクションで説明しています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> warnings</code> </p> </td> 
   <td colname="col2"> <p>警告は、データアクセス要求に関連する詳細情報を返します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> title </code> </p> </td> 
   <td colname="col2"> <p>警告に関する簡単な情報。 </p> <p>警告には以下の 2 種類があります。 </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">デバイスデータ </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">不完全な要求 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>受信した警告のより詳細な説明： </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">デバイスデータ - このデバイスのすべてのユーザーのデータが含まれています。 </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">不完全な要求 - Audience Manager データの取得が完了しませんでした。一部の情報が欠落している可能性があります。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data </code> </p> </td> 
   <td colname="col2"> <p>ユーザー ID と関連付けられた特性とセグメント。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>ユーザー ID と関連付けられた特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>特性の名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>特性のタイプ。次のいずれかの値となります。 </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> お客様独自の特性の場合、<i>ファーストパーティ</i>。 </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> パートナーに属する特性の場合、<i>セカンドパーティ</i>。詳細については、<a href="../../overview/data-types-collected.md#second-party-data">セカンドパーティデータ</a>に関する記事をお読みください。 </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <a href="../../features/audience-marketplace/audience-marketplace.md">Audience Marketplace</a> を介してデータパートナーから取得した特性の場合、<i>サードパーティ</i>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>特性の目的や機能を説明する短い文章。これはオプションのフィールドです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>この特性のデータソースに適用される<a href="../../features/data-export-controls.md">データエクスポートコントロール</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name</code> </p> </td> 
   <td colname="col2"> <p>この特性のデータソースの所有者の名前。 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">ファーストパーティデータの場合、これは顧客自身の企業名となります。 </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">セカンドパーティデータの場合、これはパートナー企業の名前となります。 </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">サードパーティデータの場合、データパートナーの名前となります。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>データ主体がこの特性に最後に適合した正確な時間。データ形式は YYYY-MM-DD です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segments </code> </p> </td> 
   <td colname="col2"> <p>このユーザーが属するセグメント。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>セグメントの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>このセグメントを説明する短い文章。これはオプションのフィールドです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>このセグメントのデータソースに適用される<a href="../../features/data-export-controls.md">データエクスポートコントロール</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name</code> </p> </td> 
   <td colname="col2"> <p>このセグメントのデータソースの所有者の名前。 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">ファーストパーティデータの場合、これは顧客自身の企業名となります。 </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">セカンドパーティデータの場合、これはパートナー企業の名前となります。 </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">サードパーティデータの場合、データパートナーの名前となります。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>データ主体がこのセグメントに最後に適合した正確な時間。データ形式は YYYY-MM-DD です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> active</code> </p> </td> 
   <td colname="col2"> <p>データ主体が現在このセグメントと適合するかを示します。戻り値：<code><i>true</i></code> または <code><i>false</i></code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> links </code> </p> </td> 
   <td colname="col2"> <p>この ID が関連付けられている他の ID。次のフィールドについて情報が返されます。 </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (data source) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">integration code </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">data provider name </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID type </li> 
     </ul> </p> <p>これらのフィールドについてはすべて、この表の 1 行目で説明されています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> linking datetime</code> </p> </td> 
   <td colname="col2"> <p>ID の同期イベントによって ID 間の関連付けがおこなわれた正確な時間。データ形式は YYYY-MM-DD です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> device metadata </code> </p> </td> 
   <td colname="col2"> <p>デバイスに関する情報。この情報には以下のフィールドが含まれます。デバイスタイプによっては一部のフィールドのみが返されることにご注意ください。 </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>ハードウェア情報 </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>デバイスの製造元 </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>デバイスのマーケティング名 </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>デバイスモデル </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>デバイスのオペレーティングシステム（OS）の名前 </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>OS のバージョン </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>デバイスのベンダー </p> </li> 
     </ul> </p> <p> <p>注意：以下のいずれかを送信した場合にのみ、デバイスのメタデータが返されます。 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">Mobile ID </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Audience Manager ID </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud ID </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## データの削除 {#delete-data}

顧客の GDPR 要求は、受領後 30 日以内に処理することが掲げられていることを踏まえ、アドビでは、お客様からのデータ削除要求をできるだけ早急に処理するよう努めています。

**リクエスト**

**プライバシーサービス UI**（[こちらの UI リンク](https://gdprui.cloud.adobe.io/)および[こちらのドキュメント](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)）、または&#x200B;**プライバシーサービス API**（[こちらのドキュメント](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)および[こちらの API リファレンス](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)）からデータ削除要求を記録できます。いずれの場合も、送信するデータアクセス要求の Audience Manager 識別子が記述された JSON をアップロードする必要があります。整形式の JSON がどのように表示されるかを確認するには、**[JSON のサンプルをダウンロード](assets/delete_request.json)**&#x200B;できます。

**応答**

データ削除要求への応答として、個々の Audience Manager 識別子に関連付けられた特性およびセグメントが削除されます。さらに、データ主体の個々の Audience Manager 識別子は以降のデータ収集から完全にオプトアウトされ、それぞれの ID マッピングは削除されます。複数のデバイスにまたがる CRM ID や顧客の Cookie ID などの宣言済み ID が GDPR 要求で送信された場合、関連付けられたすべてのデバイス（1 つの宣言済み ID につき最大 100 個のデバイス）に対して必要な削除アクションをおこないます。

## オプトアウト要求{#opt-out-request}

オプトアウト要求については、[オプトアウト管理](../../overview/data-security-and-privacy/opt-out-management.md)に関するドキュメントを参照してください。

## Audience Manager 識別子（ID） {#aam-ids}

Adobe Audience Manager に対して GDPR 要求を送信する際、以下のいずれかの識別子（ID）を含める必要があります。ID の形式の詳細については、[Audience Manager ID のインデックス](../../reference/ids-in-aam.md)で確認できます。

### Adobe Audience Manager の一意のユーザー ID

**ユーザー ID**：aam_uuid

**定義**：Adobe Audience Manager の一意のユーザー ID

**名前空間 ID**：0

>[!NOTE]
>
>名前空間として CORE を使用することもできます。2 つ目の JSON の記述例を参照してください。

**JSON の記述例**：

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

### Adobe Experience Cloud ID

**ユーザー ID**：mid

**定義**：Adobe Experience Cloud ID（旧名では訪問者 ID または Marketing Cloud ID）

**名前空間 ID**：4

>[!NOTE]
>
>名前空間として ECID を使用することもできます。2 つ目の JSON の記述例を参照してください。

**JSON の記述例**：

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

### 顧客 ID

**ユーザー ID**：cid

**定義**：匿名のサイト訪問者に設定する Cookie やオフラインシステムからの CRM ID やハッシュ化されたユーザー名などの顧客 ID。

**名前空間 ID**：顧客固有。Audience Manager インスタンスから検索します。

**JSON の記述例**：

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

### モバイル広告 ID

**ユーザー ID**：d_cid

**定義**：モバイル広告 ID。
>[!IMPORTANT]
>
> モバイル SDK をご利用の場合、GDPR のアクセスおよび削除に関して完全な応答を得るには、モバイル広告 ID と合わせて Experience Cloud ID （MID）を送信する必要があります。

**名前空間 ID**：

* IDFA：20915
* GAID：20914

詳しくは、「[グローバルデータソース](../../features/global-data-sources.md)」を参照してください。

**JSON の記述例**：

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

### 統合コード

**ユーザー ID**：d_cid_ic

**定義**：データソースの統合コード。これは、Adobe Experience Cloud の Privacy コアサービスへの API リクエストで、データソース ID／名前空間 ID の代わりに使用できます。

**名前空間 ID**：非該当

JSON の記述例：

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
