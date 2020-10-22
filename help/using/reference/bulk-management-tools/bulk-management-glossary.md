---
description: 列ヘッダーのラベルの定義。
seo-description: 列ヘッダーのラベルの定義。
seo-title: 一括管理ツールの用語集
solution: Audience Manager
title: 一括管理ツールの用語集
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: baaam
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 100%

---


# 一括管理ツールの用語集 {#bulk-management-tools-glossary}

列ヘッダーのラベルの定義。

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[!DNL Audience Manager] UI で割り当てられる [RBAC グループ権限](../../features/administration/administration-overview.md)は、[!UICONTROL Bulk Management Tools] に対しても適用されます。

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 列ヘッダー </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> dataSourceId</span> </p> </td> 
   <td colname="col2"> <p>一括で返す、または割り当てる<a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings">データソース</a>の ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p><a href="../../features/derived-signals.md">派生シグナル</a> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">description</span> </p> </td> 
   <td colname="col2"> <p>オブジェクトについての簡単でわかりやすい説明。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>マッピングまたは削除する<a href="../../features/destinations/destinations.md">宛先</a>の ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>セグメントが宛先にマッピングされた時点でセグメントに割り当てられる特別な ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>セグメントフォルダーまたは特性フォルダーの ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>操作しているオブジェクトの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>他のフォルダーが格納されているセグメントフォルダーまたは特性フォルダーの ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>セグメント ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>シグナルは、ユーザーアクティビティに基づいて <span class="keyword">Audience Manager</span> に渡されるデータのビットです。これらは<a href="../../reference/key-value-pairs-explained.md">キー値ペア</a>として渡されます。ソースキーは定数で、変動しません。これにより、変動する可能性があるソース値を分類できます。<a href="../../features/derived-signals.md">派生シグナル</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>ソース値は、<a href="../../reference/key-value-pairs-explained.md">キー値ペア</a>として渡される変数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>宛先へのセグメントの送信を開始できる時点を表します。<i>yyyy-mm-dd</i> 形式で表されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">派生シグナルで使用するキー。<a href="../../features/derived-signals.md">派生シグナル</a>を参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>派生シグナルキーで渡された値。<a href="../../features/derived-signals.md">派生シグナル</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>Cookie ベースでない宛先に渡される ID。Cookie ベースの宛先の場合、これは<a href="../../reference/key-value-pairs-explained.md">キー値ペア</a>として渡される変数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule／segmentRule</span> </p> </td> 
   <td colname="col2"> <p>データの収集に使用する実際の特性ルールまたはセグメントルール。一括リクエストは、<span class="keyword">Audience Manager</span> で<a href="../../features/traits/about-trait-builder.md">特性ルールビルダー</a>または<a href="../../features/segments/segment-builder.md">セグメントルールビルダー</a>により作成されたルールを返します。これらのツールを使用して、セグメントや特性の構成時にルールを作成して一括で適用することもできます。 </p> <p>詳しくは、<a href="../../reference/bulk-management-tools/bulk-rules.md">特性ルールとセグメントルールの作成と更新</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>特性タイプを識別する文字列。オプションは以下のとおりです。 </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>ユーザーがセグメントを認定する際に DIL により生成されるピクセル。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>Cookie の宛先に渡された<a href="../../reference/key-value-pairs-explained.md">キー値ペア</a>のキー。 </p> </td> 
  </tr> 
 </tbody> 
</table>

