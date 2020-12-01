---
description: Audience Manager にデータを送信する際に従う必要がある必須フィールド、構文、命名規則、ファイルサイズについて説明します。データを Audience Manager または Amazon S3 ディレクトリに送信する際には、これらの仕様に従ってファイルの名前とサイズを設定してください。
seo-description: Audience Manager にデータを送信する際に従う必要がある必須フィールド、構文、命名規則、ファイルサイズについて説明します。データを Audience Manager または Amazon S3 ディレクトリに送信する際には、これらの仕様に従ってファイルの名前とサイズを設定してください。
seo-title: 受信データファイルの Amazon S3 名とファイルサイズの要件
solution: Audience Manager
title: 受信データファイルの Amazon S3 名とファイルサイズの要件
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: f037a12af641da44ed67e62a249c41487da7ac07
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 100%

---


# [!DNL Amazon S3]受信データファイルの 名とファイルサイズの要件 {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

[!DNL Audience Manager] にデータを送信する際に従う必要がある必須フィールド、構文、命名規則、ファイルサイズについて説明します。データを [!DNL Audience Manager]／[!DNL Amazon S3]ディレクトリに送信する際に、これらの仕様に応じて、ファイルの名前およびサイズを設定します。

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
   <td colname="col2"> <p>データファイルに、独自のユーザー ID、Android ID、iOS ID または<a href="/help/using/features/global-data-sources.md">グローバルデータソース</a>に属する他の ID が含まれているかどうかを <span class="keyword">Audience Manager</span> に伝える lD。次のオプションを使用できます。</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>データソース ID（別名データプロバイダー ID）：</b> これは、Audience Managerがデータソースに割り当てる一意の ID です（ID の Audience Manager <a href="/help/using/reference/ids-in-aam.md"> インデックスを参照 </a>）。ご自身のユーザー ID が含まれているデータを送信する場合に、この割り当て済みの ID をファイル名に入れます。例えば、<code>...ftp_dpm_21_123456789.sync</code> は、<span class="keyword">Audience Manager</span> に対して、データソース 21 に属する ID データをオンボードするよう伝えます。 </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID（GAID）：</b>データファイルに Android の ID が含まれている場合、ファイル名に ID 20914 を使用します。Android ID を使用する場合は、このフィールド <code><i>_DPID_TARGET_DATA_OWNER</i></code> を使用する必要があります。例えば、<code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> データファイルに Android ID のみが含まれ、その ID はデー <code><i>_DPID_TARGET_DATA_OWNER</i></code> タソースに属する特性に適合する必要があると <span class="keyword">Audience Manager</span> に伝えます。</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID（IDFA）：</b>データファイルに iOS の ID が含まれている場合、ファイル名に ID 20915 を使用します。iOS ID を使用する場合は、このフィールド <code><i>_DPID_TARGET_DATA_OWNER</i></code> を使用する必要があります。例えば、<code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> データファイルに iOS ID のみが含まれ、その ID はデー <code><i>_DPID_TARGET_DATA_OWNER</i></code> タソースに属する特性に適合する必要があると <span class="keyword">Audience Manager</span> に伝えます。</li>
     <li> <b>他のグローバルデータソースに属する ID：広告用の</b>：広用の Roku ID（RIDA）、Microsoft Advertising ID（MAID）、およびその他の ID をオンボードできます。各データソースに対応する ID を使用します。詳しくは、<a href="/help/using/features/global-data-sources.md">グローバルデータソースに関する記事</a>を参照してください。</li> 
    </ul> <p> <p>注意：データファイル内で ID タイプが混在しないようにしてください。例えば、ファイル名に Android の ID が含まれている場合、データファイル内に iOS の ID やご自身の ID を入れないでください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>このフィールドは、データのオンボーディング先となるデータソースを Audience Manager に示します。このフィールドは、DPID を Android ID または iOS ID、またはグローバルデータソースに属する他の ID に設定した場合は必須です。これにより、<span class="keyword">Audience Manager</span> はファイルデータを組織にリンクすることができます。 </p> <p>例： </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code>データソース 33 に属する顧客 ID をデータソース 21 に属する特性またはシグナルに認定していることを Audience Manager に通知します。 </li> 
     <li> <b>Android ID（GAID）：</b><code>...ftp_dpm_20914_21_1234567890.sync</code> データファイルに Android ID のみが含まれ、その ID はデータソース 21 に属する特性に適合する必要があると <span class="keyword">Audience Manager</span> に伝えます。</li> 
     <li> <b>iOS ID（IDFA）：</b><code>...ftp_dpm_20915_21_1234567890.sync</code> データファイルに iOS ID のみが含まれ、その ID はデータソース 21 に属する特性に適合する必要があると <span class="keyword">Audience Manager</span> に伝えます。</li>
     <li> <b>他のグローバルデータソースに属する ID</b>：<code>...ftp_dpm_121963_21_1234567890.sync</code> データファイルに Roku ID のみが含まれ、その ID はデータソース 21 に属する特性に適合する必要があると <span class="keyword">Audience Manager</span> に伝えます。各データソースに対応する ID を使用します。詳しくは、<a href="/help/using/features/global-data-sources.md">グローバルデータソースに関する記事</a>を参照してください。</li> 
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

## 許容されるファイルサイズ  {#accepted-file-sizes}

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

