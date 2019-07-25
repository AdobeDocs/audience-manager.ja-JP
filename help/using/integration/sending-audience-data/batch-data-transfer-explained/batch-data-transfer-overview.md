---
description: 技術系／非技術系を問わず、他のシステム（オフライン）から Audience Manager にデータを取り込むお客様を対象とした概要説明です。
keywords: inbound
seo-description: 技術系／非技術系を問わず、他のシステム（オフライン）から Audience Manager にデータを取り込むお客様を対象とした概要説明です。
seo-title: Audience Manager へのバッチデータ送信の概要
solution: Audience Manager
title: Audience Manager へのバッチデータ送信の概要
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Audience Manager へのバッチデータ送信の概要{#send-batch-data-to-audience-manager-overview}

技術系／非技術系を問わず、他のシステム（オフライン）から Audience Manager にデータを取り込むお客様を対象とした概要説明です。

## メリット

<!-- c_offline_to_online.xml -->

他のシステムからのデータを Audience Manager で使用可能にできます。アドビのシステムは、値のロック解除および以前収集したユーザーデータの活用に役立ちます。これには、購入、顧客調査、登録データ、[!DNL CRM] データベースなどに関する情報が含まれます。統合ごとに課題がありますが、それらはすべてこれらの一般的な手順を共有します。この資料に目を通せば、オフラインデータをオンラインにするのに必要な労力を削減するうえで役に立ちます。

## 手順 1：ユーザー ID の同期

同期の際に、Audience Manager は一意の ID をクライアントおよびそのユーザーに割り当てます。These IDs are known as the [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) and [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectively. Audience Manager uses the [!UICONTROL DPID] and [!UICONTROL UUID] to identify users and qualify them for traits, segments, audience groups, and for reporting. Additionally, our data collection code ([!UICONTROL DIL]) looks for these IDs to capture visitor data from your website. この手順が完了したら、Audience Manager およびオフラインリポジトリは、各ユーザーレコードに対応する ID を含める必要があります。

この手順に関する重要な考慮事項：

* **クライアント ID の配置：** Audience Manager は、クライアント ID が Web サイトのどこに表示されるかを把握する必要があります（例：Cookie、Analytics 変数、ページコードなどに格納されるか）。
* **の除外：[!DNL PII]**&#x200B;ユーザー ID には、個人を特定できる情報（[!DNL PII]）が含まれないようにする必要があります。
* **大文字と小文字およびコンテンツの区別：**&#x200B;リアルタイムデータ同期の間、Audience Manager によってサイトでキャプチャされたユーザー ID は、オフラインリポジトリから渡された ID に一致する必要があります。For example, if offline records hold information about [!DNL User123], but your site renders that ID as [!DNL USER123], Audience Manager sees these as different visitors. 結果として、この訪問者のオンライン情報は、オフラインデータベース内の対応するレコードに関連付けることができません。ID は、正確に一致する必要があります。

詳しくは、[受信データ転送のための ID 同期](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

<!-- 

<p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p>

 -->

## 手順 2：データファイル形式

ファイル名およびコンテンツは、厳密なガイドラインに従います。このガイドのこれらの仕様に従って、データファイルの命名や編成をおこなう必要があります。**&#x200B;以下を参照してください。

* [受信データファイルの Amazon S3 の名前に関する要件](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [ 受信データファイルコンテンツ：構文、変数、例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## オフラインマーケティング活動に使用可能なオンラインデータ

オフラインデータをオンラインにする場合、この情報をオフラインキャンペーンに使用できます。これをおこなうには、Audience Manager で、選択した [!DNL FTP] または [!DNL Amazon S3] の場所に特性およびセグメント情報を書き出します。その他の情報やサポートについては、担当のパートナーソリューションマネージャーにお問い合わせください。

## 環境

Audience Manager は、ファイルのドロップオフ用に以下の環境を提供します。

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 環境 </th> 
   <th colname="col02" class="entry"> サービス </th> 
   <th colname="col2" class="entry"> 場所 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>実稼動</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>ベータ環境</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## その他の技術情報

Systems engineers, developers, or technical/implementation teams should review [Batch Data Transfer Process Described](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process) and the other articles in this section. これらの記事には、転送プロトコル、ファイルコンテンツおよびファイル名の要件に関する詳細が記載されています。