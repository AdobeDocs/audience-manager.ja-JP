---
description: ルールベースおよびオンボードの特性の作成プロセスに固有のセットアップ手順や機能について説明します。
keywords: create trait;create traits
seo-description: ルールベースおよびオンボードの特性の作成プロセスに固有のセットアップ手順や機能について説明します。
seo-title: ルールベースまたはオンボードの特性の作成
solution: Audience Manager
title: ルールベースまたはオンボードの特性の作成
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
translation-type: tm+mt
source-git-commit: 0869e016d7f80710cb194449c48675b82fdfa865
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 78%

---


# 必要に応じてページアプリを作成[!UICONTROL Rules-Based]または [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

[!UICONTROL rules-based]および[!UICONTROL onboarded]特性の作成プロセスに特有のセットアップ手順や機能について説明します。

<!-- c_tb_rules_traits.xml -->

## 特性の基本情報 {#basics}

In [!UICONTROL Trait Builder], the [!UICONTROL Basic Information] settings let you create new, or edit existing [!UICONTROL traits]. との [!UICONTROL Basic Information] 設定は、 [!UICONTROL rules-based]と [!UICONTROL onboarded] で同じで [!UICONTROL algorithmic traits]す。 新しいを作成するに [!UICONTROL trait]は、名前（特殊文字は使用しない）とaを指定し [!UICONTROL data source]、を選択し [!UICONTROL storage folder]ます。 それ以外の[!UICONTROL Basic Information]フィールドはオプションです。

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### 基本情報フィールドの定義

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> インターフェイス要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 名前</span></b> </td> 
   <td colname="col2"> <p>特性名。必須。 </p> <p>最大長： 255 文字。 </p> <p> <p>注意：特性に名前を付ける場合、以下の特殊文字は使用しないでください。 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">コンマ </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">ダッシュ </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">ハイフン </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">タブ </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">縦棒またはパイプ記号 </li> 
      </ul> </p> </p> <p>これは、<a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">受信データファイル転送</a>を設定する際の処理エラーを削減するのに役立ちます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Description</span></b> </td> 
   <td colname="col2"> 特性の目的や機能を説明する短い文章。オプションです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> データソース</span></b> </td> 
   <td colname="col2"> 特性を特定のデータプロバイダーに関連付けます。必須。 <p>最初のドロップダウンメニューを使用して、Audience Manager のデータソース、Adobe Analytics のレポートスイート、またはその両方をフィルタリングします。次に、2 番目のドロップダウンメニューを使用して、データソースを選択します。</p><p> Adobe Analytics レポートスイートを使用しない場合、データソースタイプセレクターは無効になり、デフォルトで Audience Manager データソースのみに設定されます。</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Event Type</span></b> </td> 
   <td colname="col2"> 通常、関数（例：コンバージョン、サイト訪問者、パートナー、ページビューなど）に従って、特性をタイプまたはカテゴリに割り当てます。オプションです。 <p> コンバージョン特性の作成方法について詳しくは、<a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Audience Manager でのコンバージョン特性の作成のビデオ</a>を参照してください。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 統合コード</span></b> </td> 
   <td colname="col2"> ID、SKU または社内ビジネスプロセスで使用されるその他の値のためのフィールド。オプションです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Comments</span></b> </td> 
   <td colname="col2"> 特性に関する一般的なメモ。オプションです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Store In</span></b> </td> 
   <td colname="col2"> 特性が属するストレージフォルダーを決定します。必須。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Data Category</span></b> </td> 
   <td colname="col2"> 一般的に理解されているカテゴリに従って、特性を分類します。 <p>注意：特性は、単一のカテゴリのみに属します。オプションです。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Set a [!UICONTROL Trait] Expiration Interval {#set-expiration-interval}

In [!UICONTROL Trait Builder], the [!UICONTROL Advanced Options] lets you set a time-to-live ([!DNL TTL]) interval for a [!UICONTROL trait]. [!DNL TTL] 条件を満たした訪問者が1回に残る日数を定義し [!UICONTROL trait] ます（デフォルトは120日）。 When set to 0, [!UICONTROL trait] membership never expires.

<!-- t_tb_ttl.xml -->

### Set the TTL for a [!UICONTROL trait]

1. Expand the [!UICONTROL Advanced Options] section and enter a number to set a [!DNL TTL] value for the [!UICONTROL trait].
1. 「**[!UICONTROL Save]**」をクリックします。

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [セグメント有効期間の説明](../../features/traits/segment-ttl-explained.md)

