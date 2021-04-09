---
description: Audience Manager において、宛先とは、データを共有する任意のサードパーティシステム（広告サーバー、DSP、広告ネットワークなど）になります。Destination Builder とは、Cookie、URL、またはサーバー間通信ベースの宛先の作成および管理をおこなうために使用するツールです。
keywords: 統合コード、宛先、宛先の概要, 宛先, 宛先, 宛先, 宛先, 宛先, 宛先, 宛先, 宛先, 宛先, 宛先, 宛先
landing-page-description: 宛先は、広告サーバーや DSP など、データを共有するサードパーティ製のシステムです。 Cookie、URL またはサーバー間の宛先を作成および管理するには、宛先ビルダーツールを使用します。
seo-title: 宛先
solution: Audience Manager
title: リンク先
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: ターゲットの基本
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
translation-type: tm+mt
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!UICONTROL Destinations] 概要 {#destinations}

Audience Manager において、[!UICONTROL destination]とは、データを共有する任意のサードパーティシステム（広告サーバー、[!DNL DSP]、広告ネットワークなど）になります。[!UICONTROL Destination Builder] は、[!UICONTROL cookie]、[!DNL URL]、または[!UICONTROL server-to-server destinations]の作成と管理に使用するツールです。

## 目的とメリット {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations]および[!UICONTROL Destination Builder]を使用すると、[!UICONTROL destinations]宛を作成し、セグメント化されたユーザーに関する情報をデータパートナーに送信できます。これは以下に役立ちます。

* **データ値の保護：**&#x200B;すべてのユーザーデータを[!UICONTROL Destination Builder]に送信するのではなく、[!UICONTROL destination] を使用して対象ユーザーのみに関する特定の情報を共有できます。
* **データに対するアクション：** [!UICONTROL destination]パートナーへのデータの送信により、対象オーディエンスセグメントをすばやく作成およびターゲット設定できます。
* **技術的なオーバーヘッドの削減：**&#x200B;ビジネスユーザーは、[!UICONTROL Destination Builder] インターフェイスで[!UICONTROL destinations]を安全にセットアップできます。これにより、デプロイメント前のテストに必要な時間を節約できます。[!UICONTROL Destination Builder] を使用すると、長い開発サイクルを経ずに、ビジネスニーズの変更に合わせて[!UICONTROL destinations]を作成、管理および削除できます。

## 技術上の考慮事項 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

データ配信は、データパートナーが[!UICONTROL destination]情報をどのように受信したいか、または受信できるかによって異なります。技術上またはエンジニアリング上の制約によって、[!UICONTROL destination] が [!DNL URL]、[!UICONTROL cookie]、または[!UICONTROL server-to-server]のプロセス経由でデータを受信できない場合があります。サードパーティパートナーと協力して、使用できる方法を決定します。

## ビジネス上の考慮事項  {#business-considerations}

配信方法を複数のものから 1 つ選択するためのビジネス上の決定は、[!UICONTROL destination]となるパートナーの技術的能力と絞り込まれたユーザーに関する情報の用途によって異なります。例えば、[!UICONTROL destination]が特定の配信方法でデータを受信できない場合は、技術的な制約で選択肢が制限されるおそれがあります。ただし、技術的な問題がなければ、データにどう対処するかに応じて情報を送信できます。例：

* [!DNL URL] および [!UICONTROL cookie-based destinations]は、ページでのユーザーアクションとほぼ同期的に連動します。
* [!UICONTROL Server-to-server]手法は、時間をかけて深みのあるオーディエンスセグメントを構築するのに適しています。

## [!UICONTROL Destination]のタイプと典型的なユーザー {#destination-types}

次の表に示す例は、特定の[!UICONTROL destination]の使用に適した状況とそれぞれのタイプの違いを理解するのに役に立ちます。

| [!UICONTROL Destination]のタイプ | 使用に適した状況 | 例 | 注意点 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 他の Adobe Experience Cloud ソリューションにデータを送信する必要があります。 | Adobe Analytics にデータを送信します。 |  |
| **[!UICONTROL People-Based Destinations]** | Facebook のように、ユーザーベースの環境にオーディエンスセグメントを送信する必要があります。 | 購入履歴に基づき、既存の顧客に対してパーソナライズされたオファーを提供する | オーディエンスのターゲティングは、ハッシュ化された識別子を使用しておこなわれます。詳しくは、[ユーザーベースの宛先](people-based-destinations-overview.md)を参照してください。 |
| **[!UICONTROL Device-Based Destinations]**（**サーバー間**） | <ul><li>すぐにデータを転送する必要がない場合。</li><li>絞り込まれたユーザーで構成される大規模なオーディエンスプールを構築するためのデータを収集している場合。</li></ul> | 後日実施する予定のキャンペーンで使用するデータを徐々に（数時間または数日間で）収集する。 | <ul><li>新規および以前のサイト訪問者に関するデータを転送します。 </li><li>訪問者を再度確認して、他のセグメントに絞り込む必要はありません。</li></ul> |
| **[!UICONTROL Custom Destinations]**（**URL** または **Cookie**） | 絞り込まれたユーザーに宛先が直ちに対応できるように、データをすぐに転送する必要がある場合。 | チケット購入サイトからのデータの送信。[!UICONTROL URL] または [!UICONTROL cookie destination]を使用してユーザーを絞り込み、直ちにリターゲティングする。 | <ul><li>新規訪問者に関するデータのみ転送します。 </li><li>訪問者を再度確認して、セグメントに絞り込む必要があります。</li></ul> |
