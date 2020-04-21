---
description: この記事では、Audience Manager と Adobe Experience Platform の間でオーディエンスを共有する方法について説明します。
seo-description: この記事では、Audience Manager と Adobe Experience Platform の間でオーディエンスを共有する方法について説明します。
seo-title: Audience Manager と Adobe Experience Platform の間でのオーディエンスの共有
solution: Audience Manager
title: Audience Manager と Adobe Experience Platform の間でのオーディエンスの共有
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: ht
source-git-commit: efc07cb0aacc31f3708c98e1c82c195c202c10ef

---


# Audience Manager と Adobe Experience Platform の間でのオーディエンスの共有 {#aam-aep-audience-sharing}

>[!NOTE]
>
> この機能へのアクセスをロック解除したい場合は、アドビの販売担当者にお問い合わせください。

## 概要 {#overview}

Audience Manager と Adobe Experience Platform の間でオーディエンス共有機能を使用すると、Audience Manager の特性とセグメントを Adobe Experience Platform と共有できます。また、その逆も可能です。Audience Manager と Adobe Experience Platform の間でオーディエンス共有を有効にするには、[Audience Manager コネクタ](https://docs.adobe.com/content/help/en/experience-platform/source-connectors/adobe-applications/audience-manager.html)が必要です。

Experience Platform で Audience Manager の特性とセグメントを使用して、Audience Manager データを顧客プロファイルに追加し、Experience Platform の[セグメント化サービス](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)を活用することができます。

Audience Manager では、次のように、Data Management Platform のユースケースに対して Experience Platform セグメントを使用できます。
* [サードパーティデータ](/help/using/overview/data-types-collected.md#third-party-data)をセグメントに追加する
* [アルゴリズムモデリング](/help/using/features/algorithmic-models/understanding-models.md)
* Experience Platform の[宛先カタログ](https://docs.adobe.com/content/help/ja-JP/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)でまだサポートされていない宛先に対してセグメントをアクティブ化します。

さらに、Experience Platform のセグメントは、[コアサービス](https://docs.adobe.com/content/help/ja-JP/core-services/interface/experience-cloud.html)を介して他の Experience Cloud ソリューションと共有されます。

 <br>

オーディエンス共有のユースケースの概要については、次の表を参照してください。

| **ユースケース** | **Adobe Experience Platform** | **Audience Manager** | **コアサービス** |
---------|----------|---------|---------
| **オーディエンス共有** | <ul><li>Audience Manager データを使用した顧客プロファイルの強化</li><li>Experience Platform セグメントでの Audience Manager データの使用</li></ul> | <ul><li>セグメントへのサードパーティデータの追加</li><li>アルゴリズムモデリング</li><li>追加の宛先へのアクティブ化</li></ul> | Adobe Target や Analytics など、他の Experience Cloud ソリューションで Experience Platform セグメントを使用します。 |

 <br>

## Adobe Experience Platform での Audience Manager のセグメントと特性 {#aam-segments-traits-in-aep}

Audience Manager の特性とセグメントは、セグメントワークフローの&#x200B;**オーディエンス**&#x200B;として Experience Platform に表示されます。Experience Platform での Audience Manager のセグメントと特性について詳しくは、次を参照してください。

* [セグメント化サービスの概要](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Experience Platform セグメントビルダーユーザーガイド](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager コネクタ](https://docs.adobe.com/content/help/en/experience-platform/source-connectors/adobe-applications/audience-manager.html)

 <br>

## Audience Manager の Adobe Experience Platform セグメント {#aep-segments-in-aam}

Experience Platform で作成したセグメントは、次の構成ルールを使用し、特性とセグメントとして Audience Manager インターフェイスに表示されます。
* 特性：特性ルールは、Experience Platform セグメントの ID です。
* セグメント：このセグメントは、上記の特性で構成されます。

### 特性 {#aep-segments-as-aam-traits}

Audience Manager は、特性ストレージに「**Experience Platform 特性**」という特性フォルダーを自動的に作成します。

![Experience Platform ダッシュボードの特性](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

自動的に作成された特性を、他の特性とともにセグメントで使用できます。例えば、Experience Platform セグメントから作成した特性と、[Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md) で取得したサードパーティの特性を混在させることができます。

Experience Platform セグメントから自動的に作成された特性の例については、以下のスクリーンショットを参照してください。

![Experience Platform の特性](/help/using/integration/integration-aep/assets/aep-trait.png)


| 項目番号 | 名前 | 説明 |
---------|----------|---------
| 1 | 特性タイプ | Experience Platform セグメントから作成された特徴は、Audience Manager でオンボードの特性として作成されます。 |
| 2 | データソース | 自動的に作成されます。Experience Platform セグメントから自動的に作成されたすべての特性とセグメントは、**Adobe Experience Platform オーディエンス共有**&#x200B;のデータソースに保存されます。 |
| 3 | 統合コード | 統合コードは、Experience Platform のセグメント ID に対応します。 |
| 4 | 特性の式 | 特性の式は `segID = segment ID in Experience Platform` です。 |
| 5 | この特性を持つセグメント | この特性を構成として使用する、自動的に作成されたセグメント。 |

 <br>

### セグメント {#aep-segments-as-aam-segments}

Audience Manager は、セグメントストレージに「**Experience Platform セグメント**」というセグメントフォルダーを自動的に作成します。

![ダッシュボードのスクリーンショット](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Experience Platform セグメントから自動的に作成されたセグメントの例については、以下のスクリーンショットを参照してください。

![セグメントのスクリーンショット](/help/using/integration/integration-aep/assets/aep-segment.png)

| 項目番号 | 名前 | 説明 |
---------|----------|---------
| 1 | 統合コード | 統合コードは、Experience Platform のセグメント ID に対応します。 |
| 2 | データソース | 自動的に作成されます。Experience Platform セグメントから自動的に作成されたすべての特性とセグメントは、**Adobe Experience Platform オーディエンス共有**&#x200B;のデータソースに保存されます。 |
| 3 | プロファイル結合ルール | **外部結合ポリシー**&#x200B;は、自動的に作成されたセグメントが、Experience Platform で設定された結合ポリシーに従うことを示します。 |
| 4 | セグメントルール | このセグメントは、[「特性」セクション](#aep-segments-as-aam-traits)で説明されている特性で構成されます。 |
