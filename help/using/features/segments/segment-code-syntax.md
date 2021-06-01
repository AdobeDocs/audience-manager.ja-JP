---
description: セグメントビルダーでは、コードエディターを使用して、セグメント用の特性ルールを作成できます。Traits パネルの「Segment Expressions (Code View)」タブをクリックすると、この機能にアクセスできます。
seo-description: セグメントビルダーでは、コードエディターを使用して、セグメント用の特性ルールを作成できます。Traits パネルの「Segment Expressions (Code View)」タブをクリックすると、この機能にアクセスできます。
seo-title: セグメント式エディターで使用するコード構文
solution: Audience Manager
title: セグメント式エディターで使用するコード構文
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: セグメント
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 100%

---

# セグメント式エディターで使用するコード構文 {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] では、コードエディターを使用して、セグメント用の特性ルールを作成できます。**[!UICONTROL Segment Expressions (Code View)]** パネルの[!UICONTROL Traits]タブをクリックすると、この機能にアクセスできます。

## 式ビルダーのコード構文

ドラッグアンドドロップ機能の代わりにコードを使用して特性ルールをセグメントに追加することができます。コードの作成時には、例の斜体の要素を実際の式や値に置き換えます。ベースのコードでは次の構文を使用しています。

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>デフォルトでは、[!DNL Boolean] [!UICONTROL OR] の条件は式の&#x200B;*中*&#x200B;にある複数の特性に適用されます。

### ブール演算子でセグメントを結合

セグメントのグループを作成するには、FREQUENCY 関数を括弧で囲み、各式の&#x200B;*間*&#x200B;の関係を [!DNL Boolean] 演算子（[!UICONTROL OR]、[!UICONTROL AND]、[!UICONTROL NOT]）で設定します。

### パラメーター

>[!NOTE]
>
>特に説明がない限り、すべてのパラメーターが必須です。

| 名前または変数 | 説明 |
|---|---|
| `FREQUENCY` | 式の前に配置する必要がある文字列。 |
| ` [`&lt;`traitID`>`T]` | 特性 ID の末尾に「`T`」を付加した文字列の配列。複数の特性がある場合、コンマで区切ります。例：`[123T, 456T]` |
| ` <Recency Operator><Numeric Value>D` | *（オプション）*&#x200B;セグメントの特性に関する最新性ルールを設定します。「`D`」は最新性を日数単位で表していることを示します。 |
| ` <Frequency Operator><Numeric Value>` | セグメントの特性に関する頻度ルールを設定します。 |

### 使用可能な最新性演算子と頻度演算子

[最新性と頻度](../../features/segments/recency-and-frequency.md)の間隔を、比較演算子と整数で設定します。[!UICONTROL Segment Builder] では、&lt;（次より小さい）、>（次より大きい）、==（次と等しい）などの標準的な式が使用されます。ただし、設定時に使用できる演算子の種類は最新性と頻度で異なります。次の表は、使用可能な最新性演算子と頻度演算子です。

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 最新性演算子 </th> 
   <th colname="col2" class="entry"> 頻度演算子 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;=（次よりも大きいか等しい） </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;=（次よりも小さいか等しい） </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;=（次よりも大きいか等しい） </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;=（次よりも小さいか等しい） </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">==（次と等しい） </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [最新性と頻度](../../features/segments/recency-and-frequency.md)
* [特性およびセグメントビルダーのブール式](../../reference/boolean-expressions-tsb.md)
* [特性ビルダーでの比較演算子の使用](../../features/traits/trait-comparison-operators.md)
* [特性ビルダーでの演算順序](../../features/traits/trait-operator-precedence.md)

