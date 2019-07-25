---
description: ワークシートの作成および更新において traitRule ヘッダーを使用することができます。これにより、複数のルールを 1 回の操作で適用できるようになります。一括ルールの要求をおこなうには、以下の手順に従ってください。
seo-description: ワークシートの作成および更新において traitRule ヘッダーを使用することができます。これにより、複数のルールを 1 回の操作で適用できるようになります。一括ルールの要求をおこなうには、以下の手順に従ってください。
seo-title: 特性ルールおよびセグメントルールの作成または更新
solution: Audience Manager
title: 特性ルールおよびセグメントルールの作成または更新
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 特性ルールおよびセグメントルールの作成または更新{#create-or-update-trait-rules-and-segment-rules}

ワークシートの作成および更新において traitRule ヘッダーを使用することができます。これにより、複数のルールを 1 回の操作で適用できるようになります。一括ルールの要求をおこなうには、以下の手順に従ってください。

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. このツールはあくまで情報提供および便宜を目的として提供されています。一括変更については、代わりに [Audience Manager API](../../api/rest-api-main/aam-api-getting-started.md) を使用することを推奨します。[UIで割り当てられたRBACグループ権限](../../features/administration/administration-overview.md)[!DNL Audience Manager] は、で使用さ [!UICONTROL Bulk Management Tools]れます。

## 特性ルールの使用 {#trait-rules}

ワークシートの特性ルール列は、ブール式、比較演算子、正規表現で構成されるルールを受け付け、また返します。[!DNL Audience Manager] のビルダーで特性またはセグメントを使用したルールを作成し、それらをワークシートにコピーできます。または、構文についての知識をお持ちの場合、直接ワークシートに式を記述できます。

## ルールビルダーの例 {#rule-builder-example}

Let's take a look at an example that demonstrates how to use [!UICONTROL Segment Builder] to create a rule you can to the bulk worksheet. ただし、ここではこれらのツールの一連の操作手順については触れず、単純なルールが既に作成済みであることを前提とします。ルールビルダーの使用方法については、[セグメントビルダー](../../features/segments/segment-builder.md)および[特性ビルダー](../../features/traits/about-trait-builder.md)を参照してください。

ルールビルダーのビジュアルな画面を使用して、3 つの特性および Boolean 演算子 [!UICONTROL AND] で構成されるセグメントが既に作成されています。

![](assets/visualrule.png)

「**[!UICONTROL Code View]**」をクリックし、このルールのテキスト版を取得します。

>[!TIP]
>
>Click **[!UICONTROL Validate Expression]** to check your rule logic. これは、無効なルールをアップロードすることを防ぐのに役立ちます。

![](assets/coderule.png)

Paste the rule into the [!UICONTROL Bulk Management Tools] worksheet and commit your changes to update segment rules in bulk.

![](assets/segmentrule.png)

## 独自ルールの作成 {#create-rules}

You can write your own rules outside of [!UICONTROL Rule Builder]. 作業を開始する前に必ず、演算子、式および必須変数などについて説明されているドキュメントをお読みください。以下の項目を確認することをお勧めします。

* [特性ビルダーでの比較演算子の使用](../../features/traits/trait-comparison-operators.md)
* [演算の順序](../../features/traits/trait-operator-precedence.md)
* [キー変数のプレフィックスに関する要件](../../features/traits/trait-variable-prefixes.md)
* [ブール値および比較演算子を使用した式の例](../../features/traits/trait-expression-samples.md)

