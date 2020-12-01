---
description: Audience Manager がセグメント情報をデータパートナーに送信すると、これらのオブジェクトが数値 ID で識別されます。データパートナーは、この情報を顧客と共有する（または自分で操作する）場合、実際の名前および説明を使用すると、レポート、ダッシュボードまたは他のユーザーインターフェイス（UI）での顧客のエクスペリエンスが向上します。データパートナーは、これらのわかりやすい名前を、手動または自動化された方法（この節で説明）のどちらかで顧客に提供できます。
seo-description: Audience Manager がセグメント情報をデータパートナーに送信すると、これらのオブジェクトが数値 ID で識別されます。データパートナーは、この情報を顧客と共有する（または自分で操作する）場合、実際の名前および説明を使用すると、レポート、ダッシュボードまたは他のユーザーインターフェイス（UI）での顧客のエクスペリエンスが向上します。データパートナーは、これらのわかりやすい名前を、手動または自動化された方法（この節で説明）のどちらかで顧客に提供できます。
seo-title: セグメントメタデータの取得
solution: Audience Manager
title: セグメントメタデータの取得
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 100%

---


# セグメントメタデータの取得 {#retrieving-segment-metadata}

Audience Manager がセグメント情報をデータパートナーに送信すると、これらのオブジェクトが数値 ID で識別されます。この情報をデータパートナーが顧客と共有する（または自分で操作する）場合、実際の名前や説明を使用すると、レポートやダッシュボードなどのユーザーインターフェイス（[!DNL UI]）での顧客のエクスペリエンスが向上します。データパートナーは、これらのわかりやすい名前を、手動または自動化された方法（この節で説明）のどちらかで顧客に提供できます。

## 手動方式  {#manual-method}

データパートナーは通常、オーディエンスのメタデータを手動プロセスにより顧客から取得しています。これには、電子メールにファイルを添付したり、専用に作成および維持されている [!DNL UI] からユーザーがデータを追加する作業が含まれます。これらのプロセスも使用できますが、複雑で時間がかかることが多く、手動でのデータ入力が必要となる場合もあります。通常、この方法は迅速な統合のために使用されますが、長期的に最善のユーザーエクスペリエンスをもたらすものではありません。その代わりに、[!DNL Audience Manager][!DNL API] を使用して、セグメントメタデータを自動的に取得することができます。

## 自動方式 {#automated-method}

[!DNL Audience Manager] には、セグメントメタデータを自動的に取得できる [REST API](../../api/rest-api-main/rest-api-main.md) が用意されています。[!DNL API] を使用すると、スケジュール設定された間隔ごと、または [!DNL Audience Manager] のデータを処理して新しいセグメント ID が見つかった時点で自動的にセグメントメタデータを取得するジョブを作成することができます。詳しくは後述の手順を参照してください。

### 手順 1：Audience Manager API を確認する

[REST API の概要](../../api/rest-api-main/aam-api-getting-started.md)の節では、一般的な要件、認証、使用可能な方式などについて説明しています。まだ [!DNL Audience Manager][!DNL API] を使用したことがない場合は、ここから始めます。

### 手順 2：OAuth2 アクセス資格情報をリクエストする

[!DNL API] 呼び出しをおこなうには、クライアント ID と暗号鍵が必要です。クライアント ID と暗号鍵は、統合設定処理時に統合のスペシャリストから入手できます。また、電子メールリクエストを [!UICONTROL Audience Manager Customer Care]（[!DNL amsupport@adobe.com]）に送信することもできます。

### 手順 3：統合された各顧客から顧客特有の情報を収集する

統合された各顧客に、次の情報を求めます。

* ユーザー名：特定の統合に関連付けられた宛先について読み取り専用権限を持つ制限付きユーザーが対象です。
* パスワード：ユーザーのパスワード。
* 宛先 ID：特定のサーバー間統合について作成された宛先に関連付けられた ID（整数）です。

### 手順 4：API 呼び出しを使用してセグメントメタデータを取得する

上述の手順を完了した後、`GET` メソッドを使用してセグメントメタデータを取得できます。リクエストと応答のサンプルについては、[宛先マッピングを返す](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings)を参照してください。この呼び出しにより、[!DNL JSON] オブジェクトのキーと値のペアとして書式設定されたセグメントデータが返されます。レスポンスで返される重要なセグメント属性の一部を次の表で紹介しています。

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingId</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> セグメント ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>セグメント名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>セグメントの内容を示す短いテキスト。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>セグメントマッピングの現在のステータス。返されるステータスオプションは次のとおりです。 </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>