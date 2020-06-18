---
description: Audience Manager 内でサードパーティデータを購入するデータ購入者の概要とワークフロー
seo-description: Audience Manager 内でサードパーティデータを購入するデータ購入者の概要とワークフロー
seo-title: データ購入者向けの Audience Marketplace
solution: Audience Manager
title: データ購入者向けの Audience Marketplace
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 96%

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

[!UICONTROL Marketplace] は、データ購入者向けの [!DNL Audience Manager] の機能で、お客様が購読できるデータフィードが一覧表示されます。定額、[!DNL CPM] またはプライベートデータフィードが一覧表示されます。これらのフィードは、[!DNL Audience Manager] を使用してデータを販売するサードパーティベンダーによって提供されます。

[!UICONTROL Marketplace] では、レポートツールを使用すると、フィードの使用状況およびお客様の特性とサブスクリプション購入されたデータフィードの間の重複を追跡できます。最後に、[!UICONTROL Audience Marketplace] では、[!DNL Adobe] が請求書および費用の支払いを処理します（ただし、[!DNL CPM] フィードを購読する場合は、使用量を自己申告する必要があります）。これらの機能を使用すると、データプロバイダーを探す時間を浪費することなく、効果的なデータソースを見つけることができます。

>[!TIP]
>
>**[Adobe Audience Finder](https://www.adobe-audience-finder.com/)**を使用して、高品質のデータフィードを見つけ、サブスクリプションを購入できます。Then, go back into the[!DNL Audience Manager]user interface or use the[Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)to subscribe to the feeds you found.

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

[!UICONTROL Marketplace] のリストには、お客様に合ったデータフィードを見つけるために、並べ替えたり検索したりできる情報が含まれます。[!UICONTROL Marketplace] の購入者のリストには、以下の項目が含まれます。

* **[!UICONTROL Search]**：名前またはテキストの説明でデータフィードを検索します。
* **[!UICONTROL Similar Traits]**：データフィードから類似した特性の数を表示します。この列は、**[!UICONTROL Similarity To]**&#x200B;セクションでフィルタリングするために特性やセグメントを入力すると表示されます。
* **[!UICONTROL Name]**：データフィードの名前。
* **[!UICONTROL Description]**：データフィードのコンテンツに関する情報。
* **[!UICONTROL Provider]**：データプロバイダーの名前。
* **[!UICONTROL Traits]**：データフィード内の特性の数。
* **[!UICONTROL 30 Day Provider Unique Users]**：過去 30 日で確認された個別ユーザーの数。
* **[!UICONTROL 30 Day Overlapped Uniques]**：プロバイダーのアカウントのユーザーと重複するアカウント内のユーザーの数。
* **[!UICONTROL Feed Overlap]**: 30日間の重複している個別訪問者数の値が割合で表示され、(データ購入者 30 日間の重複している個別訪問者数 / データ購入者の 30 日間の個別訪問者数) x 100 で計算されます。
* **[!UICONTROL Private Feeds]**：[非公開データフィード](../../../features/audience-marketplace/marketplace-private-feeds.md)を参照してください。
* **[!UICONTROL Currently Subscribed Plan Count]**：データプロバイダーを使用して所有するサブスクリプションの数。

 

ニーズに最適なデータフィードを簡単に見つけるには、[!UICONTROL Marketplace] ページの左側で使用できる次のフィルターを使用します。

* **[!UICONTROL Similarity To]**：選択した特性またはセグメントとの類似点に基づいてデータフィードをフィルタリングします。比較するための特性やセグメントを入力する際に、特性 ID やセグメント ID を使用したり、それぞれの名前を使用したりできます。
* **[!UICONTROL Similarity Cutoff]**：スライダーをドラッグして、選択した特性やセグメントに特性がどれくらい類似しているかに基づいてデータフィードをフィルタリングします。特性類似性スコアについて詳しくは、[特性類似性スコア](../../segments/trait-recommendations.md#trait-similarity-score)を参照してください。
* **[!UICONTROL Subscription Status]**：サブスクリプション状況に基づいてデータフィードをフィルタリングします。
* **[!UICONTROL Plan Use Case]**: サポートされている使用例に基づいて、データフィードをフィルターします。 **[!UICONTROL Activation]**、 **[!UICONTROL Segments and Overlap]**&#x200B;および **[!UICONTROL Modelling]**。
* **[!UICONTROL Plan Unit]**：価格タイプに基づいてデータフィードをフィルタリングします。

## 類似した特性の検索 {#finding-similar-traits}

[!UICONTROL Audience Marketplace] には、既存の特性やセグメントとの類似性に基づいて、様々なデータフィードから特性を見つけるためのオプションが用意されています。手順は次のとおりです。

1. **[!UICONTROL Audience Marketplace]**／**[!UICONTROL Marketplace]** に移動します。
2. **[!UICONTROL Similarity To]** セレクターを使用して、特性またはセグメントに基づいてフィルタリングを選択します。特性／セグメント ID または名前に基づいてフィルタリングできます。入力に基づいて、関連する候補が検索ボックスに自動的に表示されます。
3. フィルタリングしたい特性やセグメントを特定したら、候補リストでクリックします。
4. 結果を絞り込むには、**[!UICONTROL Similarity Cutoff]** スライダーを使用して、類似性の低い特性から高い特性に動かします。

フィルタリングが完了したら、結果ページに新しい列 **[!UICONTROL Similar Traits]** が表示されます。この列には、フィルタリング条件を満たした各データフィードから、フィルタリングした特性に類似した特性の数が表示されます。

類似した特性の完全なリストを確認するには、**[!UICONTROL Similar Traits]** 列の数字をクリックします。

>[!NOTE]
>
> Audience Marketplace には、データフィード全体からの上位 500 の類似した特性の結果が表示されます。

類似した特性の見つけ方の完全な概要については、以下のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 非公開データフィード {#private-data-feeds}

[!UICONTROL Marketplace] リストには、プロバイダーの名前および特性データが非公開として掲載されることがあります。これは、[非公開データフィード](../../../features/audience-marketplace/marketplace-private-feeds.md)であることを示しています。非公開データフィードを使用すると、販売者はデータへの購入者のアクセスを制限できます。販売者は、特別サービスや割引を提供したり、プライバシーおよびアクセス制御が重要な場合に、フィードを非公開にできます。購入者は、非公開フィードにアクセスしたい場合、サブスクリプション要求を販売者に送信する必要があります。詳しくは、[非公開データフィードのサブスクリプション購入](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)を参照してください。

>[!MORELIKETHIS]
>
>* [Audience Marketplace のプランの詳細ページについて](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [データ購入者にとっての割引](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

