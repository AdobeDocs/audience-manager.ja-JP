---
description: Audience Manager セグメントの構成要素、オーディエンスの認定基準の設定に使用される表現、およびイベント呼び出しでのデータの送信方法について説明します。
seo-description: Audience Manager セグメントの構成要素、オーディエンスの認定基準の設定に使用される表現、およびイベント呼び出しでのデータの送信方法について説明します。
seo-title: シグナル、特性、セグメント
solution: Audience Manager
title: シグナル、特性、セグメント
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# シグナル、特性、セグメント{#signals-traits-and-segments}

Audience Manager セグメントの構成要素、オーディエンスの認定基準の設定に使用される表現、およびイベント呼び出しでのデータの送信方法について説明します。

<!-- 

c_signal_trait_segment.xml

 -->

**構成と目的**

[!DNL Audience Manager] データは、シグナル、特性、セグメントおよび関連する資格認定ルールで構成されます。データ要素とルールが組み合わされてセグメントになります。セグメントによって、サイト訪問者が関連グループに分類、整理されます。[!DNL Audience Manager] セグメントの 3 つの主要な構成要素を次の表で定義します。

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 構成 </th> 
   <th colname="col3" class="entry"> 例 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>シグナル</b> </td> 
   <td colname="col2"> <p>シグナルは <span class="keyword"> Audience Manager</span> で最小のデータ単位で、<a href="../reference/key-value-pairs-explained.md"> キーと値のペア</a>として表現されます。 </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">キーは、データセットを定義する定数です（例：gender、color、price）。 </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">値は、定数に関連する変数です（例：male/female、green、100）。 </li> 
    </ul> <p>比較演算子は、キーと値を結合して、それらの間の関係を設定します。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>特性</b> </td> 
   <td colname="col2"> <p>1 つ以上のシグナルの組み合わせ。 </p> <p>ブール式および比較演算子を使用すると、特性資格認定ルールを作成できます。 </p> <p>特性と特性グループを組み合わせて、詳細な資格認定要件を作成します。 </p> </td> 
   <td colname="col3"> <p>例えば、使用可能なシグナルから、次のような「High End Camera Browser」ルールを作成できます。 </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>セグメント</b> </td> 
   <td colname="col2"> <p>共通する一連の属性を共有し、関連する特性の対象として認定されるユーザー。 </p> <p>ブール式を最新性／頻度要件と共に使用すると、セグメント資格認定ルールを作成できます。 </p> <p>特性とセグメントルールを組み合わせて、詳細な資格認定要件を作成します。 </p> </td> 
   <td colname="col3"> <p>例えば、使用可能な特性およびシグナルから、次のようなセグメントルールを作成できます。 </p> <p><code> (product=camera AND type=digital SLR) OR (price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

以下の図を使用して、シグナル、特性、およびセグメント間の関係を覚えておいてください。

![](assets/signals-traits-segments.png)

**ビジュアルツールおよびコードエディターを使用した特性およびセグメントルールの作成**

クライアントは、[!DNL Audience Manager] ユーザーインターフェイスのビジュアルツールおよびコードエディターを使用して、特性およびセグメントを管理します。ビジュアルツールでは、検索機能、ポップアップオプション、ドロップダウンメニューおよびドラッグ＆ドロップ機能を使用して、ルールを作成できます。コードエディターは、上級ユーザーがオーディエンスセグメント化条件をプログラムで開発する手段となります。

**Audience Manager にデータを送信するイベント呼び出し**

イベント呼び出しは、Webサイトから [!DNL Audience Manager] にデータを送信します。呼び出しには、HTTP リクエストのシグナル、特性およびセグメントデータが含まれます。イベント自体は URL 文字列の `/event` に続くすべての部分です。次の例に示すように、このプロセスでは、複数の変数を [!DNL Audience Manager] に渡すために必要なイベント呼び出しは 1 つだけです。

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_LIKE_THIS]
>
>* [セグメント：目的、構成、ルール](../features/segments/segments-purpose.md)

