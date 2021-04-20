---
description: この仕様に従ってオーディエンスの最適化のメタデータファイルの名前を設定します。
seo-description: この仕様に従ってオーディエンスの最適化のメタデータファイルの名前を設定します。
seo-title: メタデータファイルの命名規則
solution: Audience Manager
title: メタデータファイルの命名規則
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: Log Files
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 100%

---

# メタデータファイルの命名規則 {#naming-conventions-for-metadata-files}

この仕様に従ってオーディエンスの最適化のメタデータファイルの名前を設定します。

## 構文と ID カテゴリ {#syntax}

次の構文は、適正なメタデータファイル名の構造を示しています。なお、*斜体*&#x200B;の部分には実際の情報が入ります。その他の要素は定数で、変動しません。

**構文：**  *`yyyymmdd_0_childID`*

>[!NOTE]
>
>メタデータファイルにファイル拡張子を&#x200B;*使用しない*&#x200B;でください（.txt など）。

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* 中央のコンポーネント **0** は、技術的には親 ID であり、従来のフィールドです。値は常に **0** として設定する必要があります。
* 子 ID には、ディメンションに応じて 1 ～ 10 の値を指定できます。次を参照してください。

## 子 ID ディメンション {#child-dimension}

メタデータファイル名において、子 ID は、ファイル内のデータのタイプを分類しデータを階層に配置する識別子になります。ファイル名の子 ID には、次のカテゴリ ID でタグ付けできます。

1. Campaign
1. Creative
1. Placement
1. Exchange
1. Site
1. 広告主（[データソース](../../../features/manage-datasources.md#details)で統合コードを使用する場合）
1. 広告掲載申込（IO）
1. バーティカル（「コンピューター」、「自動車」、「不動産」などの業界カテゴリや事業カテゴリ）
1. 戦術
1. ビジネスユニットまたはブランド

## 例 {#example}

クリエイティブメタデータファイルの場合、ファイル名は 20190115_0_2 となります。

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
