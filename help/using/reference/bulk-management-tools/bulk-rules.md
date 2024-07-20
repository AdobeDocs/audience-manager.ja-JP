---
description: ワークシートの作成および更新において traitRule ヘッダーを使用することができます。これにより、複数のルールを 1 回の操作で適用できるようになります。一括ルールのリクエストをおこなうには、以下の手順に従ってください。
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: 特性ルールおよびセグメントルールの作成または更新
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 92%

---

# 特性ルールおよびセグメントルールの作成または更新{#create-or-update-trait-rules-and-segment-rules}

ワークシートの作成および更新において traitRule ヘッダーを使用することができます。これにより、複数のルールを 1 回の操作で適用できるようになります。一括ルールのリクエストをおこなうには、以下の手順に従ってください。

>[!IMPORTANT]
>
>Bulk Management Tools は、公式にサポートされているAdobeではありません。 カスタマーケアを通じたトラブルシューティングとサポートは、ケースバイケースで対応します。

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[!DNL Audience Manager] UI で割り当てられる [RBAC グループ権限](../../features/administration/administration-overview.md)は、[!UICONTROL Bulk Management Tools] に対しても適用されます。

## 特性ルールの使用 {#trait-rules}

ワークシートの特性ルール列は、ブール式、比較演算子、正規表現で構成されるルールを受け付け、また返します。[!DNL Audience Manager] のビルダーで特性またはセグメントを使用したルールを作成し、それらをワークシートにコピーできます。または、構文についての知識をお持ちの場合、直接ワークシートに式を記述できます。

## ルールビルダーの例 {#rule-builder-example}

[!UICONTROL Segment Builder]を使用してルールを作成し、一括ワークシートにコピーする方法の例を見てみましょう。ただし、ここではこれらのツールの一連の操作手順については触れず、単純なルールが既に作成済みであることを前提とします。ルールビルダーの使用方法については、[セグメントビルダー](../../features/segments/segment-builder.md)および[特性ビルダー](../../features/traits/about-trait-builder.md)を参照してください。

ルールビルダーのビジュアルな画面を使用して、3 つの特性および Boolean 演算子 [!UICONTROL AND] で構成されるセグメントが既に作成されています。

![](assets/visualrule.png)

「**[!UICONTROL Code View]**」をクリックし、このルールのテキスト版を取得します。

>[!TIP]
>
>ルールロジックを確認するには、「**[!UICONTROL Validate Expression]**」をクリックします。これは、無効なルールをアップロードすることを防ぐのに役立ちます。

![](assets/coderule.png)

[!UICONTROL Bulk Management Tools]のワークシートにルールをペーストし、変更をコミットしてセグメントルールを一括更新します。

![](assets/segmentrule.png)

## 独自ルールの作成 {#create-rules}

[!UICONTROL Rule Builder]外で独自ルールを記述できます。作業を開始する前に必ず、演算子、式および必須変数などについて説明されているドキュメントをお読みください。以下の項目を確認することをお勧めします。

* [特性ビルダーでの比較演算子の使用](../../features/traits/trait-comparison-operators.md)
* [演算の順序](../../features/traits/trait-operator-precedence.md)
* [キー変数のプレフィックスに関する要件](../../features/traits/trait-variable-prefixes.md)
* [ブール演算子と比較演算子を使用した式のサンプル](../../features/traits/trait-expression-samples.md)
