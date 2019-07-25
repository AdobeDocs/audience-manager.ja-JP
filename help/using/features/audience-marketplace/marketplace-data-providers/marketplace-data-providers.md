---
description: Audience Manager 内でデータを販売するデータプロバイダーのワークフローの概要です。
keywords: Google Analytics
seo-description: Audience Manager 内でデータを販売するデータプロバイダーのワークフローの概要です。
seo-title: データプロバイダー向けの Audience Marketplace
solution: Audience Manager
title: データプロバイダー向けの Audience Marketplace
topic: DIL API
uuid: 80e60d33-63e7-496c-82c5-205ecf0ec03a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# データプロバイダー向けの Audience Marketplace の概要 {#audience-marketplace-for-data-providers}

[!DNL Audience Manager] 内でデータを販売するデータプロバイダーの概要とワークフロー。

<!-- c_marketplace_provider.xml -->

>[!NOTE]
>
>[役割に基づく権限](../../../reporting/reports-dashboard.md) により、機能へ [!UICONTROL Audience Marketplace] のアクセス権を制御できます。
>
>* 管理者は、データフィードの作成、サブスクライバーの管理、およびデータフィードへのサブスクライブをおこなえます。
>* ユーザーはフィードの検索および表示のみできます。


## マイ共有データについて {#my-shared-data-about}

[!UICONTROL My Shared Data] は、データプロバイダー（セラー）の [!UICONTROL Audience Marketplace] 機能です。As a provider, it lets you bundle traits into data feeds and sell them for a flat fee or [!DNL CPM] rate to buyers from within [!DNL Audience Manager]. アクティブ化されると、購入者は、数回のマウスクリックでフィードのサブスクリプションを購入できます。さらに、シンプルなレポートツールで、売上高を追跡したり、登録者を管理したりできます。Finally, with [!UICONTROL Audience Marketplace], [!DNL Adobe] takes care of invoice, billing, and fee payments for you. これらの機能を使用すると、購入者が求める効果的で有益なデータフィードの構築に専念できます。

![](assets/seller_marketplace.png)

<!-- c_myshared_data.xml -->

機能には、以下が含まれます。

* **Search：**&#x200B;検索フィールドを使用すると、名前またはテキストの説明でデータフィードを検索できます。
* **Name：**&#x200B;データフィードの名前。ノーブランドのプライベートデータフィードを使用して、購入者にこれが表示されないようにできます。
* **Description：**&#x200B;データフィードのコンテンツについて購入者に伝えます。
* **Traits：**&#x200B;各データフィード内の特性の数。プライベートデータフィードを使用して、購入者にこれが表示されないようにできます。
* **Last 30 Day Uniques：**&#x200B;過去 30 日で確認された個別ユーザーの数。プライベートデータフィードを使用して、購入者にこれが表示されないようにできます。
* **Last Month's Total Fees：**&#x200B;サブスクリプションを購入したデータ購入者が支払う金額。レポート期間は、毎月 10 日に終了します。期限切れのアカウントには、三角形と感嘆符のアイコンでフラグが設定されます。データが誤用されていたり、アカウントの期限が切れている場合、[サブスクリプション購入者のデータフィードを非アクティブ化](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#deactivate-data-feed)できます。
* **Status：**&#x200B;フィードがアクティブ、非アクティブ、プライベートまたは公開のいずれであるかを表示します。
* **Subscribers：**&#x200B;データフィードを使用している購入者の数を表示します。この列の数をクリックすると、購入者の会社名、サブスクリプション、請求およびサブスクリプション状況が表示されます。
* **Requests：**&#x200B;データフィードに対するアクセス要求の数。

## 非公開データフィード {#private-data-feeds}

In [!UICONTROL My Shared Data], sometimes a feed status is marked as private. これは、非公開データフィードであることを示しています。プライベートデータフィードを使用すると、販売者は、データへの購入者のアクセスを制限できます（データフィードの名前を含む）。販売者は、特別サービスや割引を提供したり、プライバシーおよびアクセス制御が重要な場合に、フィードをプライベートにできます。プライベートデータフィードでは、プロバイダーは、すべての購入者のアクセス要求を確認および承認できます。詳しくは、[非公開データフィード](../../../features/audience-marketplace/marketplace-private-feeds.md)のバイヤーの節を参照してください。公開データフィードまたは非公開データフィードの作成方法については、[公開または非公開のデータフィードの作成](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)を参照してください。

>[!MORE_LIKE_THIS]
>
>* [データプロバイダーにとっての割引](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts)

