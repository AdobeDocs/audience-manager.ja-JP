---
description: アルゴリズムマネージャーで使用できるオーディエンスモデルを示します。
keywords: algo models how works predictive audiences
seo-description: アルゴリズムマネージャーで使用できるオーディエンスモデルを示します。
seo-title: アルゴリズムモデルの概要
solution: Audience Manager
title: アルゴリズムモデルの概要
translation-type: tm+mt
source-git-commit: 82e649c93664b32d62123112802fed66bbf24ae4

---


# アルゴリズムモデルの概要

## アルゴリズムによるモデリングとは{#what-algo-modeling}

オーディエンスマネージャのアルゴリズムによるモデリングとは、データ科学を使用して、既存のオーディエンスを拡張するか、個人に分類することです。

これは、次の2種類のアルゴリズムを使用して行われます。 [!UICONTROL Look-Alike Modeling] と [!UICONTROL Predictive Audiences]

## 類似モデリング{#lam}

[!UICONTROL Look-Alike Modeling] 自動化されたデータの分析により、新しい固有のオーディエンスを見つけるのに役立ちます。 このプロセスは、特性またはセグメント、時間間隔、ファーストパーティおよびサードパーティデータソースを選択した時点で開始します。この選択が、アルゴリズムモデルの入力となります。アナリティクス処理が実行されると、選択した母集団の共有特徴に基づいて、該当するユーザーを検索します。

このデータは、完了時に特性ビルダ [ーで使用でき](../../features/traits/about-trait-builder.md) 、精度とリーチに基づいて特性を作成する [ことができます](../../features/traits/trait-accuracy-reach.md)。 さらに、アルゴリズム特性とルールベースの特性を結合するセグメントを作成し、ブール式や比較演算子を使用して他の認定要件を追加することができます。

[!UICONTROL Look-Alike Modeling] 使用可能なすべての特性データから動的に値を抽出できます。

詳しくは、「類似したモデ [!UICONTROL Look-Alike Modeling]リングにつ [いて」を参照してください](understanding-models.md)。

## 予測オーディエンス{#predictive-audiences}

[!UICONTROL Predictive Audiences] 高度なデータ科学技術を使用して、未知のオーディエンスをリアルタイムで個別の人物に分類するのに役立ちます。

マーケティングコンテキストで、個人とは、訪問者、ユーザー、または潜在的な購入者が定義したオーディエンスセグメントで、人口統計、閲覧習慣、買い物履歴などの特定の特性を共有します。

[!UICONTROL Predictive Audiences] モデルは、オーディエンスマネージャの機械学習機能を使用して、未知のオーディエンスを別の個人に自動的に分類することで、この概念をさらに一歩進めます。 オーディエンスマネージャーは、既知のオーディエンスのセットに対する未知の傾向を計算することで、これを達成します。

詳しくは、予測 [!UICONTROL Predictive Audiences]オーディエンスの概 [要を参照](predictive-audiences.md)。
