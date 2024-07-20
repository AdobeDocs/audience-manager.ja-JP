---
description: 論理演算子を使用して、キー値ペアのグループ化および特性のバックフィルをおこないます。
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: サポートされる論理演算子
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 92%

---

# サポートされる論理演算子 {#supported-logical-operators}

論理演算子を使用して、キー値ペアのグループ化および特性のバックフィルをおこないます。

## シグナル検索でサポートされる演算子 {#supported-operators-search}

キー値ペアの検索では、以下の論理演算子がサポートされます。

### 比較演算子

| 演算子 | 定義 |
|---|---|
| **==** | 次と等しい |
| **>** | 次の値より大きい |
| **&lt;** | 次の値より小さい |
| **=>** | 次の値以上 |
| **&lt;=** | 次の値以下 |

### 名前付き演算子

| 演算子 | [!DNL True] の評価の条件 |
|---|---|
| **[!UICONTROL Contains]** | キー値ペアの値が、この演算子で指定された文字を&#x200B;*含む*。 |
| **[!UICONTROL Startswith]** | キー値ペアの値が、この演算子で指定された文字&#x200B;*で始まる*。 |
| **[!UICONTROL Endswith]** | キー値ペアの値が、この演算子で指定された文字&#x200B;*で終わる*。 |

## 特性のバックフィルおよび推定でサポートされる演算子 {#supported-operators-backfilling}

[!UICONTROL Signal Search]でサポートされている演算子を使用した式を含む特性をバックフィルできます。特性のバックフィルおよび推定では、これらの演算子に加えて [!UICONTROL OR]、[!UICONTROL AND]、および [!UICONTROL AND NOT] 論理演算子もサポートされており、バックフィル対象の特性の式でキー値ペアと組み合わせることができます。
