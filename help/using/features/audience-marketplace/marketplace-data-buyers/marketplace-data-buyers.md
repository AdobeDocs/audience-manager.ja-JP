---
description: Audience Manager 内でサードパーティデータを購入するデータ購入者の概要とワークフロー
seo-description: Audience Manager 内でサードパーティデータを購入するデータ購入者の概要とワークフロー
seo-title: データ購入者向けの Audience Marketplace
solution: Audience Manager
title: データ購入者向けの Audience Marketplace
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 64%

---


# [!UICONTROL Audience Marketplace] （データバイヤー用） {#audience-marketplace-for-data-buyers}

[!DNL Audience Manager] 内でサードパーティデータを購入するデータ購入者の概要とワークフロー。

>[!NOTE]
>[役割に基づく権限](../../../reporting/reports-dashboard.md)は、[!UICONTROL Audience Marketplace] 機能へのアクセスを制御します。
>
>* 管理者は、データフィードの作成、サブスクライバーの管理、およびデータフィードへのサブスクライブをおこなえます。
>* ユーザーはフィードの検索および表示のみできます。


## The [!UICONTROL Marketplace]: About {#about-marketplace}

[!UICONTROL Marketplace] は、データ購入者向けの [!DNL Audience Manager] の機能で、お客様が購読できるデータフィードが一覧表示されます。定額、[!DNL CPM] またはプライベートデータフィードが一覧表示されます。これらのフィードは、[!DNL Audience Manager] を使用してデータを販売するサードパーティベンダーによって提供されます。

In the [!UICONTROL Marketplace], reporting tools let you track feed usage and the overlap between your [!UICONTROL traits] and those in a subscribed data feed. 最後に、[!UICONTROL Audience Marketplace] では、[!DNL Adobe] が請求書および費用の支払いを処理します（ただし、[!DNL CPM] フィードを購読する場合は、使用量を自己申告する必要があります）。これらの機能を使用すると、データプロバイダーを探す時間を浪費することなく、効果的なデータソースを見つけることができます。

>[!TIP]
>
>**[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** を使用して、高品質のデータフィードを見つけ、サブスクリプションを購入できます。Then, go back into the [!DNL Audience Manager] user interface or use the [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) to subscribe to the feeds you found.

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

[!UICONTROL Marketplace] のリストには、お客様に合ったデータフィードを見つけるために、並べ替えたり検索したりできる情報が含まれます。[!UICONTROL Marketplace] の購入者のリストには、以下の項目が含まれます。

* **[!UICONTROL Search]**：名前またはテキストの説明でデータフィードを検索します。
* **[!UICONTROL Similar Traits]**:データフィード [!UICONTROL traits] からの類似の数を表示します。 This column is shown after you enter a [!UICONTROL trait] or [!UICONTROL segment] to filter by in the **[!UICONTROL Similarity To]** section.
* **[!UICONTROL Name]**：データフィードの名前。
* **[!UICONTROL Description]**：データフィードのコンテンツに関する情報。
* **[!UICONTROL Provider]**：データプロバイダーの名前。
* **[!UICONTROL Traits]**:データフィード [!UICONTROL traits] 内のの数。
* **[!UICONTROL 30 Day Provider Unique Users]**：過去 30 日で確認された個別ユーザーの数。
* **[!UICONTROL 30 Day Overlapped Uniques]**：プロバイダーのアカウントのユーザーと重複するアカウント内のユーザーの数。
* **[!UICONTROL Feed Overlap]**: 30日間の重複している個別訪問者数の値が割合で表示され、(データ購入者 30 日間の重複している個別訪問者数 / データ購入者の 30 日間の個別訪問者数) x 100 で計算されます。
* **[!UICONTROL Private Feeds]**：[非公開データフィード](../../../features/audience-marketplace/marketplace-private-feeds.md)を参照してください。
* **[!UICONTROL Currently Subscribed Plan Count]**：データプロバイダーを使用して所有するサブスクリプションの数。

 

ニーズに最適なデータフィードを簡単に見つけるには、[!UICONTROL Marketplace] ページの左側で使用できる次のフィルターを使用します。

* **[!UICONTROL Similarity To]**:選択したまたはのいずれかとの類似性に基づいて、データフィードをフィルタ [!UICONTROL trait] ー [!UICONTROL segment] します。 When entering the [!UICONTROL trait] or segment to compare to, you can use the [!UICONTROL trait] or [!UICONTROL segment] ID, or their respective names.
* **[!UICONTROL Similarity Cutoff]**:スライダーをドラッグして、選択したまたはに対するデータフィードの類似性に基づいてデータフィード [!UICONTROL traits] をフィルター [!UICONTROL trait] し [!UICONTROL segment]ます。 To learn more about [!UICONTROL trait] similarity scores, see [Trait Similarity Score](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**：サブスクリプション状況に基づいてデータフィードをフィルタリングします。
* **[!UICONTROL Plan Use Case]**:サポートされている使用例に基づいて、データフィードをフィルターします。 **[!UICONTROL Activation]**、 **[!UICONTROL Segments and Overlap]**&#x200B;および **[!UICONTROL Modelling]**。
* **[!UICONTROL Plan Unit]**：価格タイプに基づいてデータフィードをフィルタリングします。

## 類似するものの検索 [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] 既存のセグメントとの類似性に基づいて、様々なデータフィード [!UICONTROL traits] から検索するオプションが与えら [!UICONTROL traits] れます。 手順は次のとおりです。

1. **[!UICONTROL Audience Marketplace]**／**[!UICONTROL Marketplace]** に移動します。
2. Use the **[!UICONTROL Similarity To]** selector to choose between filtering based on a [!UICONTROL trait] or [!UICONTROL segment]. You can filter based on [!UICONTROL trait]/[!UICONTROL segment] ID or name. 入力に基づいて、関連する候補が検索ボックスに自動的に表示されます。
3. フィルタリングしたい特性やセグメントを特定したら、候補リストでクリックします。
4. To narrow down the results, use the **[!UICONTROL Similarity Cutoff]** slider to move from less similar [!UICONTROL traits], to more similar ones.

フィルタリングが完了したら、結果ページに新しい列 **[!UICONTROL Similar Traits]** が表示されます。This column shows you the number of similar [!UICONTROL traits] to the one you filtered by, from each data feed that meets the filtering criteria.

類似した特性の完全なリストを確認するには、**[!UICONTROL Similar Traits]** 列の数字をクリックします。

>[!NOTE]
>
> Audience Marketplace displays the top 500 similar [!UICONTROL trait] results from across the data feeds.

Watch the video below for a full overview of how to find similar [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 非公開データフィード {#private-data-feeds}

In the [!UICONTROL Marketplace] list, sometimes the provider&#39;s name and [!UICONTROL trait] data are marked as private. これは、[非公開データフィード](../../../features/audience-marketplace/marketplace-private-feeds.md)であることを示しています。非公開データフィードを使用すると、販売者はデータへの購入者のアクセスを制限できます。販売者は、特別サービスや割引を提供したり、プライバシーおよびアクセス制御が重要な場合に、フィードを非公開にできます。購入者は、非公開フィードにアクセスしたい場合、サブスクリプション要求を販売者に送信する必要があります。詳しくは、[非公開データフィードのサブスクリプション購入](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)を参照してください。

>[!MORELIKETHIS]
>
>* [Audience Marketplace のプランの詳細ページについて](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [データ購入者にとっての割引](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

