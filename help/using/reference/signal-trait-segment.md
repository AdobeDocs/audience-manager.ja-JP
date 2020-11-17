---
description: Audience Manager セグメントの構成要素、オーディエンスの認定基準の設定に使用される表現、イベント呼び出しでのデータの送信方法について説明します。
seo-description: Audience Manager セグメントの構成要素、オーディエンスの認定基準の設定に使用される表現、イベント呼び出しでのデータの送信方法について説明します。
seo-title: シグナル、特性、セグメント
solution: Audience Manager
title: シグナル、特性、セグメント
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: reference
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 49%

---


# [!UICONTROL Signals], [!UICONTROL Traits], および [!UICONTROL Segments] {#signals-traits-and-segments}

Describes the components of an [!DNL Audience Manager] [!UICONTROL segment], the expressions used to set audience qualification criteria, and how data is transmitted in an event call.

## 構成と目的

[!DNL Audience Manager] データは、 [!UICONTROL signals]、 [!UICONTROL traits]、 [!UICONTROL segments]および関連する資格ルールで構成されます。 The data elements and rules combine to create [!UICONTROL segments]. [!UICONTROL Segments] サイト訪問者を関連するグループに整理します。 The following table defines the three principal components in an [!DNL Audience Manager] [!UICONTROL segment].

| 要素 | 構成 | 例 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] は、の最小のデータ単位 [!DNL Audience Manager] で、 [キーと値のペアとして表されます](../reference/key-value-pairs-explained.md)。<br><br><ul><li>キーは、データセットを定義する定数です（例：gender、color、price）。</li><li>値は、定数に関連する変数です（例：male/female、green、100）。</li></ul>比較演算子は、キーと値を結合して、それらの間の関係を設定します。 | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinations of one or more [!UICONTROL signals].<br><br> [!DNL Boolean] 式と比較演算子を使用して、 [!UICONTROL trait] 資格ルールを作成できます。 <br><br>とグループを組み合わせて、正確な資格要件 [!UICONTROL traits] を作成し [!UICONTROL trait] ます。 | From the available [!UICONTROL signals], you could create a `High End Camera Browser` rule expressed as: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Users who share a set of common attributes and qualify for related [!UICONTROL traits]. [!DNL Boolean] 式は、最新性/頻度の要件に加え、 [!UICONTROL segment] 資格ルールを作成できます。<br><br> とルールを組み合わせて、正確な資格要件 [!UICONTROL trait] を作成し [!UICONTROL segment] ます。 | From the available [!UICONTROL traits] and [!UICONTROL signals], you could create a [!UICONTROL segment] rule expressed as:`(product=camera AND type=digital SLR) OR (price>1000)` |

Use the diagram below to keep a mental note of the relationship between [!UICONTROL signals], [!UICONTROL traits], and [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**ビジュアルツール [!UICONTROL Traits] とコードエディターを使用したビルド [!UICONTROL Segment] とルール**

Clients manage [!UICONTROL traits] and [!UICONTROL segments] with visual tools and code editors in the [!DNL Audience Manager] user interface. ビジュアルツールでは、検索機能、ポップアップオプション、ドロップダウンメニューおよびドラッグ＆ドロップ機能を使用して、ルールを作成できます。コードエディターは、上級ユーザーがオーディエンスセグメント化条件をプログラムで開発する手段となります。

**イベント呼び出しのデータの送信先[!DNL Audience Manager]**

イベント呼び出しは、Webサイトから [!DNL Audience Manager] にデータを送信します。この呼び出しには、リク [!UICONTROL signal]エスト内の、、 [!UICONTROL trait]および [!UICONTROL segment][!DNL HTTP] データが含まれます。 イベント自体は 文字列の `/event` に続くすべての部分です。[!DNL URL]次の例に示すように、このプロセスでは、複数の変数を [!DNL Audience Manager] に渡すために必要なイベント呼び出しは 1 つだけです。

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [セグメント：目的、構成、ルール](../features/segments/segments-purpose.md)

