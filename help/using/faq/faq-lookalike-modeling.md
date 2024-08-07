---
description: 類似（look-alike）モデリングを使用すると、自動データ分析により、新しい個別のオーディエンスを発見できます。この記事では、最もよくある質問に対する回答を示します。
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: 類似（look-alike）モデリングに関するよくある質問
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 100%

---

# 類似（look-alike）モデリングに関するよくある質問

## 概要 {#overview}

この記事では、[!UICONTROL Look-Alike Modeling] に関するよくある質問の回答を示します。

## 質問 {#questions}

**なぜフラットな [!UICONTROL Accuracy & Reach] グラフになるのですか？**

フラットな [!UICONTROL Accuracy & Reach] グラフは、ほぼすべてのユーザーがモデルによって同じスコアを得ていることを意味します。この問題は、モデルを実行したデータソースにサイト訪問者の特性を含める場合に発生する可能性があります。これを回避するには、[!UICONTROL Exclusions]フィールドを使用して、モデル作成手順の間、モデル入力から汎用特性を削除します。

 

**なぜ影響力のある一部の特性には、オーディエンスが非常に少ないのですか？**

アルゴリズムは、ベースライン特性と相関の高い特性を選択します。例えば、特定の特性がベースライン特性と 100% 重複している場合、その特性のユーザー数が少なくても、非常に高い重み付けを持ちます。

 

**モデルが実行／再実行されないのはなぜですか？**

結果を生成したモデルは、少なくとも 1 つのアクティブなアルゴリズム特性を作成し、それをアクティブなセグメントと宛先にマップした場合にのみ、引き続き実行されます。

 

**モデルが結果を生成しなかったのはなぜですか？**

これは、通常、ベースライン母集団と選択したデータソース内の母集団の間に、大きな特性が重複していないことが原因です。

 

**ベースライン特性やセグメントサイズについてのレコメンデーションはありますか？**

ベースライン母集団と選択したデータソースの母集団の間に大きな特性の重複がある場合、モデルを実行するには数千のユーザーで十分です。[!UICONTROL Look-Alike Modeling] は、ベースラインが大きいほど正確な結果が得られます。

 

**モデルに対して選択すべきサードパーティのデータソースは何ですか？**

ベースラインの特性やセグメントと少なくとも一部が重複しているデータソースを使用し、同時に追加のユーザーを取り込んでください。各データフィードに関連するコストも考慮する必要があります。コストと価格モデルは、[!UICONTROL Audience Marketplace] のデータプロバイダーによって異なります。

 

**モデリングにサードパーティのデータを使用すると、コストがかかりますか？**

選択したデータフィードの価格モデルによって異なります。フィードによって、モデリングを無料でできる場合と、料金がかかる場合があります。詳しくは、[データフィード購入者への課金](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)を参照してください。

 

**モデルや特性はいくつ作成できますか？**

現在、最大 20 個のアルゴリズムモデルと 50 個のアルゴリズム特性を作成できます。

 

**モデルのトレーニングとアルゴリズム特性の母集団の更新頻度は？**

モデルの再トレーニングと、アルゴリズム特性の母集団の更新は、8 日に 1 回行われます。
