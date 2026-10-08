---
description: 論理演算子を使用して、キー値ペアのグループ化および特性のバックフィルをおこないます。
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: サポートされる論理演算子
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
TQID: 'https://experienceleague.adobe.com/m9daAh4HRSx5zwBX-ByQU0dLVy-KOt3RMrdjGvFqsMU'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
    internal-label: Audience Marketplace
subfeature_v2:
  - id: a2c6d65b-635d-4454-a9cc-9771ed501bb4
    internal-label: Data Explorer
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 92%
---
# サポートされる論理演算子 {#supported-logical-operators}

論理演算子を使用して、キー値ペアのグループ化および特性のバックフィルをおこないます。

## 信号検索でサポートされる演算子 {#supported-operators-search}

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

## 特性のバックフィルと推定でサポートされる演算子 {#supported-operators-backfilling}

[!UICONTROL Signal Search]でサポートされている演算子を使用した式を含む特性をバックフィルできます。 特性のバックフィルおよび推定では、これらの演算子に加えて [!UICONTROL OR]、[!UICONTROL AND]、および [!UICONTROL AND NOT] 論理演算子もサポートされており、バックフィル対象の特性の式でキー値ペアと組み合わせることができます。
