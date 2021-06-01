---
description: Audience Manager で使用可能なアルゴリズムモデルを説明します。
keywords: アルゴモデルは、予測オーディエンスを機能させる方法をモデルします。
seo-description: Audience Manager で使用可能なアルゴリズムモデルを説明します。
seo-title: アルゴリズムモデルの概要
solution: Audience Manager
title: アルゴリズムモデルの概要
feature: アルゴリズムモデル
exl-id: ee5c3392-2756-45c5-b325-41a51d3c494f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 97%

---

# アルゴリズムモデルの概要

## アルゴリズムモデリングとは {#what-algo-modeling}

Audience Manager のアルゴリズムモデリングとは、既存のオーディエンスを拡張したりペルソナに分類したりするためのデータサイエンスの使用のことです。

これは、[!UICONTROL Look-Alike Modeling] と [!UICONTROL Predictive Audiences] の 2 種類のアルゴリズムを使用しておこなわれます。

## 類似モデリング {#lam}

[!UICONTROL Look-Alike Modeling] を使用すると、自動データ分析により、新しい一意のオーディエンスを発見できます。このプロセスは、特性またはセグメント、時間間隔、ファーストパーティおよびサードパーティデータソースを選択した時点で開始します。この選択が、アルゴリズムモデルの入力となります。分析処理が実行されると、選択した母集団と共有する特徴に基づいて、該当するユーザーを検索します。

完了すると、このデータは[特性ビルダー](../../features/traits/about-trait-builder.md)で使用可能になります。ここでは、このデータを使用して[精度とリーチ](../../features/traits/trait-accuracy-reach.md)に基づいて特性を作成できます。さらに、アルゴリズム特性とルールベースの特性を結合するセグメントを作成し、ブール式や比較演算子を使用して他の認定要件を追加することができます。

[!UICONTROL Look-Alike Modeling] を使用すると、使用可能なすべての特性データから価値を動的に抽出できます。

[!UICONTROL Look-Alike Modeling] について詳しくは、[類似（look-alike）モデリングについて](understanding-models.md)を参照してください。

## Predictive Audiences {#predictive-audiences}

[!UICONTROL Predictive Audiences] は、高度なデータサイエンス技法を使用して、リアルタイムに不明なオーディエンスを個別のペルソナに分類するのに役立ちます。

マーケティングにおいて、ペルソナとは、人口統計、閲覧傾向、買い物履歴など、特定の特性のセットを共有する、訪問者、ユーザーまたは見込み客別に定義されたオーディエンスセグメントです。

[!UICONTROL Predictive Audiences] モデルは、この概念をさらに一歩進めて、Audience Manager の機械学習機能を使用して不明なオーディエンスを個別のペルソナに自動的に分類できるようにします。Audience Manager は、既知のオーディエンスのセットに関する不明なオーディエンスの傾向を計算することで、これを実現します。

[!UICONTROL Predictive Audiences] について詳しくは、[Predictive Audiences の概要](predictive-audiences.md)を参照してください。
