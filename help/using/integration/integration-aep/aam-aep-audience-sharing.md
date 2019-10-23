---
description: この記事では、Audience ManagerとAdobe Experience Platform間でオーディエンスを共有する方法について説明します。
seo-description: この記事では、Audience ManagerとAdobe Experience Platform間でオーディエンスを共有する方法について説明します。
seo-title: Audience ManagerとAdobe Experience Platform間でのオーディエンスの共有
solution: Audience Manager
title: Audience ManagerとAdobe Experience Platform間でのオーディエンスの共有
keywords: AEPオーディエンス共有， AEPセグメント，プラットフォームセグメント
translation-type: tm+mt
source-git-commit: 421f15b79fa647bf4fbf71a425c7f7792fb302e5

---


# Audience ManagerとAdobe Experience Platform間でのオーディエンスの共有 {#aam-aep-audience-sharing}

>[!NOTE]
>
>このページには、Audience Managerおよび *Adobe Experience Platformのお客様が使用できる機能について説明するベータ版ドキ* ュメントが含まれています。 このドキュメントは、最終製品リリースの前に変更される場合があります。
>
> この機能へのアクセスをロック解除するには、アドビの販売担当者にお問い合わせください。

## 概要 {#overview}

Audience ManagerとAdobe Experience Platform間でオーディエンスを共有する機能を使用すると、Audience Managerの特徴とセグメントをAdobe Experience Platformと共有できます。また、その逆も可能です。

Experience PlatformのAudience Managerの特徴とセグメントを使用して、Audience Managerデータを顧客プロファイルに追加し、Experience Platformのセグメント化サービスの利点を活かすこ [とができます](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)。

Audience Managerでは、Data Management Platformの使用例に対して次のようなエクスペリエンスプラットフォームセグメントを使用できます。
* サード [パーティデータの](/help/using/overview/data-types-collected.md#third-party-data) 、セグメントへの追加
* [アルゴリズムによるモデリング](/help/using/features/algorithmic-models/understanding-models.md);
* エクスペリエンスプラットフォームでは現在サポートされていない宛先へのセグメントのアクティブ化を参照してください。

さらに、Experience Platformのセグメントは、コアサービスを介して他のExperience cloudソリューションと [共有されます](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)。

 <br>

オーディエンス共有の使用例の概要については、次の表を参照してください。

| `*` | **Adobe Experience Platform** | **Audience Manager** | **コアサービス** |
---------|----------|---------|---------
| **オーディエンス共有の使用例** | <ul><li>Audience Managerデータによる顧客プロファイルの強化</li><li>Experience PlatformセグメントでのAudience Managerデータの使用</li></ul> | <ul><li>セグメントへのサードパーティデータの追加</li><li>アルゴリズムによるモデリング</li><li>追加の宛先へのアクティブ化</li></ul> | Adobe targetやAnalyticsなど、他のExperience cloudソリューションでExperience Platformセグメントを使用します。 |

 <br>

## Adobe Experience PlatformのAudience Managerのセグメントと特徴 {#aam-segments-traits-in-aep}

Audience Managerの特徴とセグメントは、セグメントワークフローでオーディエンスとし **てExperience Platform** に表示されます。 Experience PlatformでのAudience Managerのセグメントと特徴について詳しくは、次を参照してください。

* [Segmentation Serviceの概要](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)
* [エクスペリエンスプラットフォームセグメントビルダーユーザーガイド](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segment-builder-guide.md)

 <br>

## Audience ManagerのAdobe Experience Platformセグメント {#aep-segments-in-aam}

Experience Platformで作成したセグメントは、次の構成ルールを使用して、特徴とセグメントとしてAudience Managerインターフェイスに表示されます。
* 特性：特性ルールは、エクスペリエンスプラットフォームセグメントのIDです。
* セグメント：このセグメントは、上記の特性で構成されます。

### 特性 {#aep-segments-as-aam-traits}

Audience Managerは、特性ストレージに **Experience Platform Traitsという名前の特性フォルダーを** 、自動的に作成します。

![Experience Platformダッシュボードの特徴](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

自動的に作成された特性を、他の特性と並べてセグメントで使用できます。 例えば、Experience Platformセグメントから作成した特性を、 [Audience Marketplaceで取得したサードパーティの特性と混在させることができます](/help/using/features/audience-marketplace/audience-marketplace.md)。

エクスペリエンスプラットフォームセグメントから自動的に作成された特性の例については、以下のスクリーンショットを参照してください。

![エクスペリエンスプラットフォームの特性](/help/using/integration/integration-aep/assets/aep-trait.png)


| 項目番号 | 名前 | 説明 |
---------|----------|---------
| 1 | 特性タイプ | Experience Platformセグメントから作成された特徴は、Audience Managerでオンボードの特徴として作成されます。 |
| 2 | データソース | 自動的に作成されます。 エクスペリエンスプラットフォームセグメントから自動的に作成されたすべての特徴とセグメントは、 **Adobe Experience Platformオーディエンス共有のデータソースに保存されます**。 |
| 3 | Integration Code | 統合コードは、Experience PlatformのセグメントIDに対応します。 |
| 4 | Trait Expression | 特性表現はです `segID = segment ID in Experience Platform`。 |
| 5 | この特性を持つセグメント | この特性を構成として使用する、自動的に作成されたセグメント。 |

 <br>

### セグメント {#aep-segments-as-aam-segments}

Audience Managerは、セグメントストレージに「 **Experience Platform Segments** 」というセグメントフォルダーを自動的に作成します。

![ダッシュボードのスクリーンショット](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

エクスペリエンスプラットフォームセグメントから自動的に作成されたセグメントの例については、以下のスクリーンショットを参照してください。

![セグメントのスクリーンショット](/help/using/integration/integration-aep/assets/aep-segment.png)

| 項目番号 | 名前 | 説明 |
---------|----------|---------
| 1 | Integration Code | 統合コードは、Experience PlatformのセグメントIDに対応します。 |
| 2 | データソース | 自動的に作成されます。 エクスペリエンスプラットフォームセグメントから自動的に作成されたすべての特徴とセグメントは、 **Adobe Experience Platformオーディエンス共有のデータソースに保存されます**。 |
| 3 | Profile Merge Rule | **「外部結合ポリシー** 」は、自動的に作成されたセグメントが、Experience Platformで設定された結合ポリシーに従うことを示します。 |
| 4 | セグメントルール | このセグメントは、「特徴」セクションで説明されている特性 [で構成されます](#aep-segments-as-aam-traits)。 |