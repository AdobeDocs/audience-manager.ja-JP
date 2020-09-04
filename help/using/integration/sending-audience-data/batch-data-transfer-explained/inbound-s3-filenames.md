---
description: Audience Manager にデータを送信する際に従う必要がある必須フィールド、構文、命名規則、ファイルサイズについて説明します。データを Audience Manager または Amazon S3 ディレクトリに送信する際には、これらの仕様に従ってファイルの名前とサイズを設定してください。
seo-description: Audience Manager にデータを送信する際に従う必要がある必須フィールド、構文、命名規則、ファイルサイズについて説明します。データを Audience Manager または Amazon S3 ディレクトリに送信する際には、これらの仕様に従ってファイルの名前とサイズを設定してください。
seo-title: 受信データファイルの Amazon S3 名とファイルサイズの要件
solution: Audience Manager
title: 受信データファイルの Amazon S3 名とファイルサイズの要件
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: adab01a81c0002d28c2387a20d8ae284e11a5e41
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 96%

---


# [!DNL Amazon S3]受信データファイルの 名とファイルサイズの要件 {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to [!DNL Audience Manager]. Set the names and sizes of your files according to these specifications when you send data to an [!DNL Audience Manager] / [!DNL Amazon S3] directory.

>[!NOTE]
>
>テキストスタイル（`monospaced text`、*斜体*、括弧 `[ ]` `( )`、その他）コード要素およびオプションを表します。詳しくは、[コードおよびテキスト要素のスタイル規則](../../../reference/code-style-elements.md)を参照してください。

## ファイル名の構文 {#file-name-syntax}

[!DNL S3] ファイル名は、次の必須要素とオプション要素で構成されています。

* **[!DNL S3]プレフィックス：**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **ファイル名要素：**`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

使用可能なその他のファイル名の形式については、[カスタムパートナー統合](/help/using/integration/sending-audience-data/custom-partner-integrations.md)を参照してください。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] は、[!DNL ASCII] と [!DNL UTF-8] でエンコードされたファイルのみを処理します。

### 名前の要素

次の表は、[!DNL S3] ファイル名の要素の定義を示しています。

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名前の要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 バケットのパスと名前。S3 ディレクトリの名前、パス、資格情報については、担当のアカウントマネージャーにお問い合わせください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>ファイルを S3 バケットに送信した時点を示すタイムスタンプ（UTC 時間に基づく）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p><span class="term">データプロバイダー ID</span>（DPID）は、データファイルにご自身のユーザー ID、または Android か iOS の ID が含まれているかどうかを <span class="keyword">Audience Manager</span> に通知するための ID です。次のオプションを使用できます。 </p> <p> <b>データパートナー ID</b> </p> <p>Audience Manager が会社や組織に割り当てる一意の ID です。ご自身のユーザー ID が含まれているデータを送信する場合に、この割り当て済みの ID をファイル名に入れます。例えば、「<code>...ftp_dpm_21_123456789.sync</code>」は、ID が 21 であるパートナーがファイルの送信者で、このファイルにはそのパートナーが割り当てたユーザー ID が含まれていることを <span class="keyword">Audience Manager</span> に通知します。 </p> <p> <b>Android ID（GAID）</b> </p> <p> ファイルに Android ID が含まれている場合、データファイル名の DPID として ID 20914 を使用します。DPID として ID 20914 を使用する場合、<span class="keyword">Audience Manager</span> で会社を特定する必要があります。つまり、ファイル名で <code><i>_DPID_TARGET_DATA_OWNER</i></code> パラメーターを使用して会社 ID を含める必要があります。例えば、Android ID が含まれるファイルを渡そうとしていて、データプロバイダー ID が 21 であるとします。この場合、ファイル名は <code>...ftp_dpm_20914_21_123456789.sync</code> のようになります。これにより、<span class="keyword">Audience Manager</span> は、ファイルに Android ID が含まれていること、およびこのファイルが ID 21 のパートナーからのものであることを認識します。 </p> <p> <b>iOS ID（IDFA）</b> </p> <p> ファイルに iOS ID が含まれている場合、データファイル名の DPID として ID 20915 を使用します。DPID として ID 20915 を使用する場合、<span class="keyword">Audience Manager</span> で会社を特定する必要があります。つまり、ファイル名で <code><i>_DPID_TARGET_DATA_OWNER</i></code> パラメーターを使用して会社 ID を含める必要があります。例えば、Android ID が含まれるファイルを渡そうとしていて、データプロバイダー ID が 21 であるとします。この場合、ファイル名は <code>...ftp_dpm_20915_21_123456789.sync</code> のようになります。これにより、<span class="keyword">Audience Manager</span> は、ファイルに iOS ID が含まれていること、およびこのファイルが ID 21 のパートナーからのものであることを認識します。 </p> 
    <!-- 
     <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
      <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Data Partner ID:</b> This is a unique ID Audience Manager assigns to your company or organization. Use this assigned ID in a file name when sending in data that contains your own user IDs. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
      <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android IDs (GAID):</b> Use ID 20914 in a data file name if it contains Android ID. For example, <code>...ftp_dpm_20914_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. Note, the ID 21 </li> 
      <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS IDs (IDFA):</b> Use ID 20915 in a data file name if it contains iOS IDs. For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
     </ul> 
    --> <p> <p>注意：データファイル内で ID タイプが混在しないようにしてください。例えば、ファイル名に Android の ID が含まれている場合、データファイル内に iOS の ID やご自身の ID を入れないでください。 </p> </p><p>詳しくは、「<a href="https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/features/data-sources/global-data-sources.html">グローバルデータソース</a>」を参照してください。</p> <p>下記の <code><i>_DPID_TARGET_DATA_OWNER</i></code> エントリも参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>ID のプレースホルダー。例えば、DPID をデータソース ID か、Android または iOS の ID に設定した場合、これを <span class="keyword">Audience Manager</span> ID に設定することができます。これにより、<span class="keyword">Audience Manager</span> はファイルデータを組織にリンクすることができます。 </p> <p>次に例を示します。 </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> 「<code>...ftp_dpm_33_21_1234567890.sync</code>」は、ID が 21 であるパートナーが、ID が 33 であるデータソースからのデータを送信したことを示しています。 </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> 「<code>...ftp_dpm_20914_21_1234567890.sync</code>」は、ID が 21 であるパートナーが、Android の ID を含むデータを送信したことを示しています。 </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> 「<code>...ftp_dpm_20915_21_1234567890.sync</code>」は、ID が 21 であるパートナーが、iOS の ID を含むデータを送信したことを示しています。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> で使用する会社または組織の名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>10 桁の UTC UNIX タイムスタンプ（秒単位）。タイムスタンプは、各ファイル名を一意にするのに役立ちます。 </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同期オプション。以下のものがあります。 </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>：通常のシナリオ。サードパーティデータプロバイダーが、Audience Manager システムで追加または削除するユーザー単位の特性を送信します。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>：データプロバイダーはユーザー単位の特性のリストを送信できます。これにより、Audience Manager で特定のデータプロバイダーについて当該ユーザーの既存のサードパーティ特性がすべて上書きされます。すべてのユーザーを上書きファイルに入れる必要はありません。変更するユーザーのみを入れるようにしてください。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整数。大きなファイルを複数に分割して処理時間を短縮する場合に使用します。数は、送信している元のファイルのどの部分かを示します。 </p> <p>ファイル処理を効率的に実行するために、データファイルを次のように分割します。 </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">圧縮なし：1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">圧縮済み：200～300 MB </li> 
    </ul> <p>以下の 2 つの<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples">ファイル名の例</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>ファイルを Amazon S3 に送信する場合、gzip 圧縮のみを使用します。これらのファイルを圧縮すると、拡張子は <code> .gz</code> になります。.zip 圧縮は使用しないでください。 </p> <p>圧縮ファイルのサイズは 3 GB 以下である必要があります。ファイルがそれより大きい場合は、カスタマーケアにお問い合わせください。Audience Manager で大きなファイルを操作することは可能ですが、ファイルのサイズを小さくして、効率的にデータを転送できるようにすることもできます。詳しくは、<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">受信データ転送ファイルのファイル圧縮</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## ファイル名の例 {#file-name-examples}

以下に、適切に書式設定されたファイル名の例を示します。ファイル名は、このようになります。

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

追加の例が必要であれば、サンプルを[ダウンロード](assets/ftp_dpm_1234_1445374061.overwrite)することもできます。このファイルは `.overwrite` ファイル拡張子で保存されます。これを普通のテキストエディターで開きます。

## 許容されるファイルサイズ {#accepted-file-sizes}

データを [!DNL Audience Manager] や [!DNL Amazon S3] ディレクトリに送信する際の最速／最短のファイル処理やファイルサイズの制限については、以下の数字を考慮してください。

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファイルタイプ </th> 
   <th colname="col2" class="entry"> 最適なサイズ </th> 
   <th colname="col3" class="entry"> 最大サイズ </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>圧縮済み</b> </td> 
   <td colname="col2"> <p>200～300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>圧縮なし</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>受信データの検証プロセスでは、空のファイルは無効としてマークされます。

>[!MORELIKETHIS]
>
>* [受信データファイルの FTP の名前に関する要件](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

