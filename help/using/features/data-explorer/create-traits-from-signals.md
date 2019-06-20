---
description: 特性で既に使用されている、すべてのシグナルから新しい特性を作成し、特性作成後に資格を持つ将来のオーディエンスを捕捉します。
seo-description: 特性で既に使用されている、すべてのシグナルから新しい特性を作成し、特性作成後に資格を持つ将来のオーディエンスを捕捉します。
seo-title: シグナルからの特性の作成
title: シグナルからの特性の作成
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# シグナルからの特性の作成

特性で既に使用されている、すべてのシグナルから新しい特性を作成し、特性作成後に資格を持つ将来のオーディエンスを捕捉します。詳細なデモについては、ビデオを視聴してください。詳細については、以下を参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12&captions=jpn)

## シグナルダッシュボードでの特性の作成 {#create-traits-from-signal-dashboard}

[!UICONTROL Signal Dashboard] これにより [!UICONTROL Top Unused Signals]、および [!UICONTROL New Unused Signals]保存した検索から新しい特性を作成できます。

新しい特性を作成する場合、シグナルタイプに応じて以下の特性タイプが事前設定されます。

* **[!UICONTROL Rule-based]** 特性、実行可能なログファイルおよび [!DNL Adobe Analytics] シグナルの特性。

* **[!UICONTROL Onboarded]** オンボーブ信号の特性。

To create new traits from the **[!UICONTROL Signal Dashboard]**, identify the signal that you want to use in the trait, then click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.

![](assets/signals-create-trait.png)

**[特性ビルダー](../../features/traits/about-trait-builder.md)** が表示され、新規特性を作成できます。

## シグナル検索での特性の作成 {#create-traits-from-signal-search}

Create traits based on used or unused signals that are not shown in the [!UICONTROL Signal Dashboard].

特定のシグナルを検索し、検索結果に基づいてルールベースまたはオンボードの特性を作成します。手順は次のとおりです。

1. Go to **[!UICONTROL Audience Data > Signals > Search]** and run a search based on the key-value pairs that you are looking for, or click **[!UICONTROL Search]** without entering any key-value pair to display all results.
2. 検索結果のリストで、特性に使用するシグナルを選択します。
   * To create a trait from one signal, click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.
   * To create a trait from multiple signals, click the corresponding check box of each signal, then click **[!UICONTROL Create Trait from Multiple Signals]**.
   >[!NOTE]
   >特性の作成元に指定できるのは、同一タイプのシグナルのみです。リアルタイムのシグナルとオンボードのシグナルを組み合わせて特性を作成することはできません。
   >
   > ![](assets/signals-create-trait-search.png)
   >また、特性は使用済みのシグナルからも作成できます。特性で既に使用されているシグナルについては、**[!UICONTROL Included in Traits]** 列に特性の数が表示されます。矢印をクリックすると、該当するシグナルを含む特性が表示されます。
   >
   >![](assets/signals-used-traits.png)

3. **[特性ビルダー](../../features/traits/about-trait-builder.md)** を使用して、新しい特性を作成します。
