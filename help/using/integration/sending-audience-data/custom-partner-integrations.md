---
description: このページには、Audience Manager とデータパートナー間のカスタム統合の一覧が掲載されています。
seo-description: このページには、Audience Manager とデータパートナー間のカスタム統合の一覧が掲載されています。
seo-title: カスタムパートナー統合
solution: Audience Manager
title: カスタムパートナー統合
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Custom Partner Integrations {#custom-partner-integrations}

このページには、Audience Manager とデータパートナー間のカスタム統合の一覧が掲載されています。

## Oracle Data Cloud {#oracle-data-cloud}

**Description**

Audience Manager は、受信データファイルを使用して、Oracle Data Cloud for Audience Marketplace から cookie とモバイル ID データを取り込みます。後述のカスタム統合仕様は、モバイルID（IDFAおよびAndroidデバイスID）を含む受信データファイルのみを参照します。

<br> 

**統合の詳細**

Inbound Data Files received from the Oracle Data Cloud differ from the standard inbound file name syntax described in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the standard inbound file content syntax described in [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

以下に示す要素は、受信データファイルの標準実装フィールドに加えて、必須です。他のすべての標準フィールドおよびファイル名要素の説明については、前述の2つのページの「ファイル名構文とファイルコンテンツ構文」を参照してください。

<br> 

**ファイルの命名**

ODCファイル名は次のように構造化されています。

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

`odc` file name要素は、Oracle Data Cloudからインポートされたファイルを識別し、Audience Managerの受信ファイルバリデーターにそれを処理するように指示します。

<br> 

**ファイルの内容**

ODC受信データファイルのフィールドは、以下の順序で表示する必要があります。

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;user ID&gt;&lt;TAB&gt;&lt;trait ID&gt;,&lt;trait ID&gt;,&lt;trait ID&gt;,...</pre>

`ID type` 次のことができます。

* IDFA
* AndroidデバイスID

>[!IMPORTANT]
>
>同じ受信データファイルでIDFAおよびAndroidデバイスIDを送信しないでください。

<br> 

**ODC受信ファイルのサンプル**

[サンプルファイルをダウンロード](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)します。このファイルでは、特性ID38838の複数のIdFAを指定します。このファイルは、標準のテキストエディターまたはコードエディターで開くことができます。