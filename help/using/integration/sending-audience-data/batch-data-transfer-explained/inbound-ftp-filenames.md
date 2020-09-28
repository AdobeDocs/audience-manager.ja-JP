---
description: Audience Manager にデータを送信する際に従う必要がある必須フィールド、構文、命名規則、ファイルサイズについて説明します。データを Audience Manager／FTP ディレクトリに送信する際に、これらの仕様に応じて、ファイルの名前およびサイズを設定します。
seo-description: Audience Manager にデータを送信する際に従う必要がある必須フィールド、構文、命名規則、ファイルサイズについて説明します。データを Audience Manager／FTP ディレクトリに送信する際に、これらの仕様に応じて、ファイルの名前およびサイズを設定します。
seo-title: 受信データファイルの FTP 名とファイルサイズの要件
solution: Audience Manager
title: 受信データファイルの FTP 名とファイルサイズの要件
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e8eb1c1c7a235c0c9dd32182e522ad0b6e965c61
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 81%

---


# [!DNL FTP]受信データファイルの 名とファイルサイズの要件 {#ftp-name-and-file-size-requirements-for-inbound-data-files}

Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to [!DNL Audience Manager]. データを Audience Manager [!DNL FTP] ディレクトリに送信する際に、これらの仕様に応じて、ファイルの名前およびサイズを設定します。

>[!WARNING]
>
>We are gradually phasing out support for [!DNL FTP] configurations. While inbound data file ingestion is still supported in existing [!DNL FTP] integrations, we strongly recommend using [!DNL Amazon S3] to onboard offline data for new integrations. 詳細は、[受信データファイルの Amazon S3 名とファイルサイズの要件](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)を参照してください。

>[!NOTE]
>
>テキストスタイル（`monospaced text`、*斜体*、括弧 `[ ]` `( )`、その他）コード要素およびオプションを表します。詳しくは、[コードおよびテキスト要素のスタイル規則](../../../reference/code-style-elements.md)を参照してください。

## ファイル名の構文 {#file-name-syntax}

[!DNL FTP] ファイル名は、次の必須要素とオプション要素で構成されています。

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

使用可能なその他のファイル名の形式については、[カスタムパートナー統合](/help/using/integration/sending-audience-data/custom-partner-integrations.md)を参照してください。

>[!NOTE]
>
>[!DNL Audience Manager] は、[!DNL ASCII] と [!DNL UTF-8] でエンコードされたファイルのみを処理します。

### 名前の要素

次の表は、[!DNL FTP] ファイル名の要素の定義を示しています。

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファイル名要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> FTP ディレクトリのパスと名前。FTP ディレクトリと資格情報については、アカウントマネージャーにお問い合わせください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>データファイルに独自のユーザーID、Android ID、iOS IDまたはグロー <span class="keyword"> バルデータソースに属する他のIDが含まれているかどうかをAudience Managerに通知するlD</span><a href="/help/using/features/global-data-sources.md"></a>。 次のオプションを使用できます。</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>データソースID（データプロバイダーIDとも呼ばれます）:</b> これは、Audience Managerがデータソースに割り当てる一意のIDです(IDのAudience Manager <a href="/help/using/reference/ids-in-aam.md"> インデックスを参照 </a>)。 ご自身のユーザー ID が含まれているデータを送信する場合に、この割り当て済みの ID をファイル名に入れます。例えば、 <code>...ftp_dpm_21_123456789.sync</code> Audience Managerに対して、データソース21に属するIDに対して車載データを通知する <span class="keyword"></span> 。 </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GAID):</b> Android IDが含まれる場合は、データファイル名にID 20914を使用します。 例えば、「<code>...ftp_dpm_20914_123456789.sync</code>」は、データファイルに Android の ID しか含まれていないことを <span class="keyword">Audience Manager</span> に通知します。 </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID（IDFA）：</b>データファイルに iOS の ID が含まれている場合、ファイル名に ID 20915 を使用します。例えば、「<code>...ftp_dpm_20915_123456789.sync</code>.」は、データファイルに iOS の ID しか含まれていないことを <span class="keyword">Audience Manager</span> に通知します。 </li>
     <li> <b>他のグローバルデータソースに属するID</b>:広告用のRoku ID(RIDA)、Microsoft広告用ID(MAID)、その他のIDを搭載できます。 各データソースに対応するIDを使用します。詳しくは、「 <a href="/help/using/features/global-data-sources.md"> グローバルデータソース」の記事を参照</a>。</li> 
    </ul> <p> <p>注意：データファイル内で ID タイプが混在しないようにしてください。例えば、ファイル名に Android の ID が含まれている場合、データファイル内に iOS の ID やご自身の ID を入れないでください。 </p> </p> </td> 
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
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同期オプション。以下のものがあります。 </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>：通常のシナリオ。サードパーティデータプロバイダーが、Audience Manager システムで追加または削除するユーザー単位の特性を送信します。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>：顧客とデータプロバイダーはユーザー単位の特性のリストを送信できます。これにより、Audience Manager で特定のデータソースについて当該ユーザーの既存の特性がすべて上書きされます。すべてのユーザーを上書きファイルに入れる必要はありません。変更するユーザーのみを入れるようにしてください。ターゲットデータソースに割り当てられていない特性は消去されません。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整数。大きなファイルを複数に分割して処理時間を短縮する場合に使用します。数は、送信している元のファイルのどの部分かを示します。 </p> <p>ファイル処理を効率的に実行するために、データファイルを次のように分割します。 </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">圧縮なし：1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">圧縮済み：200～300 MB </li> 
    </ul> <p>以下の 2 つの<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples">ファイル名の例</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>10 桁の UTC UNIX タイムスタンプ（秒単位）。タイムスタンプは、各ファイル名を一意にするのに役立ちます。 </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip は、FTP ファイル名として許可されている圧縮形式です。ファイル圧縮を使用する場合、ファイル名の拡張子が適切であることを確認します。 </p> <p>圧縮ファイルのサイズは 3 GB 以下である必要があります。ファイルがそれより大きい場合は、カスタマーケアにお問い合わせください。Audience Manager で大きなファイルを操作することは可能ですが、ファイルのサイズを小さくして、効率的にデータを転送できるようにすることもできます。詳しくは、<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">受信データ転送ファイルのファイル圧縮</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## ファイル名の例 {#file-name-examples}

以下に、適切に書式設定されたファイル名の例を示します。ファイル名は、このようになります。

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

他の例が必要な場合は、サンプルファイルを[ダウンロードします](assets/ftp_dpm_1234_1445374061.overwrite)。このファイルは `.overwrite` ファイル拡張子で保存されます。これを普通のテキストエディターで開きます。

## 許容されるファイルサイズ {#accepted-file-sizes}

データを [!DNL Audience Manager] や [!DNL FTP] ディレクトリに送信する際の最速／最短のファイル処理やファイルサイズの制限については、以下の数字を考慮してください。

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

>[!MORELIKETHIS]
>
>* [受信データファイルの Amazon S3 の名前に関する要件](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

