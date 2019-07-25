---
description: プライベートデータフィードは、プロバイダーがデータへの購入者のアクセスを制限するためのオプションです。データプロバイダーはプライベートデータフィードを作成する前に、データ購入者はプライベートデータフィードのサブスクリプションを購入する前に、この情報によく目を通してください。
seo-description: プライベートデータフィードは、プロバイダーがデータへの購入者のアクセスを制限するためのオプションです。データプロバイダーはプライベートデータフィードを作成する前に、データ購入者はプライベートデータフィードのサブスクリプションを購入する前に、この情報によく目を通してください。
seo-title: プライベートデータフィード
solution: Audience Manager
title: プライベートデータフィード
uuid: e4ca59ca-bbc9-4897-9374-8f3d54b2beee
translation-type: tm+mt
source-git-commit: 21b2505ac6cdf97b401bf0b0ac80bf1964f084b8

---


# 非公開データフィード {#private-data-feeds}

プライベートデータフィードは、プロバイダーがデータへの購入者のアクセスを制限するためのオプションです。データプロバイダーはプライベートデータフィードを作成する前に、データ購入者はプライベートデータフィードのサブスクリプションを購入する前に、この情報によく目を通してください。

<!-- c_marketplace_privatefeed.xml -->

## プロバイダーにとってのプライベートデータフィード {#private-data-feeds-providers}

プロバイダーは、データフィードを公開またはプライベートにできます。プライベートデータフィードを使用すると、データへの購入者のアクセスを制限できます（データ販売者の名前を含む）。特別サービスや割引を提供したり、プライバシーおよびアクセス制御が重要な場合に、プライベートデータフィードを作成することもできます。プライベートデータフィードでは、購入者の要求を確認および承認できます。要求を承認したら、フィードは、購入者には公開データフィードのように見えます。You can view and manage all your feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. 以下に示すように、このタイプのフィードは、ステータス列で「Private」とマークされます。

![](assets/my_shared_data.png)

### フィードリクエストの管理

[!UICONTROL My Shared Data] でプライベートデータフィードの名前をクリックすると、いくつかのタブを含むページが表示されます。タブをクリックして、プライベートデータフィードリクエストを管理します。

![](assets/shared_data_tabs.png)

以下の表に、各アクションタブで提供される役割または関数の定義を示します。

<table id="table_AFB429CA52A34658859448D9A5215F9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> タブ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Current Subscribers</span></b> </p> </td> 
   <td colname="col2"> <p>プライベートデータフィードのサブスクリプションを購入した承認済みの購入者を一覧表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Potential Subscribers</span></b> </p> </td> 
   <td colname="col2"> <p>プライベートデータフィードのサブスクリプションを購入していない承認済みの購入者を一覧表示します。 </p> <p>承認により、購入者には、データフィードが公開されているかのように表示されます。これにより、フィードを登録前に確認および評価できます。また、潜在的なサブスクリプション購入者として一覧表示された購入者に、データフィードに対する割引を提供することもできます。Once the buyer subscribes, their profile moves to <b><span class="uicontrol"> Current Subscribers</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Access Requests</span></b> </p> </td>
   <td colname="col2"> <p>プライベートデータフィードの新しいサブスクリプション要求を一覧表示します。このタブをクリックして、購入者の要求を確認、承認または拒否できます。 </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">Approved buyers move to <b><span class="uicontrol"> Potential Subscribers</span></b>. </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">Rejected buyers move to <b><span class="uicontrol"> Denied Access</span></b>. </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Details Requests</span></b> </p> </td>
   <td colname="col2"> <p>まだデータフィードのサブスクリプションを購入してはいないものの、フィードに関する詳細情報を要求した承認済みの購入者を一覧表示します。 </p> <p>承認により、購入者には、データフィードが公開されているかのように表示されます。これにより、フィードを登録前に確認および評価できます。また、アクセスを要求している購入者に、データフィードに対する割引を提供することもできます。詳細の要求に対応すると、購入者プロファイルがこのタブから削除されます。If they haven't subscribed, the buyer profile is still in <b><span class="uicontrol"> Potential Subscribers</span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Denied Access</span></b> </p> </td> 
   <td colname="col2"> <p>プライベートデータフィードに関する拒否されたサブスクリプション要求を一覧表示します。 </p> <p>To re-approve denied buyers, change the <span class="wintitle"> Rejection Status</span> to <b><span class="uicontrol"> Allow</span></b>. This moves the buyer to <b><span class="uicontrol"> Potential Subscribers</span></b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 次の手順

以下のドキュメントは、プライベートデータフィードを導入するうえで役立ちます。

* [公開または非公開のデータフィードの作成](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [プライベートフィード要求の確認、承認または拒否](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [購入者にとってのプライベートデータフィード](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## 購入者にとってのプライベートデータフィード {#private-data-feeds-for-buyers}

[Marketplace](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace) では、バイヤーには、非公開データフィードも他のオファーと同様に表示されます。ただし、この場合、フィードリストには、特性、個別ユーザーおよびユーザーの重複に関する概要情報は表示されません。また、データ販売者には、[!UICONTROL Provider] リストの [!UICONTROL Marketplace] 列で名前を表示または非表示にするオプションがあります。販売者がサブスクリプション要求を承認したら、プライベートフィードのすべてのデータが使用可能になります（公開フィードのように機能します）。以下の [!UICONTROL Marketplace] の例に、購入者が使用できる 3 つの異なるフィードタイプを示します。

![](assets/buyer_marketplace.png)

フィードタイプには次のものがあります。

これらの様々なフィードタイプがデータを表示または非表示にする方法を次の表に示します。

<table id="table_41D4A798ACF548A3A03ACB427CA4652D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィードのタイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Public</span></b> </p> </td> 
   <td colname="col2"> <p>プロバイダーの名前、特性および一意のデータがリストに表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Private Without Branding</span></b> </p> </td> 
   <td colname="col2"> <p>プロバイダーの名前が「Private Seller」に設定され、特性数、一意のデータおよび特性の重複データは表示されません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Private With Branding</span></b> </p> </td> 
   <td colname="col2"> <p>プロバイダーの名前はリストに表示されますが、特性数、一意のデータおよび特性の重複データは表示されません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 次の手順

アクセスのリクエスト方法について、[非公開データフィードを購読する](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)を参照してください。

## How to set up the Sharing Relationship between Data Provider and Data Buyer {#set-up-sharing-relationship}

### ステップ1-有効化-データプロバイダーとデータ購入者

プロセスの最初の手順には、アドビコンサルティングまたはカスタマーケアからの介入が必要です。データプロバイダーとデータのバイヤーは、有効化をリクエストするためにアドビコンサルティングまたはカスタマーケアにお問い合わせください。

### ステップ2-データプロバイダー-新規データソースの作成

Audience Managerアカウントで、以下を含む新しいcookieデータソースを作成します。

* **受信キー** としてのAudience Manager ID;
* **「共有の有効化」** オプションがオンになっています。

![](assets/create-datasource.png)

**「保存」**&#x200B;をクリックすると、特性ストレージ/サードパーティデータで **新しいサブフォルダーが自動的に作成**&#x200B;されます。

![](assets/folder-structure.png)

### 手順3-データプロバイダー-共有の特性の特定

この手順では、パートナーと共有する特性を特定します。新しい特性を作成したり、既存の特性を編集したりできます。場合によっては、次の特徴が必要になります。

* 手順2の一部として作成したデータソースに関連付ける場合。
* 新しく作成したサブフォルダーに、サードパーティのデータの下に保存される。

Read more about [creating traits](/help/using/features/traits/create-onboarded-rule-based-traits.md) and [editing traits](/help/using/features/traits/manage-trait-rules.md#edit-trait).

### 手順4-データプロバイダー-データフィードの作成

次に、データフィードを作成して、特性をデータバイヤーと共有します。Refer to [Create a Public or Private Data Feed](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md) for instructions on how to create a data feed.

>[!IMPORTANT]
>
>「設定」で、「非公開」オプションを選択します。このフィールドを「公開」に設定すると、Audience Marketplace顧客はフィードを購読できます。

![](assets/create-data-feed.png)

### 手順5-データ購入者-アクセス権

**Audience Marketplace／Marketplace** を開きます。前の手順でデータプロバイダーによって作成されたデータフィードを検索します。「**Request Access**」をクリックします。データプロバイダー側の指定された連絡先に電子メール通知が送信されるようになりました。See also, [Subscribe to a Private Data Feed](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

### 手順6-データプロバイダー-アクセス権の付与

**Audience Marketplace/マイ共有データ** に移動し、手順4で作成したフィードを検索します。Click into the new access request and click **Allow Access** to approve the request. [「プライベートフィードリクエストのレビュー、承認、拒否」も参照](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)してください。

### ステップ7-データ購入者-購読オン

After the data provider grants access to the data feed, you can see the feed in your account in **Audience Marketplace &gt; Marketplace**. Review the details, turn the Subscription button ON, and click **Review &amp; Subscribe**. See [Storage for Subscribed Data Feeds](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee) for information on where to find the 3rd party traits.

これらの特徴は、データプロバイダーのアカウントでのみ編集できます。




