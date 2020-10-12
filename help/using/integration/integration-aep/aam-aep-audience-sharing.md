---
description: この記事では、Audience Manager と Adobe Experience Platform の間でオーディエンスを共有する方法について説明します。
seo-description: この記事では、Audience Manager と Adobe Experience Platform の間でオーディエンスを共有する方法について説明します。
seo-title: Audience Manager と Adobe Experience Platform の間でのオーディエンスの共有
solution: Audience Manager
title: Audience Manager と Adobe Experience Platform の間でのオーディエンスの共有
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: 6a9a48aa6d3a7a5d871ea9aabbca2c2ec1229c0e
workflow-type: tm+mt
source-wordcount: '1492'
ht-degree: 50%

---


# Audience Managerや他のExperience CloudソリューションとのExperience Platformセグメントの共有 {#aam-aep-audience-sharing}

>[!NOTE]
>
> この機能へのアクセスをロック解除したい場合は、アドビの販売担当者にお問い合わせください。

## 概要 {#overview}

Audience Manager と Adobe Experience Platform の間でオーディエンス共有機能を使用すると、Audience Manager の特性とセグメントを Adobe Experience Platform と共有できます。また、その逆も可能です。You need the [[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/connectors/adobe-applications/audience-manager.html) to enable audience sharing between Audience Manager and Adobe Experience Platform.

Experience Platform で Audience Manager の特性とセグメントを使用して、Audience Manager データを顧客プロファイルに追加し、Experience Platform の[セグメント化サービス](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)を活用することができます。

Audience Manager では、次のように、Data Management Platform のユースケースに対して Experience Platform セグメントを使用できます。
* [サードパーティデータ](/help/using/overview/data-types-collected.md#third-party-data)をセグメントに追加する
* [アルゴリズムモデリング](/help/using/features/algorithmic-models/understanding-models.md)
* Experience Platform の[宛先カタログ](https://docs.adobe.com/content/help/ja-JP/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)でまだサポートされていない宛先に対してセグメントをアクティブ化します。

さらに、Experience Platform のセグメントは、[コアサービス](https://docs.adobe.com/content/help/ja-JP/core-services/interface/experience-cloud.html)を介して他の Experience Cloud ソリューションと共有されます。

>[!IMPORTANT]
>
> * 上記のデータ管理プラットフォームの使用例を有効にするには、Audience Managerライセンスが必要です。
> * コアサービス *の統合を通じて、Adobe Ad Cloud、Adobe Target、マーケティングトおよびその他のExperience CloudソリューションとExperience Platformセグメントを共有する場合、Audience Managerライセンスは必要ありません* 。


 <br>

オーディエンス共有のユースケースの概要については、次の表を参照してください。

| **ユースケース** | **Adobe Experience Platform** | **Audience Manager** | **コアサービス** |
---------|----------|---------|---------
| **オーディエンス共有** | <ul><li>Audience Manager データを使用した顧客プロファイルの強化</li><li>Experience Platform セグメントでの Audience Manager データの使用</li></ul> | <ul><li>セグメントへのサードパーティデータの追加</li><li>アルゴリズムモデリング</li><li>追加の宛先へのアクティブ化</li></ul> | Experience Platformセグメントは、Adobe Target、Ad Cloud、Marketoなど、他のExperience Cloudソリューションで使用します。 |

 <br>

## Adobe Experience Platform での Audience Manager のセグメントと特性 {#aam-segments-traits-in-aep}

Audience Manager の特性とセグメントは、セグメントワークフローの&#x200B;**オーディエンス**&#x200B;として Experience Platform に表示されます。Experience Platform での Audience Manager のセグメントと特性について詳しくは、次を参照してください。

* [セグメント化サービスの概要](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Experience Platform セグメントビルダーユーザーガイド](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager コネクタ](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

 <br>

## Audience Manager の Adobe Experience Platform セグメント {#aep-segments-in-aam}

Experience Platformで作成したセグメントは、シグナル、特性およびセグメントとしてAudience Managerインターフェイスに表示され、次の組版規則が適用されます。

* シグナル：各Experience Platformセグメントについて、フォームにシグナルが表示され `segID = segment ID`ます。
* 特性：特性ルールは、Experience Platform セグメントの ID です。
* セグメント：このセグメントは、上記の特性で構成されます。

### シグナル {#aep-segments-as-aam-signals}

を選択 **[!UICONTROL Audience Data > Signals > General Online Data]** して、Experience Platformから来るシグナル `SegId` を探します。 この画面は、デバッグ目的で使用できます。この画面を使用して、Experience PlatformとAudience Managerの統合が正しく設定されているかどうかを確認できます。

![シグナルダッシュボードのAudience ManagerでExperience Platformシグナルを参照](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### 特性 {#aep-segments-as-aam-traits}

Audience Manager は、特性ストレージに「**Experience Platform 特性**」という特性フォルダーを自動的に作成します。

![Experience Platform ダッシュボードの特性](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

自動的に作成された特性を、他の特性とともにセグメントで使用できます。例えば、Experience Platform セグメントから作成した特性と、[Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md) で取得したサードパーティの特性を混在させることができます。

Experience Platform セグメントから自動的に作成された特性の例については、以下のスクリーンショットを参照してください。

![Experience Platform の特性](/help/using/integration/integration-aep/assets/aep-trait.png)


| 項目番号 | 名前 | 説明 |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | Experience Platform セグメントから作成された特徴は、Audience Manager でオンボードの特性として作成されます。 |
| 2 | [!UICONTROL Data Source] | 自動的に作成されます。Experience Platform セグメントから自動的に作成されたすべての特性とセグメントは、**[!UICONTROL Adobe Experience Platform Audience Sharing]** のデータソースに保存されます。 |
| 3 | [!UICONTROL Integration Code] | 統合コードは、Experience Platform のセグメント ID に対応します。 |
| 4 | [!UICONTROL Trait Expression] | 特性の式は `segID = segment ID in Experience Platform` です。 |
| 5 | [!UICONTROL Segments with this Trait] | この特性を構成として使用する、自動的に作成されたセグメント。 |

 <br>

### セグメント {#aep-segments-as-aam-segments}

Audience Manager は、セグメントストレージに「**Experience Platform セグメント**」というセグメントフォルダーを自動的に作成します。

![ダッシュボードのスクリーンショット](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Experience Platform セグメントから自動的に作成されたセグメントの例については、以下のスクリーンショットを参照してください。

![セグメントのスクリーンショット](/help/using/integration/integration-aep/assets/aep-segment.png)

| 項目番号 | 名前 | 説明 |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | 統合コードは、Experience Platform のセグメント ID に対応します。 |
| 2 | [!UICONTROL Data Source] | 自動的に作成されます。Experience Platform セグメントから自動的に作成されたすべての特性とセグメントは、**[!DNL Adobe Experience Platform Audience Sharing]** のデータソースに保存されます。 |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** は、自動的に作成されたセグメントが、Experience Platform で設定された結合ポリシーに従うことを示します。 |
| 4 | [!UICONTROL Segment Rule] | このセグメントは、[特性](#aep-segments-as-aam-traits)の節で説明されている特性で構成されます。 |

##  Experience Platform での Audience Manager データ書き出しコントロールのサポート{#aam-data-export-control-in-aep}

Experience Platformでのデータ使用量のコンプライアンスを強化するために、該当するすべてのデータセットおよびフィールドに適切な [データ使用ラベルを付与する必要があります](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html)。 さらに、 [データ使用ポリシー](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) ( [Data Usage Labeling and Enforcement(DULE)フレームワークで概要を説明しているように、これらのラベルに対する特定のマーケティングアクションに対して、](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework)データ使用ポリシーを有効にする必要があります。

Audience ManagerとExperience Platformの間でオーディエンスを共有するプロセスでは、Audience Managerセグメントに適用されたデータエクスポートコントロールは、Experience Platformデータガバナンスで認識される同等のラベルやマーケティングアクションに変換されます。

>[!NOTE]
>
>データエクスポートコントロールの詳細については、『 [データエクスポートコントロール』のドキュメントを参照してください](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/features/data-export-controls.html)。
>
>このドキュメントでは、特定のAudience Managerデータのエクスポートコントロールを、プラットフォームのデータ使用ラベルおよびマーケティングアクションにどのようにマッピングするかについて説明します。

### データ使用ラベルに対するデータエクスポートコントロール

次の表に、特定のデータエクスポートコントロールが、認識されるデータ使用ラベルにどのように対応しているかを示します。

| データエクスポートコントロール | データ使用ラベル |
| --- | --- |
| 個人が特定できる情報と共に使用することはできません。 | C3:データを組み合わせたり、直接識別できる情報と組み合わせて使用することはできません。 |
| オフサイト広告ターゲティングには使用できません | C5:データは、コンテンツや広告の関心に基づくクロスサイトターゲティングには使用できません。 |
| オンサイト広告ターゲット設定には使用できません | C6:データはオンサイト広告のターゲット設定には使用できません |
| オンサイトパーソナライゼーションには使用できません。 | C7:データは、コンテンツのオンサイトターゲティングには使用できません |

### マーケティングアクションへのデータエクスポートコントロール

次の表に、特定のデータエクスポートラベルと認識されるマーケティングアクションとの対応を示します。

| データエクスポートラベル | マーケティングのアクション |
| --- | --- |
| This destination may enable a combination with personally identifiable information (PII) | PIIと組み合わせる |
| This destination may be used for off-site ad targeting | クロスサイトターゲティング |
| This destination may be used for on-site ad targeting | オンサイト広告 |
| This destination may be used for on-site ad personalization | オンサイトパーソナライゼーション |

## Audience Manager と Experience Platform の間のセグメント母集団の違いの理解 {#aep-aam-segment-population-differences}

セグメント母集団の数は、Audience Manager と Experience Platform のセグメント間で異なる可能性があります。類似または同一のオーディエンスのセグメント番号は近い値にする必要がありますが、訪問者数の違いは、次に示す要因が原因の場合があります。

### Experience Platformでのセグメントの評価

Audience Managerは、インターフェイスのレポート番号を1日に1回更新します。   この更新のタイミングが、Experience Platformのセグメント評価の時間に合致することはほとんどありません。

### プロファイルの結合ルールと結合ポリシーの違い

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) audience managerとExperience Platform [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/ja-JP/experience-platform/profile/ui/merge-policies.html) では、動作が異なり、それぞれに使用されるアイデンティティグラフも異なります。 これにより、セグメント母集団間でのいくつかの違いが想定されます。

### Experience Platformでのセグメントの構成

Adobe Experience PlatformとAudience Managerの統合は、すべての顧客に対して多くの標準 [ID名前空間](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types) （標準ID）を共有します。ECID、IDFA、GAID、ハッシュされた電子メールアドレス(EMAIL_LC_SHA256)、AdCloud IDなど。 Experience Platformセグメントで、資格を持つプロファイルの主要なIDとしてこれらのいずれかを使用している場合、プロファイルはAudience Managerの特性とセグメントでカウントされます。

また、Audience Managerは、次の場合に、Experience Platformセグメントで使用するカスタムID名前空間の受信認証を登録できます。
* IDはプライマリとしてマークされ *、*
* 対応するクロスデバイスデータソースが既にAudience Managerに存在します。

>[!NOTE]
>
> IDが生の電子メールをキーに設定しているExperience Platformのオーディエンスは、Audience Managerに表示されません。

例えば、「すべての顧客」というExperience Platformセグメントがあり、資格を持つプロファイルがCRM ID、ECID、IDFA、生の電子メールアドレスおよびハッシュの電子メールアドレスの場合、Audience Manager内の対応するセグメントには、CRM ID、ECID、IDFAおよびハッシュされた電子メールアドレスのプロファイルのみが含まれます。 Audience Managerのセグメントの母集団は、Experience Platformのセグメントの母集団よりも小さくなります。

![Audience Managerセグメントの共有に対するExperience Platform — セグメントの構成](/help/using/integration/integration-aep/assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [セグメント化サービスの概要](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform セグメントビルダーユーザーガイド](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager コネクタ](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/connectors/adobe-applications/audience-manager.html)