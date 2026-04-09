---
description: Audience Manager で使用可能なアルゴリズムモデルを説明します。
keywords: algo models how works predictive audiences
seo-description: Describes the algorithmic models available in Audience Manager.
seo-title: Algorithmic Models Overview
solution: Audience Manager
title: アルゴリズムモデルの概要
feature: Algorithmic Models
exl-id: ee5c3392-2756-45c5-b325-41a51d3c494f
TQID: https://experienceleague.adobe.com/7p5atoiqA98Uy9TABSlTcWGu1hqFyQ-LwslePnsvoNo
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eb30f47f-d87a-400f-8f78-63ce7979ff56id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 96%

---

# アルゴリズムモデルの概要

## アルゴリズムモデリングとは{#what-algo-modeling}

Audience Manager のアルゴリズムモデリングとは、既存のオーディエンスを拡張したりペルソナに分類したりするためのデータサイエンスの使用のことです。

これは、[!UICONTROL Look-Alike Modeling] と [!UICONTROL Predictive Audiences] の 2 種類のアルゴリズムを使用しておこなわれます。

## 類似モデリング{#lam}

[!UICONTROL Look-Alike Modeling] を使用すると、自動データ分析により、新しい一意のオーディエンスを発見できます。このプロセスは、特性またはセグメント、時間間隔、ファーストパーティおよびサードパーティデータソースを選択した時点で開始します。この選択が、アルゴリズムモデルの入力となります。分析処理が実行されると、選択した母集団と共有する特徴に基づいて、該当するユーザーを検索します。

完了すると、このデータは[特性ビルダー](../../features/traits/about-trait-builder.md)で使用可能になります。ここでは、このデータを使用して[精度とリーチ](../../features/traits/trait-accuracy-reach.md)に基づいて特性を作成できます。さらに、アルゴリズム特性とルールベースの特性を結合するセグメントを作成し、ブール式や比較演算子を使用して他の選定要件を追加することができます。

[!UICONTROL Look-Alike Modeling] を使用すると、使用可能なすべての特性データから価値を動的に抽出できます。

[!UICONTROL Look-Alike Modeling] について詳しくは、[類似（look-alike）モデリングについて](understanding-models.md)を参照してください。

## 予測オーディエンス{#predictive-audiences}

[!UICONTROL Predictive Audiences] は、高度なデータサイエンス技法を使用して、リアルタイムに不明なオーディエンスを個別のペルソナに分類するのに役立ちます。

マーケティングにおいて、ペルソナとは、人口統計、閲覧傾向、買い物履歴など、特定の特性のセットを共有する、訪問者、ユーザーまたは見込み客別に定義されたオーディエンスセグメントです。

[!UICONTROL Predictive Audiences] モデルは、この概念をさらに一歩進めて、Audience Manager の機械学習機能を使用して不明なオーディエンスを個別のペルソナに自動的に分類できるようにします。Audience Manager は、既知のオーディエンスのセットに関する不明なオーディエンスの傾向を計算することで、これを実現します。

[!UICONTROL Predictive Audiences] について詳しくは、[予測オーディエンスの概要](predictive-audiences.md)を参照してください。
