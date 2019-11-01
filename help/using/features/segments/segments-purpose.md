---
description: セグメント、セグメントの構成要素、セグメントビルダーを使用したルール作成について説明します。
seo-description: セグメント、セグメントの構成要素、セグメントビルダーを使用したルール作成について説明します。
seo-title: セグメントの目的、構成およびルール
solution: Audience Manager
title: セグメントの目的、構成およびルール
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# セグメント：目的、構成、ルール {#segments-purpose-composition-and-rules}

セグメント、セグメントの構成要素、[!UICONTROL Segment Builder]を使用したルール作成について説明します。

## セグメントの目的

*`segment`*（または *`audience`*）は、共通の属性を共有する一連のユーザーです。Audience Manager では、サーバー側ルールを使用してセグメントを作成します。これらのルールを使用すると、次のようなサイト訪問者属性に基づいて、オーディエンスグループを作成できます。

* 動作、
* 人口統計（年齢、性別、収入など）、
* ユーザーインターフェイスで定義できるその他の特徴

## セグメントの構成

Audience Manager セグメントは、個々の特性または特性のグループで構成されるサーバー側ルールです。特性は、キー値ペアと呼ばれるデータ要素で構成されます。これらのキー値ペアには、セグメントレベルで設定したルールと共に、訪問者を特性およびセグメントのメンバーシップの対象に認定するための条件が含まれています。

## Adobe Analytics のセグメントマッピングに関する考慮事項

Adobe Analytics セグメントまたはレポートスイートをExperience Cloud 組織にマッピングする場合、Audience Manager は、対応する新しい、読み取り専用のセグメントおよび特性を自動的に作成します。Audience Manager からこれらのセグメントの保管場所を編集または変更することはできません。ただし、マッピングされた Adobe Analytics セグメントまたはレポートスイートに対する変更は、Audience Manager に反映されます。

>[!TIP]
>
>Audience Manager セグメントは [!DNL Adobe Analytics] セグメントとは異なります。両者の違いについて詳しくは、[Analytics と Audience Manager について](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html)を参照してください。

## セグメントビルダーを使用したルールベースセグメントの作成

シンプルな yes/no 条件の応答で実行される従来のピクセルとは異なり、セグメントビルダーを使用すると、複雑なセグメント要件を作成できます。特性と同様に、セグメントは、[!DNL Boolean] 式（[!DNL AND]、[!DNL OR]、[!DNL NOT]）、比較演算子（greater than、less than、equal to など）および最新性／頻度の条件を使用して、データを評価します。これらの機能は、ビジネスニーズに関係のある焦点を絞ったオーディエンスセグメントを作成するのに役立ちます。

## メリット

セグメントは、以下の理由により、標準的なピクセルベースのオーディエンス作成／セグメント化プロセスを改善します。

* ファーストパーティおよびサードパーティの特性を使用して、関連性の高い有用なセグメントを作成できる。
* ブール演算子、比較式および最新性／頻度の条件を使用して、高度で複雑なセグメント化ルールを作成できる。
* セグメントデータを宛先パートナーに送信できる。
* Audience Manager レポートでパフォーマンスを監視できる。

>[!MORELIKETHIS]
>
>* [シグナル、特性、セグメント](../../reference/signal-trait-segment.md)

