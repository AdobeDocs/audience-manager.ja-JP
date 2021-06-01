---
description: ここでは、特性ビルダーで使用される比較演算子について説明します。
seo-description: ここでは、特性ビルダーで使用される比較演算子について説明します。
seo-title: 特性ビルダーでの比較演算子の使用
solution: Audience Manager
title: 特性ビルダーでの比較演算子の使用
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: 特性
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 100%

---

# 特性ビルダーでの比較演算子の使用 {#working-with-comparison-operators-in-trait-builder}

ここでは、[!UICONTROL Trait Builder] で使用される比較演算子について説明します。

## 比較演算子の目的

<!-- c_tb_comparison_operators.xml -->

比較演算子（または関係演算子）は、異なる値の間の関係を比較、テストまたは評価するために使用されます。[!UICONTROL Trait Builder]では、シグナルルールを作成する際に、比較演算子を使用すると、異なるキーと値のペア間の関係をテストできます。例えば、シグナルルールを作成して、高級カメラ購買者のオーディエンスを定義できます。この場合、カメラ／価格のキーと値のペアを作成して、設定した額以上の価格のカメラを探しているかどうかでユーザーを評価できます。

## 比較演算子のメリット

比較演算子は、複数の値に基づいて特性を評価および作成する必要がある場合に役に立ちます。商品やサービスの価格を例に取ると、この条件を説明できます。例えば、ビジネスで、見ている商品の価格に基づいて訪問者を識別する必要があるとします。ただし、特定の値に基づいて個別のセグメントを定義するのは、管理上、非効率である可能性があります。比較演算子は、価格のしきい値または範囲に基づいてセグメント化をトリガーすることで、この困難を克服できます。

## 比較演算子

以下の比較演算子を使用してルールを作成できます。

| 演算子 | 定義 |
|---|---|
| **==** | 次と等しい |
| **!=** | 次と等しくない |
| **>** | 次の値より大きい |
| **&lt;>** | 次の値より小さい |
| **=>** | 次の値以上 |
| **&lt;>** | 次の値以下 |

## 名前付き演算子

以下の名前付き演算子を使用してルールを作成できます。

| 演算子 | [!DNL True] の評価の条件 |
|---|---|
| **[!UICONTROL Contains]** | キー値ペアの値が、この演算子で指定された文字を&#x200B;*含む*。 |
| **[!UICONTROL Matcheswords]** | キー値ペアの値が、この演算子で指定されたパターンに&#x200B;*合致する*。 |
| **[!UICONTROL Startswith]** | キー値ペアの値が、この演算子で指定された文字&#x200B;*で始まる*。 |
| **[!UICONTROL Endswith]** | キー値ペアの値が、この演算子で指定された文字&#x200B;*で終わる*。 |
| **[!UICONTROL Matchesregex]** | キー値ペアの値が、正規表現で指定されたパターンに&#x200B;*合致する*。[こちら](../../features/traits/trait-builder-regex.md)を参照して、[!UICONTROL Trait Builder]での正規表現の使用について確認してください。 |

>[!MORELIKETHIS]
>
>* [特性およびセグメントビルダーのブール式](../../reference/boolean-expressions-tsb.md)
* [特性ビルダーのブール式について](../../reference/boolean-expressions-tsb.md)
* [特性ビルダーでの演算順序](../../features/traits/trait-operator-precedence.md)
* [ブール演算子と比較演算子を使用した式のサンプル](../../features/traits/trait-expression-samples.md)

