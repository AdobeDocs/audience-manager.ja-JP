---
description: セグメント、セグメントの構成要素、セグメントビルダーを使用したルール作成について説明します。
seo-description: セグメント、セグメントの構成要素、セグメントビルダーを使用したルール作成について説明します。
seo-title: セグメントの目的、構成およびルール
solution: Audience Manager
title: セグメントの目的、構成およびルール
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: セグメント
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 97%

---

# セグメント：目的、構成、ルール {#segments-purpose-composition-and-rules}

[!UICONTROL segments]、セグメントの構成要素、および [!UICONTROL Segment Builder] を使用したルール作成について説明します。

## [!UICONTROL Segments] の用途

*`segment`*（または *`audience`*）は、共通の属性を共有する一連のユーザーです。Audience Manager では、サーバーサイドルールを使用して[!UICONTROL segments]を作成します。これらのルールを使用すると、次のようなサイト訪問者属性に基づいて、オーディエンスグループを作成できます。

* 動作、
* 人口統計（年齢、性別、収入など）、
* ユーザーインターフェイスで定義できるその他の特徴

## [!UICONTROL Segment]構成

Audience Manager [!UICONTROL segment]は、個々の特性または特性のグループで構成されるサーバーサアイドルールです。特性は、キーと値のペアと呼ばれるデータ要素で構成されます。これらのキーと値のペアには、[!UICONTROL segment]レベルで設定したルールと共に、訪問者を特性および[!UICONTROL segment]のメンバーシップの対象に認定するための条件が含まれています。

## [!UICONTROL Adobe Analytics] [!UICONTROL Segment] マッピングに関する考慮事項

Adobe Analytics [!UICONTROL segments]またはレポートスイートをExperience Cloud 組織にマッピングする場合、Audience Manager は、対応する新しい、読み取り専用の[!UICONTROL segments]および特性を自動的に作成します。Audience Manager からこれらの[!UICONTROL segments]の保管場所を編集または変更することはできません。ただし、マッピングされた Adobe Analytics [!UICONTROL segments]またはレポートスイートに対する変更は、Audience Manager に反映されます。

>[!TIP]
>
>Audience Manager [!UICONTROL segments]は、[!DNL Adobe Analytics] [!UICONTROL segments] とは異なります。両者の違いについて詳しくは、[Analytics と Audience Manager について](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)を参照してください。

## [!UICONTROL Segment Builder] でルールベース[!UICONTROL Segments]を作成する

シンプルな yes/no 条件の応答で実行される従来のピクセルとは異なり、[!UICONTROL Segment Builder] を使用すると、複雑な[!UICONTROL segment]要件を作成できます。[!UICONTROL traits] 特性と同様に、[!UICONTROL segments] は、[!DNL Boolean] 式（[!DNL AND]、[!DNL OR]、[!DNL NOT]）、比較演算子（greater than、less than、equal to など）および最新性／頻度の条件を使用して、データを評価します。これらの機能は、ビジネスニーズに関係のある焦点を絞ったオーディエンス[!UICONTROL segments]を作成するのに役立ちます。

## メリット

[!UICONTROL Segments]は、以下の理由により、標準的なピクセルベースのオーディエンス作成／セグメント化プロセスを改善します。

* ファーストパーティおよびサードパーティの特性を使用して、関連性の高い有用な[!UICONTROL segments]を作成できる。
* ブール演算子、比較式および最新性／頻度の条件を使用して、高度で複雑なセグメント化ルールを作成できる。
* [!UICONTROL segment]データを宛先パートナーに送信できる。
* Audience Manager レポートでパフォーマンスを監視する。

>[!MORELIKETHIS]
>
>* [シグナル、特性、セグメント](../../reference/signal-trait-segment.md)

