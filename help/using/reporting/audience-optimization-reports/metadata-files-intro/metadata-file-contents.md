---
description: オーディエンスの最適化のメタデータファイルのコンテンツを、以下の仕様に従って書式設定します。
seo-description: オーディエンスの最適化のメタデータファイルのコンテンツを、以下の仕様に従って書式設定します。
seo-title: メタデータファイルのコンテンツの形式
solution: Audience Manager
title: メタデータファイルのコンテンツの形式
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# メタデータファイルのコンテンツの形式{#content-format-for-metadata-files}

オーディエンスの最適化のメタデータファイルのコンテンツを、以下の仕様に従って書式設定します。

## 構文{#syntax}

次の構文は、メタデータファイルの適正なコンテンツの構造を示しています。なお、*斜体*の部分には実際の情報が入ります。

**構文：**  *content ID* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

3 番目の列 **-1** は、レガシーフィールドの親 ID です。値は常に **-1** に設定する必要があります。

>[!NOTE]
>
>ディメンションごとにメタデータが 1 つ必要なので、複数のメタデータファイルはバケットで想定されます。ディメンションは、記事[メタデータファイルの命名規則](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)で一覧表示されています。

**ファイルエントリを ^a（Ctrl + A または ASCII 001）で区切る**

Use `^a` (control-A or ASCII 001) to separate content in your metadata files. これらは非印字文字なので、上記の構文例では、表示のためだけにパイプ「|」を使用しています。

If needed, you may download the example file - [20181105_0_1](assets/20181105_0_1.zip). 必要な区切り文字が既に含まれているため、選択したエディターでそれを解凍して編集し、実際のメタデータコンテンツに従って調整します。

>[!IMPORTANT]
>
>メタデータファイルにヘッダー行を追加しないでください。

## 例 {#examples}

メタデータファイルのコンテンツを構成する方法を紹介します。この構造の一部は、ディメンションによって異なります。ディメンションは、記事[メタデータファイルの命名規則](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)で一覧表示されています。

**Campaign**

この例では、ファイルタイトルは 20180921_0_1 で、ファイルの 3 つの列はキャンペーン ID、名前、親 ID です。

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**クリエイティブ**

この例では、ファイルタイトルは 20180827_0_2 で、ファイルの 3 つの列はクリエイティブ ID、名前、親 ID です。

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**サイト**

この例では、ファイルタイトルは 20180921_0_5 で、ファイルの 3 つの列はサイト ID、名前、親 ID です。

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
