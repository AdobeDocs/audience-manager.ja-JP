---
description: このページには、Audience Manager とデータパートナー間のカスタム統合の一覧が掲載されています。
seo-description: このページには、Audience Manager とデータパートナー間のカスタム統合の一覧が掲載されています。
seo-title: カスタムパートナーの統合
solution: Audience Manager
title: カスタムパートナーの統合
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# カスタムパートナーの統合{#custom-partner-integrations}

このページには、Audience Manager とデータパートナー間のカスタム統合の一覧が掲載されています。

## Oracle Data Cloud {#oracle-data-cloud}

**説明**

Audience Manager は、受信データファイルを使用して、Oracle Data Cloud for Audience Marketplace から cookie とモバイル ID データを取り込みます。以下で説明するカスタム統合仕様は、モバイル ID（IDFA および Android デバイスID）を含む受信データファイルのみを対象としています。

<br> 

**統合の詳細**

Oracle Data Cloudから受信した受信データファイルは、[受信データファイルの Amazon S3 名とファイルサイズの要件Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) で説明されている標準的な受信ファイル名構文や、[受信データファイルコンテンツ：構文、無効な文字、変数、例](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)で説明されている標準的な受信ファイルコンテンツ構文とは異なります。

受信データファイルの標準実装フィールドに加えて、以下に示す要素が必須です。他のすべての標準フィールドおよびファイル名要素の説明については、上記にリンクされている 2 つのページの「ファイル名構文」と「ファイルコンテンツ構文」を参照してください。

<br> 

**ファイルの命名**

ODC ファイル名の構造は次のようになります。

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

`odc`file name 要素は、ファイルが Oracle Data Cloud から読み込まれたことを識別し、Audience Manager の受信ファイルバリデーターに対してそのように処理するように指示します。

<br> 

**ファイルコンテンツ**

受信データファイルのフィールドは、以下の順序で表示される必要があります。

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;ユーザー ID&gt;&lt;TAB&gt;&lt;特性 ID&gt;、&lt;特性 ID&gt;、&lt;特性 ID&gt;、...</pre>

`ID type` には、次のことができます。

* IDFA
* Android デバイス ID

>[!IMPORTANT]
>
>同じ受信データファイルで IDFA と Android デバイス ID を送信しないでください。

<br> 

**ODC 受信ファイルのサンプル**

[サンプルファイル](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)をダウンロードします。このファイルは、特性 ID38838 の複数の IDFA を認定します。このファイルは、標準のテキストエディターまたはコードエディターで開くことができます。