---
description: Audience Manager において、宛先とは、データを共有する任意のサードパーティシステム（広告サーバー、DSP、広告ネットワークなど）になります。Cookie、URLまたはサーバー間の宛先を作成および管理するには、宛先ビルダーツールを使用します。
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: Audience Manager において、宛先とは、データを共有する任意のサードパーティシステム（広告サーバー、DSP、広告ネットワークなど）になります。宛先ビルダーは、Cookie、URLまたはサーバー間の宛先を作成および管理するためのツールです。
seo-title: 宛先
solution: Audience Manager
title: 宛先
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 8027f278aa2b879b6cb277f44caf4b62dc75e2c3
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 50%

---


# [!UICONTROL Destinations] 概要 {#destinations}

In Audience Manager, a [!UICONTROL destination] is any third-party system (ad server, [!DNL DSP], ad network, etc.) になります。[!UICONTROL Destination Builder] は、を作成および管理するためのツール [!UICONTROL cookie]、 [!DNL URL]または [!UICONTROL server-to-server destinations]。

## 目的とメリット {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] セグメント化 [!UICONTROL Destination Builder] されたユーザーに関する情報を作成し [!UICONTROL destinations] て、データパートナーに送信できます。 これは以下に役立ちます。

* **Protectデータ値：** すべてのユーザーデータをに送信する代わりに [!UICONTROL destination]、資格を持つユーザーに関する特定の情報のみを共有 [!UICONTROL Destination Builder] できます。
* **データに対して次のアクションを実行します。** パートナーにデータを送信すると、資格を満たすオーディエンスセグメントをすばやく開発し、ターゲットするのに役立ちます。 [!UICONTROL destination]
* **技術的なオーバーヘッドの削減：** ビジネスユーザーは、インター [!UICONTROL destinations][!UICONTROL Destination Builder] フェイス内で安全にセットアップできます。 これにより、デプロイメント前のテストに必要な時間を節約できます。With [!UICONTROL Destination Builder], you create, manage, and delete [!UICONTROL destinations] as your business needs change, all without working through a long development cycle.

## 技術上の考慮事項 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

Data delivery depends on how your data partner wants to, or can, receive [!UICONTROL destination] information. Technical or engineering constraints may prevent a [!UICONTROL destination] from receiving data via [!DNL URL], [!UICONTROL cookie], or [!UICONTROL server-to-server] processes. サードパーティパートナーと協力して、使用できる方法を決定します。

## ビジネス上の考慮事項 {#business-considerations}

Business decisions for selecting one delivery method over another depend on the technical capabilities of your [!UICONTROL destination] partner and what you want to do with qualified user information. For example, technical constraints can limit your options if a [!UICONTROL destination] cannot receive data by a particular delivery method. ただし、技術的な問題がなければ、データにどう対処するかに応じて情報を送信できます。次に例を示します。

* [!DNL URL]とは、ページ上のユーザーアクションとほぼ同期して [!UICONTROL cookie-based destinations] 機能します。
* [!UICONTROL Server-to-server] メソッドは、時間の経過と共に深いオーディエンスセグメントを作成する場合に便利です。

## [!UICONTROL Destination] タイプと一般的な使用方法 {#destination-types}

The examples in the following table can help you understand when to use a particular [!UICONTROL destination] and the differences between each type.

| [!UICONTROL Destination]&quot; | 使用に適した状況 | 例 | 注意点 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 他の Adobe Experience Cloud ソリューションにデータを送信する必要があります。 | Adobe Analytics にデータを送信します。 |  |
| **[!UICONTROL People-Based Destinations]** | Facebook のように、ユーザーベースの環境にオーディエンスセグメントを送信する必要があります。 | 購入履歴に基づき、既存の顧客に対してパーソナライズされたオファーを提供する | オーディエンスのターゲティングは、ハッシュ化された識別子を使用しておこなわれます。詳しくは、[ユーザーベースの宛先](people-based-destinations-overview.md)を参照してください。 |
| **[!UICONTROL Device-Based Destinations]** (**サーバー間**) | <ul><li>すぐにデータを転送する必要がない場合。</li><li>絞り込まれたユーザーで構成される大規模なオーディエンスプールを構築するためのデータを収集している場合。</li></ul> | 後日実施する予定のキャンペーンで使用するデータを徐々に（数時間または数日間で）収集する。 | <ul><li>新規および以前のサイト訪問者に関するデータを転送します。 </li><li>訪問者を再度確認して、他のセグメントに絞り込む必要はありません。</li></ul> |
| **[!UICONTROL Custom Destinations]**（**URL** または **Cookie**） | 絞り込まれたユーザーに宛先が直ちに対応できるように、データをすぐに転送する必要がある場合。 | チケット購入サイトからのデータの送信。Use a [!UICONTROL URL] or [!UICONTROL cookie destination] to qualify user and immediately re-target. | <ul><li>新規訪問者に関するデータのみ転送します。 </li><li>訪問者を再度確認して、セグメントに絞り込む必要があります。</li></ul> |
