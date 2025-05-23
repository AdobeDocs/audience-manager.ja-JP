---
description: この記事では、一般的なカテゴリへの特性の分類についての全般的な概要について説明します。
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: 一般的なカテゴリへの特性の分類
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 100%

---

# 一般的なカテゴリへの特性の分類 {#classifying-traits-with-a-common-taxonomy}

この記事では、一般的なカテゴリへの特性の分類についての全般的な概要について説明します。

## Audience Manager の分類

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager] の分類は、論理的かつ統一された、一般的に理解可能な命名規則を使用して特性を分類するオプション機能です。この機能は、[!DNL Audience Manager] のエコシステム全体で名前の一貫性を保つために、プラットフォームレベルで動作します。最終的な目標は、一般的なカテゴリを使用することで、アドビ製品を消費者のプライバシーやオプトアウト処理に関する業界標準によりよく準拠させることです。

## 特性の分類の利点

お客様が独自のセグメントおよびデータモデルを作成できることは、[!DNL Audience Manager] のモデルにおいても、アドビのプラットフォームを最大限に活用するうえでも欠かせない要素です。しかし、これに加えて顧客およびパートナーとの間でセグメントに関する情報を堅牢かつスケーラブルな手段でやり取りできることも必須です。さらに、このやり取りにおいては、御社独自の特性およびセグメントの名前を保護しながら、わかりやすく誰もが理解できる言語でセグメント情報を共有できる必要があります。[!DNL Audience Manager] の一般的なカテゴリは、このような言語および能力を実現します。

## カテゴリには業界標準の分類を使用

この一般的なカテゴリは、[!DNL Interactive Advertising Bureau (IAB)] によって作成された分類に基づいています。ネットワークとエクスチェンジの品質保証ガイドラインについて詳しくは、[!DNL IAB] の [Web サイト](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines)を参照してください。

## 分類の構成

[!DNL Audience Manager] の分類では、データをネストされたカテゴリに編成します。これらは層と呼ばれます。各カテゴリは、データ分類のための個別の層を最大 3 つまで持つことができます。最上位レベルである第 1 層のカテゴリは、データを最も一般的な形式（地域など）でグループ化します。これに続く層では、上位レベルの一般的なカテゴリよりも詳細になります（*地理 --> 米国 --> ニューヨーク*&#x200B;など）。ただし、どのカテゴリも必ず 3 層であるとは限らず、2 層のみのものもあります。

## データカテゴリによる特性の分類

[!UICONTROL Add New Trait Wizard]（* **[!UICONTROL Audience Data > Traits]*** にあります）の特性を作成または編集する際に、分類を割り当てることができます。詳しくは、[特性の作成に関するドキュメント](../../features/traits/create-onboarded-rule-based-traits.md)を参照してください。

## 分類の使用：その他の考慮事項

アドビの一般的なカテゴリで特性の分類をおこなう場合、次のことを念頭に置いてください。

* 分類は&#x200B;*オプション*&#x200B;です。
* デフォルトでは、特性はカテゴリに割り当てられ&#x200B;*ません*（例えば、特性は「不明」または「分類なし」などに分類されません）。
* 特性は *1 つの*&#x200B;カテゴリにのみ分類されます（複数のカテゴリにまたがった分類はできません）。
