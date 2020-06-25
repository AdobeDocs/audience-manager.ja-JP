---
description: Audience Manager はファーストパーティ、セカンドパーティ、サードパーティのデータの収集および管理をサポートします。
seo-description: Audience Manager はファーストパーティ、セカンドパーティ、サードパーティのデータの収集および管理をサポートします。
seo-title: 収集されるデータのタイプ
solution: Audience Manager
title: 収集されるデータのタイプ
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: overview
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 72%

---


# 収集されるデータのタイプ {#types-of-data-collected}

[!DNL Audience Manager] はファーストパーティ、セカンドパーティ、サードパーティのデータの収集および管理をサポートします。

複数のサイロに格納された顧客情報アセットを解放することは、今日、企業が直面しているデータに関する最大の課題の 1 つです。From [!DNL CRM] databases, to registration systems, to ad servers, and so forth, companies require tools that help centralize valuable data and manage customer/audience information as a single strategic data asset. [!DNL Audience Manager] は、孤立した顧客情報を解放し、複数のソースからのデータ収集を管理するのに役立ちます。Collected data can be managed based on data element time-to-live ([!DNL TTL]) values, which helps the publisher control data expiration across all sources. [!DNL Audience Manager] は、以下のデータタイプの管理を支援するように設計されています。

| データタイプ | データの発生源 |
|---|---|
| **ファーストパーティ** | 顧客。データは、オンライン（Web サイトでの消費者とのやり取り）またはオフラインで収集されます。 |
| **セカンドパーティ** | 戦略的パートナーおよび広告主。 |
| **サードパーティ** | データプロバイダーおよびデータ交換。データには、インテント、デモグラフィック、ソーシャル／ライフスタイル、サイコグラフィックなどの情報が含まれる可能性があります。 |

## ファーストパーティデータ収集 {#first-party-data}

First-party data collection is a main [!DNL Audience Manager] feature. コアとなるこの機能は、マーケティングプログラムの土台とするために、または他のデータソースに対してターゲティングもしくはモデリングをおこなうために独自データを使用するお客様（パブリッシャーや広告主）のニーズに応えるものです。

[!DNL Audience Manager] では、クライアントと協力しながらデータ戦略を把握したうえで、その戦略を独自のデータ収集プランに取り込みます。弊社のパートナーソリューションチームはお客様と連携して、サイトや生データのシグナルなどの Web サイト上のユーザーインタラクションを評価します。アドビはこの情報を基に、インベントリの様々なページからユーザーレベルのデータシグナルを取得するための、お客様専用のデータ収集戦略を作成するお手伝いをします。収集されたデータは保存され、定義済みの分類に再マッピングされます。これらはビジネス上のニーズの変化に応じていつでも更新できます。

次の例では、サンプルのショッピングページからどのようなデータ要素を取得できるかを示します。

![買い物かごのデータ](assets/shopping-cart-data.png)

| 項目 | 説明 |
|---|---|
| 1 | **性別**。買い物客の性別は、通常、名を見ればわかります。この例では、買い物客の名は Mary なので、女性であることがわかります。名前は Audience Manager には保存されません。 |
| 2 | **関心**。買い物かごの品目は、様々な関心を示す場合があります。例では、Mary はフィットネス機器を多く購入しています。 |
| 3 | **住居のタイプ**。配送先や請求先の住所に基づいて、Mary がフィットネス機器を自分用と会社用のどちらで購入したかを推測できます。 |
| 4 | **場所**.[!DNL ZIP] コードは、場所を特定する際に、 [!DNL IP] アドレスよりも信頼性が高くなります。 |
| 5 | **プロモーションの親和性**。プロモーションコードやギフトカードを使用する買い物客はおそらく、最安値を探すバーゲンのプロです。 |
| 6 | **購買力**。Price data correlated with [!DNL ZIP+4] codes indicate spending power of a given location. |

After the raw data is collected, it gets mapped back to customer-defined traits within the [!DNL Audience Manager] platform. 分類もデータマッピングも、データ収集コードを変更することなく、いつでも調整できます。

## セカンドパーティデータ収集 {#second-party-data}

セカンドパーティデータは戦略ビジネスパートナーのデータです（パブリッシャーのデータではありません）。この情報はファーストパーティデータと同様に収集および管理されます。

セカンドパーティデータのシナリオでは、広告主が自身のデータアセットをパブリッシャーに送信し、その情報をパブリッシャーのデータと組み合わせてよりターゲティングされた広告プログラムを展開します。さらに、パブリッシャーは他の広告主と連携することで、オーディエンスプールを拡大することができます。In most cases, these arrangements involve contractual relationships limited to putting the [!DNL Audience Manager] container tag on the partner site to facilitate data collection and sharing.

セカンドパーティデータの収集およびリマーケティングの例としては、ある衣料販売店が製品に関するデータを収集し、これらの情報を主要なパートナーと共有するようなケースが挙げられます。In this case, the retailed could serve different ads across an [!DNL Audience Manager] partner site for consumers who chose various jacket colors and sizes.

![](assets/shopping-cart-traits.png)

## サードパーティデータ収集 {#third-party-data}

Third-party data is information collected and shared by vendors outside of [!DNL Audience Manager].

Third-party data can be used to qualify existing data [!UICONTROL segments] (for example, age, household income, and so forth), provide data that is in demand but not otherwise available, or be used in lookalike modeling against a known user base from first-party and second-party data. [!DNL Audience Manager] は様々なサードパーティデータプロバイダーと連携しています。アドビは、お客様がこれらのデータプロバイダーが収集するデータのタイプを理解し、個々のプロバイダーに応じて適切な戦略取引を構築するお手伝いをします。

>[!NOTE]
>
>[!DNL Audience Manager] でサポートされるサードパーティデータプロバイダーの完全なリストについては、[Adobe Audience Finder](https://www.adobe-audience-finder.com/)/を参照してください。

[!DNL Audience Manager] 使用可能なデータセットとデータセットに基づいて、他のデータプロバイダー [!DNL APIs] と統合できます。 データ収集は、ユーザーがサイトを表示したときにリアルタイムでおこなわれるか、またはユーザーがサイトを退出後、パートナー間で ID 同期がおこなわれ、サーバー間データ転送がおこなわれるアウトオブバウンド方式でおこなわれます。In either case, [!DNL Audience Manager] clients get the benefit of having third-party data synchronized on our platform, which means each client, or domain, does not have to perform its own synchronization. これにより、ページからのサーバー呼び出しを減らしながら、リーチを拡大することができます。

## マッチングパートナー {#match-partners}

クライアントの多くは、サードパーティのデータマッチング企業とパートナー連携しています。これらの企業は登録を伴う各種サイトとつながっており、企業が持つ登録ネットワークに基づき、リアルタイムで顧客データファイルのマッチングをおこないます。

![data-provider-match](assets/data-provider-match.png)
