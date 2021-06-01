---
description: すべてのシグナルから新しい特性を作成し（特性内ですでに使用しているものを含む）、特性作成後に認定する将来のオーディエンスを取り込みます。
seo-description: すべてのシグナルから新しい特性を作成し（特性内ですでに使用しているものを含む）、特性作成後に認定する将来のオーディエンスを取り込みます。
seo-title: シグナルからの特性の作成
title: シグナルからの特性の作成
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: 'データエクスプローラ '
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 100%

---

# シグナルからの特性の作成

すべてのシグナルから新しい特性を作成し（特性内ですでに使用しているものを含む）、特性作成後に認定する将来のオーディエンスを取り込みます。ビデオで詳細なデモを視聴するか、詳細情報をお読みください。

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## シグナルダッシュボードでの特性の作成 {#create-traits-from-signal-dashboard}

[!UICONTROL Signal Dashboard] を使用すれば、[!UICONTROL Top Unused Signals]、[!UICONTROL New Unused Signals]、および保存済みの検索から新しい特性を作ることができます。

新しい特性を作成する場合、シグナルタイプに応じて以下の特性タイプが事前設定されます。

* リアルタイムのシグナル、アクションにつながるログファイルおよび [!DNL Adobe Analytics] のシグナルの場合は&#x200B;**[!UICONTROL Rule-based]**&#x200B;の特性

* オンボードのシグナルの場合は&#x200B;**[!UICONTROL Onboarded]**&#x200B;の特性

**[!UICONTROL Signal Dashboard]**&#x200B;で新しい特性を作成するには、特性に使用するシグナルを選択し、**[!UICONTROL Create Rule-Based Trait]** リンクまたは **[!UICONTROL Create Onboarded Trait]** リンクのいずれか該当する方をクリックします。

![](assets/signals-create-trait.png)

**[特性ビルダー](../../features/traits/about-trait-builder.md)**&#x200B;が表示され、新規特性を作成できます。

## シグナル検索での特性の作成 {#create-traits-from-signal-search}

[!UICONTROL Signal Dashboard]に表示されない使用済みまたは未使用のシグナルに基づいて、特性を作成します。

特定のシグナルを検索し、検索結果に基づいてルールベースまたはオンボードの特性を作成します。手順は次のとおりです。

1. **[!UICONTROL Audience Data > Signals > Search]** を開き、目的のキー値ベアに応じて検索を実行します。すべての結果を表示する場合は、キー値ペアを入力せずに「**[!UICONTROL Search]**&#x200B;検索」をクリックします。
2. 検索結果のリストで、特性に使用するシグナルを選択します。
   * 1 つのシグナルから特性を作成するには、**[!UICONTROL Create Rule-Based Trait]** リンクまたは **[!UICONTROL Create Onboarded Trait]** リンクのいずれか該当する方をクリックします。
   * 複数のシグナルから特性を作成するには、各シグナルのチェックボックスをオンにして、「**[!UICONTROL Create Trait from Multiple Signals]**」をクリックします。

   >[!NOTE]
   >特性の作成元に指定できるのは、同一タイプのシグナルのみです。リアルタイムのシグナルとオンボードのシグナルを組み合わせて特性を作成することはできません。
   >
   > ![](assets/signals-create-trait-search.png)
   >また、特性は使用済みのシグナルからも作成できます。特性で既に使用されているシグナルについては、**[!UICONTROL Included in Traits]** 列に特性の数が表示されます。矢印をクリックすると、該当するシグナルを含む特性が表示されます。
   >
   >![](assets/signals-used-traits.png)

3. **[特性ビルダー](../../features/traits/about-trait-builder.md)**&#x200B;を使用して、新しい特性を作成します。
