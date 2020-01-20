---
description: Audience Manager において、宛先とは、データを共有する任意のサードパーティシステム（広告サーバー、DSP、広告ネットワークなど）になります。Destination Builder とは、Cookie、URL、またはサーバー間通信ベースの宛先の作成および管理をおこなうために使用するツールです。
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: Audience Manager において、宛先とは、データを共有する任意のサードパーティシステム（広告サーバー、DSP、広告ネットワークなど）になります。Destination Builder とは、Cookie、URL、またはサーバー間通信ベースの宛先の作成および管理をおこなうために使用するツールです。
seo-title: 宛先
solution: Audience Manager
title: 宛先
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
translation-type: tm+mt
source-git-commit: 431a254f1a70958db29621a59acc6239d2a6b005

---


# 宛先の概要 {#destinations}

Audience Manager において、宛先とは、データを共有する任意のサードパーティシステム（広告サーバー、[!DNL DSP]、広告ネットワークなど）になります。[!UICONTROL Destination Builder] は、Cookie、[!DNL URL]、またはサーバー間の宛先の作成と管理に使用するツールです。

## 目的とメリット {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations]および[!UICONTROL Destination Builder]を使用すると、宛先を作成し、セグメント化されたユーザーに関する情報をデータパートナーに送信できます。これは以下に役立ちます。

* **データ値の保護：**&#x200B;すべてのユーザーデータを宛先に送信するのではなく、[!UICONTROL Destination Builder] を使用して対象ユーザーのみに関する特定の情報を共有できます。
* **データに対するアクション：**&#x200B;宛先パートナーへのデータの送信により、対象オーディエンスセグメントをすばやく作成およびターゲット設定できます。
* **技術的なオーバーヘッドの削減：**&#x200B;ビジネスユーザーは、[!UICONTROL Destination Builder] インターフェイスで宛先を安全にセットアップできます。これにより、デプロイメント前のテストに必要な時間を節約できます。[!UICONTROL Destination Builder] を使用すると、長い開発サイクルを経ずに、ビジネスニーズの変更に合わせて宛先を作成、管理および削除できます。

## 技術上の考慮事項 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

データ配信は、データパートナーによる宛先情報の受信方法によって異なります。技術上またはエンジニアリング上の制約によって、宛先が [!DNL URL]、Cookie、サーバー間の処理を通じてデータを受信できない場合があります。サードパーティパートナーと協力して、使用できる方法を決定します。

## ビジネス上の考慮事項 {#business-considerations}

配信方法を複数のものから 1 つ選択するためのビジネス上の決定は、宛先となるパートナーの技術的能力と絞り込まれたユーザーに関する情報の用途によって異なります。例えば、宛先が特定の配信方法でデータを受信できない場合は、技術的な制約で選択肢が制限されるおそれがあります。ただし、技術的な問題がなければ、データにどう対処するかに応じて情報を送信できます。次に例を示します。

* [!DNL URL] の宛先と Cookie ベースの宛先は、ページでのユーザーアクションとほぼ同期的に連動します。
* サーバー間手法は、時間をかけて深みのあるオーディエンスセグメントを構築するのに適しています。

## 宛先のタイプと典型的なユーザー {#destination-types}

次の表に示す例は、特定の宛先の使用に適した状況とそれぞれのタイプの違いを理解するのに役に立ちます。

| 宛先のタイプ | 使用に適した状況 | 例 | 注意点 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 他のAdobe Experience cloudソリューションにデータを送信する必要があります。 | Adobe Analyticsへのデータの送信を参照してください。 |  |
| **[!UICONTROL People-Based Destinations]** | Facebookなどの人ベースの環境にオーディエンスセグメントを送信する必要があります。 | 購入履歴に基づいて、既存の顧客に対してパーソナライズされたオファーを提供 | オーディエンスのターゲット設定は、ハッシュ化された識別子を使用して行われます。 「人ベ [ースの宛先」を参照](people-based-destinations-overview.md) |
| **[!UICONTROL Device-Based Destinations]**(**&#x200B;サーバー間&#x200B;**) | <ul><li>すぐにデータを転送する必要がない場合。</li><li>絞り込まれたユーザーで構成される大規模なオーディエンスプールを構築するためのデータを収集している場合。</li></ul> | 後日実施する予定のキャンペーンで使用するデータを徐々に（数時間または数日間で）収集する。 | <ul><li>新規および以前のサイト訪問者に関するデータを転送します。 </li><li>訪問者を再度確認して、他のセグメントに絞り込む必要はありません。</li></ul> |
| **[!UICONTROL Custom Destinations]**(** URL **または** Cookie **) | 絞り込まれたユーザーに宛先が直ちに対応できるように、データをすぐに転送する必要がある場合。 | チケット購入サイトからのデータの送信。URL または Cookie の宛先を使用してユーザーを絞り込み、直ちにリターゲティングする。 | <ul><li>新規訪問者に関するデータのみ転送します。 </li><li>訪問者を再度確認して、セグメントに絞り込む必要があります。</li></ul> |

