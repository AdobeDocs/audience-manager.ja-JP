---
description: Audience Manager 内でサードパーティデータを購入するデータ購入者の概要とワークフロー
seo-description: Audience Manager 内でサードパーティデータを購入するデータ購入者の概要とワークフロー
seo-title: データ購入者向けの Audience Marketplace
solution: Audience Manager
title: データ購入者向けの Audience Marketplace
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: d9a4244f68e95c872d3686da10ee3a774250fbfe

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

[!UICONTROL Marketplace] は、データ購入者向けの [!DNL Audience Manager] の機能で、お客様が購読できるデータフィードが一覧表示されます。It lists flat rate, [!DNL CPM], and private data feeds. これらのフィードは、[!DNL Audience Manager] を使用してデータを販売するサードパーティベンダーによって提供されます。

[!UICONTROL Marketplace] では、レポートツールを使用すると、フィードの使用状況およびお客様の特性とサブスクリプション購入されたデータフィードの間の重複を追跡できます。最後に、[!UICONTROL Audience Marketplace] では、[!DNL Adobe] が請求書および費用の支払いを処理します（ただし、[!DNL CPM] フィードを購読する場合は、使用量を自己申告する必要があります）。これらの機能を使用すると、データプロバイダーを探す時間を浪費することなく、効果的なデータソースを見つけることができます。

>[!TIP]
>
>Use the **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** to find high quality data feeds that you can subscribe to. Then, go back into the Audience Manager UI or use the [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) to subscribe to the feeds you found.

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

[!UICONTROL Marketplace] のリストには、お客様に合ったデータフィードを見つけるために、並べ替えたり検索したりできる情報が含まれます。[!UICONTROL Marketplace] の購入者のリストには、以下の項目が含まれます。

* **[!UICONTROL Search]**:名前または説明テキストでデータフィードを検索します。
* **[!UICONTROL Similar Traits]**:データフィードからの類似特性の数を表示します。 この列は、セクションにフィルターする特性またはセグメントを入力した後に表示さ **[!UICONTROL Similarity To]** れます。
* **[!UICONTROL Name]**:データフィードの名前。
* **[!UICONTROL Description]**:データフィードの内容に関する情報です。
* **[!UICONTROL Provider]**:データプロバイダーの名前。
* **[!UICONTROL Traits]**:データフィード内の特性の数。
* **[!UICONTROL 30 Day Provider Unique Users]**:過去30日間に閲覧された個別ユーザーの数です。
* **[!UICONTROL 30 Day Overlapped Uniques]**:アカウント内で、プロバイダーのアカウント内のユーザーと重複するユーザーの数。
* **[!UICONTROL Feed Overlap]**:30日の重複個別の値（割合で表示）。次のように計算されます。データ購入者30日重複個別/データ購入者30日個別)x 100
* **[!UICONTROL Private Feeds]**:プライベートデ [ータフィードを参照してください](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]**:データプロバイダーに対する購読の数です。

ニーズに最適なデータフィードを簡単に見つけるには、ページの左側にある次のフィルターを使用し [!UICONTROL Marketplace] ます。

* **[!UICONTROL Similarity To]**:選択した特性またはセグメントとの類似性に基づいて、データフィードをフィルタリングします。 比較する特性またはセグメントを入力する際に、特性またはセグメントID、またはそれぞれの名前を使用できます。
* **[!UICONTROL Similarity Cutoff]**:スライダをドラッグして、選択した特性またはセグメントに対する特性の類似性に基づいて、データフィードをフィルタリングします。
* **[!UICONTROL Subscription Status]**:購読ステータスに基づいてデータフィードをフィルターします。
* **[!UICONTROL Plan Use Case]**:サポートされている使用例に基づいて、データフィードをフィルターします。 **[!UICONTROL Activation]**、 **[!UICONTROL Segments and Overlap]**、、 **[!UICONTROL Modelling]**、
* **[!UICONTROL Plan Unit]**:価格タイプに基づいてデータフィードをフィルターします。

以下のビデオで、これらのフィルターの使用方法の概要をご覧ください。

## 類似の特徴の検索 {#finding-similar-traits}

[!UICONTROL Audience Marketplace] には、既存の特性やセグメントとの類似性に基づいて、様々なデータフィードから特性を検索するオプションがあります。 手順は次のとおりです。

1. **[!UICONTROL Audience Marketplace]**／**[!UICONTROL Marketplace]** に移動します。
2. セレクターを使 **[!UICONTROL Similarity To]** 用して、特性またはセグメントに基づくフィルターを選択します。 特性/セグメントIDまたは名前に基づいてフィルターできます。 検索ボックスには、入力に基づいて関連する提案が自動的に表示されます。
3. フィルターに使用する特性またはセグメントを特定したら、提案リストでその特性またはセグメントをクリックします。
4. 結果を絞り込むには、スライダーを使 **[!UICONTROL Similarity Cutoff]** 用して、類似の少ない特徴から類似の特徴に移動します。

フィルタリングが完了すると、結果ページに新しい列が表示されます。 **[!UICONTROL Similar Traits]**. この列には、フィルター条件を満たす各データフィードから、フィルターした特性と類似する特性の数が表示されます。

類似した特性の完全なリストを表示するには、列の数値をクリックし **[!UICONTROL Similar Traits]** ます。

>[!NOTE]
>
> Audience Marketplaceには、複数のデータフィードにわたる類似した特徴の結果の上位500件が表示されます。

以下のビデオで、類似の特徴を見つける方法の概要をご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/29370/?captions=jpn)


## 非公開データフィード {#private-data-feeds}

[!UICONTROL Marketplace] リストには、プロバイダーの名前および特性データが非公開として掲載されることがあります。これは、[非公開データフィード](../../../features/audience-marketplace/marketplace-private-feeds.md)であることを示しています。非公開データフィードを使用すると、販売者はデータへの購入者のアクセスを制限できます。販売者は、特別サービスや割引を提供したり、プライバシーおよびアクセス制御が重要な場合に、フィードを非公開にできます。購入者は、非公開フィードにアクセスしたい場合、サブスクリプション要求を販売者に送信する必要があります。See [Subscribe to a Private Data Feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) for details.

>[!MORE_LIKE_THIS]
>
>* [Audience Marketplace のプランの詳細ページについて](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [データ購入者にとっての割引](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

