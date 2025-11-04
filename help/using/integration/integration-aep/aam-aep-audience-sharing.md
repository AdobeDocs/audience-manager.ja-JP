---
description: Audience Manager と Adobe Experience Platform 間において、データ共有を有効にする方法とオーディエンスの共有方法について説明します
solution: Audience Manager
title: Audience Manager およびその他の Experience Cloud ソリューションを使用した Experience Platform のセグメント共有
keywords: AEP オーディエンス共有、AEP セグメント、Platform のセグメント、セグメント共有、オーディエンス共有、セグメントの共有、AAM AEP セグメント共有
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 94%

---

# Audience Manager およびその他の Experience Cloud ソリューションを使用した Experience Platform のセグメント共有

## 概要 {#overview}

Audience ManagerとAdobe Experience Platformの間でオーディエンスを共有する機能を使用すると、Audience Managerの特性とセグメントをAdobe Experience Platformに、Experience PlatformのセグメントをAudience Managerに共有できます。

Audience ManagerとAdobe Experience Platformの間でオーディエンスの共有を有効にするには、Experience Platformで [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=ja) と [2&rbrace;Experience Cloud Audiences&rbrace; の宛先が必要です。](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html)

Experience Platform で Audience Manager の特性とセグメントを使用して、Audience Manager データを顧客プロファイルに追加し、Experience Platform の[セグメント化サービス](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)を活用することができます。

Audience Manager では、次のような、データ管理プラットフォームのユースケースに対して Experience Platform のセグメントを使用できます。

* [サードパーティデータ](/help/using/overview/data-types-collected.md#third-party-data)をセグメントに追加する
* [アルゴリズムモデリング](/help/using/features/algorithmic-models/understanding-models.md)
* Experience Platform の[宛先カタログ](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html?lang=ja)でまだサポートされていない宛先に対してセグメントをアクティブ化します。

さらに、Experience Platform のセグメントは、[コアサービス](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=ja)を介して他の Experience Cloud ソリューションと共有されます。

>[!IMPORTANT]
>
> * 上記のデータ管理プラットフォームのユースケースを可能にするには、Audience Manager ライセンスが必要です。
> * コアサービスの統合を通じて、Adobe Advertising Cloud、Adobe Target、Marketo およびその他の Experience Cloud ソリューションと Experience Platform のセグメントを共有する場合、Audience Manager ライセンスは *必要ありません*。

オーディエンス共有のユースケースの概要については、次の表を参照してください。

| **ユースケース** | **Adobe Experience Platform** | **Audience Manager** | **コアサービス** |
|---------|----------|---------|---------|
| **オーディエンス共有** | <ul><li>Audience Manager データを使用した顧客プロファイルの強化</li><li>Experience Platform のセグメント化で Audience Manager データを使用する</li></ul> | <ul><li>セグメントへのサードパーティデータの追加</li><li>アルゴリズムモデリング</li><li>追加の宛先へのアクティブ化</li></ul> | Adobe Target や Advertising Cloud、Marketo など、他の Experience Cloud ソリューションで Experience Platform のセグメントを使用します。 |

{style="table-layout:auto"}

## Adobe Experience Platform での Audience Manager のセグメントと特性 {#aam-segments-traits-in-aep}

以下の節では、Audience Manager から Experience Platform へのデータ共有を有効にする方法と、Experience Platform で Audience Manager の特性とセグメントを使用する方法について説明します。

### Audience Manager から Experience Platform へのデータ共有を有効にする {#enable-aam-to-aep-data}

Audience Manager から Experience Platform にセグメントと特性を送信するには、Experience Platform ソースカタログで Audience Manager ソースコネクタを設定する必要があります。これはセルフサービスワークフローで、アドビカスタマーケアやエンジニアリングチームの関与は必要ありません。Audience Manager ソースコネクターを設定するには、次を参照してください。

* [Audience Manager ソース](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=ja)
* [UI での Adobe Audience Manager ソース接続の作成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=ja)

>[!IMPORTANT]
>
>アドビは、以下に示すように、「**[!UICONTROL Select all segments]**」および「**[!UICONTROL Select all traits]**」オプションを選択せずに接続を設定することをお勧めします。サイズの大きい Audience Manager セグメント母集団の取り込みは、Audience Manager ソースを使用して Audience Manager セグメントをプラットフォームに初めて送信する際に、合計プロファイル数に直接影響します。つまり、すべてのセグメントを選択すると、ライセンス使用権限を超えてプロファイル数がカウントされる可能性があります。
>
>![Audience Manager ソースコネクターに接続するワークフローで「すべてのセグメントを選択」および「すべての特性を選択」オプションがオフになっていることを示すスクリーンショット。](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Experience Platform での Audience Manager の特性とセグメントの使用 {#use-aam-data-in-aep}

Audience Manager ソースコネクターを設定して、Audience Manager から特性とセグメントを読み込むと、Audience Manager データがセグメントワークフローの **Audiences** として Experience Platform に表示されます。Experience Platform での Audience Manager のセグメントと特性について詳しくは、次を参照してください。

* [セグメント化サービスの概要](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja#audiences)
* [Experience Platform セグメントビルダーユーザーガイド](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja#audiences)

## Audience Manager における Adobe Experience Platform のセグメント {#aep-segments-in-aam}

以下の節では、Experience Platform から Audience Manager へのデータ共有を有効にする方法と、Audience Manager で Experience Platform のセグメントを使用する方法について説明します。

### Experience Platform から Audience Manager へのデータ共有を有効にする {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> ここでは、Experience PlatformからAudience Managerへの従来のセグメント共有の統合について説明します。 Adobeのお客様の担当者のサポートなしで、この統合を設定できるようになりました。 詳しくは、[Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html) の宛先に関するドキュメントを参照してください。

>[!NOTE]
>
> この機能へのアクセスのロックを解除するには、アドビカスタマーサクセスマネージャーまたはカスタマーケアにお問い合わせください。

セグメントを Experience Platform から Audience Manager に送信するには、カスタマーケアまたはカスタマーサクセスマネージャーに問い合わせる必要があります。カスタマーケアおよびカスタマーサポート管理チームは、チケットを提出して（テンプレートチケット AAM-52354 を参照）、Platform から Audience Manager への接続を有効にする必要があります。

接続が正しく設定されていることを確認するには、Platform から Audience Manager に転送するデータのプランを必ず共有するようにしてください。例えば、Adobe Target に送信するセグメントで地域データを共有する必要がある場合、この情報をチケットで伝える必要があります。Experience Platform から Audience Manager へのデータ共有接続は、リクエストが送信されてから 6 営業日以内に設定されます。

### Audience Manager で Adobe Experience Platform のセグメントを使用する {#use-aep-data-in-aam}

Experience Platform で作成したセグメントは、次の構成ルールを使用し、シグナル、特性、およびセグメントとして Audience Manager インターフェイスに表示されます。

* シグナル：各 Experience Platform のセグメントに対し、フォーム `segID = segment ID` にシグナルが表示されます。
* 特性：特性ルールは、Experience Platform のセグメントの ID です。
* セグメント：このセグメントは、上記の特性で構成されます。

### シグナル {#aep-segments-as-aam-signals}

**[!UICONTROL Audience Data > Signals > General Online Data]** を選択し、`SegId` で Experience Platform から来るシグナルを探します。この画面をデバッグ目的で使用し、Experience Platform と Audience Manager の統合が正しく設定されているかどうかを確認できます。

![シグナルダッシュボードの Audience Manager で Experience Platform シグナルを確認する](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### 特性 {#aep-segments-as-aam-traits}

Audience Manager は、特性ストレージに「**Experience Platform 特性**」という特性フォルダーを自動的に作成します。

![Experience Platform ダッシュボードの特性](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

自動的に作成された特性を、他の特性とともにセグメントで使用できます。例えば、Experience Platform のセグメントから作成した特性と、[Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md) で取得したサードパーティの特性を混在させることができます。

Experience Platform のセグメントから自動的に作成された特性の例については、以下のスクリーンショットを参照してください。

![Experience Platform の特性](/help/using/integration/integration-aep/assets/aep-trait.png)


| 項目番号 | 名前 | 説明 |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Experience Platform のセグメントから作成された特徴は、Audience Manager でオンボードの特性として作成されます。 |
| 2 | [!UICONTROL Data Source] | 自動的に作成されます。Experience Platform のセグメントから自動的に作成されたすべての特性とセグメントは、**[!UICONTROL Adobe Experience Platform Audience Sharing]** のデータソースに保存されます。 |
| 3 | [!UICONTROL Integration Code] | 統合コードは、Experience Platform のセグメント ID に対応します。 |
| 4 | [!UICONTROL Trait Expression] | 特性の式は `segID = segment ID in Experience Platform` です。 |
| 5 | [!UICONTROL Segments with this Trait] | この特性を構成として使用する、自動的に作成されたセグメント。 |

{style="table-layout:auto"}

### セグメント {#aep-segments-as-aam-segments}

Audience Manager は、セグメントストレージに「**Experience Platform のセグメント**」というセグメントフォルダーを自動的に作成します。

![ダッシュボードのスクリーンショット](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Experience Platform のセグメントから自動的に作成されたセグメントの例については、以下のスクリーンショットを参照してください。

![セグメントのスクリーンショット](/help/using/integration/integration-aep/assets/aep-segment.png)

| 項目番号 | 名前 | 説明 |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | 統合コードは、Experience Platform のセグメント ID に対応します。 |
| 2 | [!UICONTROL Data Source] | 自動的に作成されます。Experience Platform のセグメントから自動的に作成されたすべての特性とセグメントは、**[!DNL Adobe Experience Platform Audience Sharing]** のデータソースに保存されます。 |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** は、自動的に作成されたセグメントが、Experience Platform の結合ポリシーセットに従うことを示します。 |
| 4 | [!UICONTROL Segment Rule] | このセグメントは、[特性](#aep-segments-as-aam-traits)の節で説明されている特性で構成されます。 |

{style="table-layout:auto"}

## Experience Platform での Audience Manager データ書き出しコントロールのサポート {#aam-data-export-control-in-aep}

Experience Platform でのデータ使用量のコンプライアンスを強化するために、該当するすべてのデータセットおよびフィールドに適切な[データラベル](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=ja)を付与する必要があります。さらに、[Data Usage Labeling and Enforcement（DULE）フレームワーク](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=ja#dule-framework)で概要を説明しているように、これらのラベルに対する特定のマーケティングアクションに対して、[データポリシー](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=ja)を有効にする必要があります。

Audience Manager と Experience Platform の間でオーディエンスを共有するプロセスでは、Audience Manager セグメントに適用されたデータ書き出しコントロールは、Experience Platform データガバナンスで認識される同等のラベルやマーケティングアクションに変換されます。また、その逆も可能です。

>[!NOTE]
>
>データ書き出しコントロールの詳細については、[データ書き出しコントロールのドキュメント](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=ja)を参照してください。
>
>このドキュメントでは、特定の Audience Manager データの書き出しコントロールを、Platform のデータラベルおよびマーケティングアクションにどのようにマッピングするかについて説明します。

### データ使用ラベルに対するデータ書き出しコントロール

次の表に、特定のデータ書き出しコントロールが、認識されるデータラベルにどのように対応しているかを示します。

| データ書き出しコントロール | データラベル |
| --- | --- |
| 個人情報と共に使用することはできません。 | C3：データを組み合わせたり、直接識別できる情報と組み合わせて使用することはできません。 |
| オフサイトの広告ターゲティングには使用できません。 | C5：コンテンツや広告の、関心に基づたクロスサイトターゲティングにデータを使用することはできません。 |
| オンサイトの広告ターゲティングには使用できません。 | C6：データをオンサイトのターゲティングには使用できません。 |
| オンサイトのパーソナライズ機能には使用できません。 | C7：データをコンテンツのオンサイトターゲティングに使用することはできません。 |

{style="table-layout:auto"}

### マーケティングアクションへのデータ書き出しコントロール

次の表は、特定のデータ書き出しラベルを、認識されているマーケティングアクションにマッピングする仕組みの概要を示しています。

| データ書き出しラベル | マーケティングのアクション |
| --- | --- |
| この宛先は個人情報（PII）との組み合わせを有効にすることができます | PII と組み合わせる |
| この宛先はオフサイト広告ターゲティングに使用できます | クロスサイトターゲティング |
| この宛先はオンサイト広告ターゲティングに使用できます | オンサイト広告 |
| この宛先は、オンサイト広告パーソナライズ機能に使用できます | オンサイトのパーソナライズ機能 |

{style="table-layout:auto"}

## Audience Manager と Experience Platform の間のセグメント母集団の違いの理解 {#aep-aam-segment-population-differences}

セグメント母集団の数は、Audience Manager と Experience Platform のセグメント間で異なる可能性があります。類似または同一のオーディエンスのセグメント数が近づくのに対して、母集団の違いは、次の要因による可能性があります。

### Experience Platform でのセグメントの評価

Audience Manager は、インターフェイスのレポート番号を 1 日に 1 回更新します。この更新のタイミングが、Experience Platform のセグメント評価の時間に合致することはほとんどありません。

### プロファイルの結合ルールと結合ポリシーの違い

Audience Manager の[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md)と Experience Platform の[[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html?lang=ja)の動作は異なり、それぞれで使用される ID グラフは異なります。これにより、セグメント母集団間でのいくつかの違いが想定されます。

>[!NOTE]
>
> Experience Platform から Audience Manager にセグメントを共有する場合は、Platform 組織の [デフォルトの結合ポリシー](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=ja#default-merge-policy)が Audience Manager で共有された[セグメントで使用される結合ポリシー](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=ja#merge-policies)よりも優先されます。例えば、共有セグメントの結合ポリシーで [ID のステッチ](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja#configure)が許可されていても、組織のデフォルトの結合ポリシーでは許可されていない場合、Platform と Audience Manager の間の母集団の違いが生じる可能性があります。

### Experience Platform でのセグメントの構成

Adobe Experience Platform と Audience Manager の統合では、すべての顧客に対して多くの標準 [ID 名前空間](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ja#identity-types)を共有します。これには、ECID、IDFA、GAID、ハッシュ化された電子メールアドレス（EMAIL_LC_SHA256）、AdCloud ID などが含まれます。Experience Platform のセグメントで、認定されたプロファイルのプライマリ ID としてこれらのいずれかを使用している場合、プロファイルは Audience Manager の特性およびセグメントにカウントされます。

>[!NOTE]
>
> ID が生の電子メールをキーに設定している Experience Platform のオーディエンスは、Audience Manager には表示されません。

例えば、「すべての顧客」という Experience Platform のセグメントがあり、認定プロファイルが CRM ID、ECID、IDFA、生の電子メールアドレスおよびハッシュ化された電子メールアドレスの場合、Audience Manager 内の対応するセグメントには、ECID、IDFA およびハッシュ化された電子メールアドレスのキーオフされたプロファイルのみが含まれます。Audience Manager のセグメントの母集団は、Experience Platform のセグメントの母集団よりも小さくなります。

![Experience Platform から Audience Manager へのセグメント共有 — セグメントの構成](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [セグメント化サービスの概要](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja#audiences)
>* [Experience Platform セグメントビルダーユーザーガイド](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja#audiences)
>* [Audience Manager コネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=ja)
