---
description: セグメント、セグメントの構成要素、セグメントビルダーを使用したルール作成について説明します。
seo-description: セグメント、セグメントの構成要素、セグメントビルダーを使用したルール作成について説明します。
seo-title: セグメントの目的、構成およびルール
solution: Audience Manager
title: セグメントの目的、構成およびルール
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 42%

---


# セグメント：目的、構成、ルール {#segments-purpose-composition-and-rules}

Describes [!UICONTROL segments], their constituent parts, and rule creation with [!UICONTROL Segment Builder].

## [!UICONTROL Segments] の用途

*`segment`*（または *`audience`*）は、共通の属性を共有する一連のユーザーです。In Audience Manager, you create [!UICONTROL segments] with server-side rules. これらのルールを使用すると、次のようなサイト訪問者属性に基づいて、オーディエンスグループを作成できます。

* 動作、
* 人口統計（年齢、性別、収入など）、
* ユーザーインターフェイスで定義できるその他の特徴

## [!UICONTROL Segment] 構成

An Audience Manager [!UICONTROL segment] is a server-side rule that consists of individual or groups of traits. 特性は、キーと値のペアと呼ばれるデータ要素で構成されます。Along with rules you set at the [!UICONTROL segment] level, these key-value pairs contain the criteria that qualify visitors for trait and [!UICONTROL segment] membership.

## マッ [!UICONTROL Adobe Analytics][!UICONTROL Segment] ピングに関する考慮事項

When mapping Adobe Analytics [!UICONTROL segments] or report suites to your Experience Cloud organization, Audience Manager automatically creates new, corresponding, read-only [!UICONTROL segments] and traits. You cannot edit or change the storage location of these [!UICONTROL segments] from Audience Manager. However, any change that you perform on your mapped Adobe Analytics [!UICONTROL segments] or report suites reflects in Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] はとは異なり [!DNL Adobe Analytics][!UICONTROL segments]ます。 両者の違いについて詳しくは、[Analytics と Audience Manager について](https://docs.adobe.com/content/help/ja-JP/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)を参照してください。

## ルールベースの作成 [!UICONTROL Segments] に使用 [!UICONTROL Segment Builder]

Unlike traditional pixels that fire in response to simple yes/no conditions, [!UICONTROL Segment Builder] lets you create complex [!UICONTROL segment] requirements. Like [!UICONTROL traits], [!UICONTROL segments] evaluate data using [!DNL Boolean] expressions ([!DNL AND], [!DNL OR], [!DNL NOT]), comparison operators (greater than, less than, equal to, etc.), and recency/frequency criteria. These features help create focused audience [!UICONTROL segments] relevant to your business needs.

## メリット

[!UICONTROL Segments] ピクセルベースの標準的なオーディエンス作成/セグメント化プロセスの改善点：

* Build relevant, useful [!UICONTROL segments] with first and third-party traits.
* ブール演算子、比較式および最新性／頻度の条件を使用して、高度で複雑なセグメント化ルールを作成できる。
* Send [!UICONTROL segment] data to a destination partner.
* Audience Manager レポートでパフォーマンスを監視する。

>[!MORELIKETHIS]
>
>* [シグナル、特性、セグメント](../../reference/signal-trait-segment.md)

