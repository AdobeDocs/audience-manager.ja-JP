---
description: Audience Manager 内でサードパーティデータを購入するデータ購入者の概要とワークフロー
seo-description: Audience Manager 内でサードパーティデータを購入するデータ購入者の概要とワークフロー
seo-title: データ購入者向けの Audience Marketplace
solution: Audience Manager
title: データ購入者向けの Audience Marketplace
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# データ購入者向けの Audience Marketplace {#audience-marketplace-for-data-buyers}

[!DNL Audience Manager] 内でサードパーティデータを購入するデータバイヤーの概要とワークフロー。

>[!NOTE]
>[役割に基づく権限](../../../reporting/reports-dashboard.md) により、機能へ [!UICONTROL Audience Marketplace] のアクセス権を制御できます。
>
>* 管理者は、データフィードの作成、サブスクライバーの管理、およびデータフィードへのサブスクライブをおこなえます。
>* ユーザーはフィードの検索および表示のみできます。


## Marketplace について {#about-marketplace}

<!-- c_marketplace_about.xml -->

[!UICONTROL Marketplace] は、データバイヤー向けの [!DNL Audience Manager] の機能で、お客様が購読できるデータフィードが一覧表示されます。It lists flat rate, [!DNL CPM], or private data feeds. これらのフィードは、[!DNL Audience Manager] を使用してデータを販売するサードパーティベンダーによって提供されます。[!UICONTROL Marketplace] では、レポートツールを使用すると、フィードの使用状況およびお客様の特性とサブスクリプション購入されたデータフィードの間の重複を追跡できます。Finally, with [!UICONTROL Audience Marketplace], [!DNL Adobe] takes care of invoices and fee payments (though you do have to self-report usage when subscribed to a [!DNL CPM] feed). これらの機能を使用すると、データプロバイダーを探す時間を浪費することなく、効果的なデータソースを見つけることができます。

>[!TIP]
> 
>**[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** を使用して、登録できる高品質なデータフィードを見つけます。Then, go back into the Audience Manager UI or use the [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) to subscribe to the feeds you found.

![](assets/buyer_marketplace.png)

[!UICONTROL Marketplace] のリストには、お客様に合ったデータフィードを見つけるために、並べ替えたり検索したりできる情報が含まれます。[!UICONTROL Marketplace] の購入者のリストには、以下の項目が含まれます。

* **[!UICONTROL Search]:** 名前またはテキストの説明に従ってデータフィードを検索します。
* **[!UICONTROL Name]:** データフィードの名前。
* **[!UICONTROL Description]:** データフィードのコンテンツに関する情報です。
* **[!UICONTROL Provider]:** データプロバイダーの名前。
* **[!UICONTROL Traits]:** データフィード内の特性の数。
* **[!UICONTROL 30 Day Provider Unique Users]:** 過去30日間に閲覧された個別ユーザーの数。
* **[!UICONTROL 30 Day Overlapped Uniques]:** プロバイダーのアカウント内のユーザーと重複するアカウント内のユーザーの数。
* **[!UICONTROL Feed Overlap]:** 30日の個別の重複値が割合で表示され、次のように計算されます。データ購入者30日が個別の30日間の個別訪問者数（30日個別） x100。
* **[!UICONTROL Private Feeds]:**[プライベートデータフィード](../../../features/audience-marketplace/marketplace-private-feeds.md)を参照してください。
* **[!UICONTROL Currently Subscribed Plan Count]:** データプロバイダーと共に持っている購読の数。

## 非公開データフィード {#private-data-feeds}

[!UICONTROL Marketplace] リストには、プロバイダーの名前および特性データがプライベートとして掲載されることがあります。これは、[非公開データフィード](../../../features/audience-marketplace/marketplace-private-feeds.md)であることを示しています。プライベートデータフィードを使用すると、販売者はデータへの購入者のアクセスを制限できます。販売者は、特別サービスや割引を提供したり、プライバシーおよびアクセス制御が重要な場合に、フィードをプライベートにできます。購入者は、プライベートフィードにアクセスしたい場合、サブスクリプション要求を販売者に送信する必要があります。詳しくは、[プライベートデータフィードのサブスクリプション購入](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)を参照してください。

>[!MORE_LIKE_THIS]
>
>* [Audience Marketplace のプランの詳細ページについて](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [データ購入者にとっての割引](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

