---
description: Audience Manager 内でサードパーティデータを購入するデータ購入者の概要とワークフロー
seo-description: Audience Manager 内でサードパーティデータを購入するデータ購入者の概要とワークフロー
seo-title: データ購入者向けの Audience Marketplace
solution: Audience Manager
title: データ購入者向けの Audience Marketplace
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: ht
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# データ購入者向けの Audience Marketplace {#audience-marketplace-for-data-buyers}

[!DNL Audience Manager] 内でサードパーティデータを購入するデータ購入者の概要とワークフロー。

>[!NOTE]
>[役割に基づく権限](../../../reporting/reports-dashboard.md)は、[!UICONTROL Audience Marketplace] 機能へのアクセスを制御します。
>
>* 管理者は、データフィードの作成、サブスクライバーの管理、およびデータフィードへのサブスクライブをおこなえます。
>* ユーザーはフィードの検索および表示のみできます。


## Marketplace について {#about-marketplace}

<!-- c_marketplace_about.xml -->

[!UICONTROL Marketplace] は、データ購入者向けの [!DNL Audience Manager] の機能で、お客様が購読できるデータフィードが一覧表示されます。定額、[!DNL CPM] または非公開データフィードが一覧表示されます。これらのフィードは、[!DNL Audience Manager] を使用してデータを販売するサードパーティベンダーによって提供されます。[!UICONTROL Marketplace] では、レポートツールを使用すると、フィードの使用状況およびお客様の特性とサブスクリプション購入されたデータフィードの間の重複を追跡できます。最後に、[!UICONTROL Audience Marketplace] では、[!DNL Adobe] が請求書および費用の支払いを処理します（ただし、[!DNL CPM] フィードを購読する場合は、使用量を自己申告する必要があります）。これらの機能を使用すると、データプロバイダーを探す時間を浪費することなく、効果的なデータソースを見つけることができます。

>[!TIP]
> 
>**[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** を使用して、高品質のデータフィードを見つけ、サブスクリプションを購入できます。次に、Audience Manager UI へ戻るか[Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) を使用して、見つけたフィードを購読します。

![](assets/buyer_marketplace.png)

[!UICONTROL Marketplace] のリストには、お客様に合ったデータフィードを見つけるために、並べ替えたり検索したりできる情報が含まれます。[!UICONTROL Marketplace] の購入者のリストには、以下の項目が含まれます。

* **[!UICONTROL Search]：**&#x200B;名前またはテキストの説明でデータフィードを検索します。
* **[!UICONTROL Name]：**&#x200B;データフィードの名前。
* **[!UICONTROL Description]：**&#x200B;データフィードのコンテンツに関する情報。
* **[!UICONTROL Provider]：**&#x200B;データプロバイダーの名前。
* **[!UICONTROL Traits]：**&#x200B;データフィード内の特性の数。
* **[!UICONTROL 30 Day Provider Unique Users]：**&#x200B;過去 30 日で確認された個別訪問者数。
* **[!UICONTROL 30 Day Overlapped Uniques]：**&#x200B;プロバイダーのアカウントのユーザーと重複するアカウント内のユーザーの数。
* **[!UICONTROL Feed Overlap]:** 30日間の重複している個別訪問者数の値が割合で表示され、(データ購入者 30 日間の重複している個別訪問者数 / データ購入者の 30 日間の個別訪問者数) x 100 で計算されます。
* **[!UICONTROL Private Feeds]：**[非公開データフィード](../../../features/audience-marketplace/marketplace-private-feeds.md)を参照してください。
* **[!UICONTROL Currently Subscribed Plan Count]：**&#x200B;データプロバイダーを使用して所有するサブスクリプションの数。

## 非公開データフィード {#private-data-feeds}

[!UICONTROL Marketplace] リストには、プロバイダーの名前および特性データが非公開として掲載されることがあります。これは、[非公開データフィード](../../../features/audience-marketplace/marketplace-private-feeds.md)であることを示しています。非公開データフィードを使用すると、販売者はデータへの購入者のアクセスを制限できます。販売者は、特別サービスや割引を提供したり、プライバシーおよびアクセス制御が重要な場合に、フィードを非公開にできます。購入者は、非公開フィードにアクセスしたい場合、サブスクリプション要求を販売者に送信する必要があります。詳しくは、[非公開データフィードのサブスクリプション購入](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)を参照してください。

>[!MORE_LIKE_THIS]
>
>* [Audience Marketplace のプランの詳細ページについて](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [データ購入者にとっての割引](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

