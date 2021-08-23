---
description: ID サービスのお客様は、訪問者 Cookie を読み取って DCS API 呼び出しの実行に必要な ID を取得する方法を、この節で確認してください。
seo-description: ID サービスのお客様は、訪問者 Cookie を読み取って DCS API 呼び出しの実行に必要な ID を取得する方法を、この節で確認してください。
seo-title: Adobe Experience Platform ID サービスを通じたユーザー ID と地域 ID の取得
solution: Audience Manager
title: Adobe Experience Platform ID サービスを通じたユーザー ID と地域 ID の取得
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 94%

---

# Adobe Experience Platform ID サービスを通じたユーザー ID と地域 ID の取得 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID サービスのお客様は、訪問者 Cookie を読み取って [!DNL DCS] API 呼び出しの実行に必要な ID を取得する方法を、この節で確認してください。

## ID サービス Cookie からのユーザー ID の取得 {#get-user-ids-from-service-cookie}

[Adobe Experience Platform ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html)では、Web サイトにアクセスするユーザーに訪問者 ID と地域 ID を割り当てます。[!DNL Experience Cloud] のあらゆるソリューションでユーザーはこれらの ID によって識別されるので、[!DNL DCS] 呼び出しをおこなうには、これらの ID が必要になります。

* [!UICONTROL user ID] は、データを識別し特定の訪問者に関連付けるのに必要になります。
* [!UICONTROL region ID] が必要なのは、地域サーバー名に関連付けられているからです。地域サーバー名は [!DNL DCS] へのデータ送信に必要になります。[!DNL DCS] では、サイト訪問者に地理的に最も近いデータセンターに情報を保存します。[DCS 地域 ID、場所、ホスト名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)を参照してください。

ID サービスのお客様は、ID サービス Cookie から、または関数の呼び出しによって、この情報を抽出できます。必要なタスクや手順を次の表に示します。

コードの&#x200B;*斜体*&#x200B;の部分には実際の情報が入ります。

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> タスク </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1.<span class="keyword">Experience Cloud</span> のステータスを確認する</b> </p> </td> 
   <td colname="col2"> <p>ID サービスを使用するには、<span class="keyword">Experience Cloud</span> アカウントが必要です。既に <span class="keyword">Experience Cloud</span> アカウントがあれば、そのままでけっこうです。 </p> <p> まだ <span class="keyword">Experience Cloud</span> に登録していなければ、新規登録してください。いつでもお客様にご参加いただく用意ができています。アカウントの設定方法について詳しくは、<a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external">コアサービスのソリューションの有効化</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2.<span class="keyword">ID サービス</span>をセットアップする</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">ID サービス</span>は、データ収集に使用する各ページに組み込まれる JavaScript コードで構成されます。詳しくは、ID サービスの<a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external">実装ガイド</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3.<span class="keyword">ID サービス</span> Cookie を読み取る</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">ID サービス</span>では、ユーザー ID と地域 ID を AMCV Cookie に保存します。Cookie の完全名は <code>AMCV_<i>###</i>@AdobeOrg</code> です。<code><i>###</i></code> 要素は組織 ID のプレースホルダーです。詳しくは、<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external">Cookie と Experience Cloud ID</a> を参照してください。 </p> <p>AMCV Cookie を解析して、次のキー値ペアを取得します。 </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>：このキー値ペアには <span class="keyword">Experience Cloud</span> ユーザー ID が格納されています。 </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>：このキー値ペアには、地域サーバー名に関連付けられている地域 ID（<span class="term">ロケーションヒント</span>と呼ばれる場合もある）が格納されています。 </li> 
     </ul> </p> <p>ユーザー ID と地域 ID が用意できたら、<span class="wintitle">DCS</span> への呼び出しをおこなうことができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4.getMarketingCloudVisitorID で <span class="keyword">Experience Cloud ID</span> を取得する</b> </p> </td> 
   <td colname="col2"> <p><i>（オプション）</i>この関数は <span class="keyword">Experience Cloud</span> 訪問者 ID を返します。カスタムソリューションや特定のユースケース向けに設計されています。詳しくは、次の <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid">getMarketingCloudVisitorID の使用方法</a>や <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external">ID サービスの関連ドキュメント</a>を参照してください。 </p> <p>ID サービス Cookie からユーザー ID および地域 ID を取得した場合は、これを使用する必要はありません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## `getMarketingCloudVisitorID` の操作方法  {#working-with-getmarketingcloudvisitorid}

訪問者 ID を取得するもう 1 つの方法は、`getMarketingCloudVisitorID` 関数を使用することです。この関数は、呼び出されると、[!DNL ID service] に対してクエリを実行して ID を返します。`getMarketingCloudVisitorID` は、次に示すように、オプションの `callback` 引数を受け取ります。

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### コールバックの使用法と目的 {#callback-usage}

`callback` はオプションです。この引数がなくても、この関数は機能しますが、訪問者のブラウザーに [!DNL Experience Cloud] Cookie が設定されている場合にのみ ID を返します。訪問者の Cookie が見つからないか、訪問者に ID がない場合、この関数は空の `()` オブジェクトを返します。このような状況は、ページが読み込まれて訪問者が新しい ID を受け取った後でも、起こる可能性があります。これを避けるために、この関数に `callback` を指定して、ページの読み込み後に訪問者 ID の有無を確認させることができます。`callback` がなければ、訪問者 ID が後で訪問者のブラウザーに書き込まれても、関数は ID を返しません。

## 次の手順 {#next-steps}

ユーザー ID と地域 ID が用意できたら、[!DNL DCS] データの送受信を開始できます。[DCS API 呼び出しの実行](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)を参照してください。
