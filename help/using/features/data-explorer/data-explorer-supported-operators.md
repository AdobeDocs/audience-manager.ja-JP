---
description: 論理演算子を使用して、キー値ペアのグループ化および特性のバックフィルをおこないます。
seo-description: 論理演算子を使用して、キー値ペアのグループ化および特性のバックフィルをおこないます。
seo-title: サポートされる論理演算子
title: サポートされる論理演算子
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# サポートされる論理演算子 {#supported-logical-operators}

論理演算子を使用して、キー値ペアのグループ化および特性のバックフィルをおこないます。

## シグナル検索{#supported-operators-search}でサポートされる演算子 

キー値ペアの検索では、以下の論理演算子がサポートされます。

### 比較演算子

| 演算子 | 定義 |
|---|---|
| **==** | 次と等しい |
| **&gt;** | 次の値より大きい |
| **&lt;** | 次の値より小さい |
| **=&gt;** | 次の値以上 |
| **&lt;=** | 次の値以下 |

### 名前付き演算子

| 演算子 | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | キー値ペアの値が、この演算子で指定された文字を*含む*。 |
| **[!UICONTROL Startswith]** | キー値ペアの値が、この演算子で指定された文字*で始まる*。 |
| **[!UICONTROL Endswith]** | キー値ペアの値が、この演算子で指定された文字*で終わる*。 |

## 特性のバックフィルおよび推定でサポートされる演算子 {#supported-operators-backfilling}

You can backfill traits that include expressions containing any of the operators supported by [!UICONTROL Signal Search]. In addition to these operators, trait backfilling and estimation also support the [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL AND NOT] logical operators, used to combine key-value pairs within the backfilled trait expressions.