---
description: 技術系／非技術系を問わず、他のシステム（オフライン）から Audience Manager にデータを取り込むお客様を対象とした概要説明です。
keywords: inbound, batch, batch upload, batch data
seo-description: 技術系／非技術系を問わず、他のシステム（オフライン）から Audience Manager にデータを取り込むお客様を対象とした概要説明です。これをおこなうには、Audience Manager のバッチアップロードオプションを使用します。
seo-title: Audience Manager へのバッチデータ送信の概要
solution: Audience Manager
title: Audience Manager へのバッチデータ送信の概要
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 80%

---


# Send Batch Data to [!DNL Audience Manager] Overview {#send-batch-data-to-audience-manager-overview}

An overview for technical and non-technical customers who want to bring data from other systems (offline) into [!DNL Audience Manager].

## メリット

You can make data from other systems available in [!DNL Audience Manager]. アドビのシステムは、値のロック解除および以前収集したユーザーデータの活用に役立ちます。これには、購入、顧客調査、登録データ、[!DNL CRM] データベースなどに関する情報が含まれます。統合ごとに課題がありますが、それらはすべてこれらの一般的な手順を共有します。この資料に目を通せば、オフラインデータをオンラインにするのに必要な労力を削減するうえで役に立ちます。

## 手順 1：ユーザー ID の同期

During synchronization, [!DNL Audience Manager] assigns unique IDs to clients and their users. これらの ID はそれぞれ、[!UICONTROL Data Provider ID]（[!UICONTROL DPID]）および [!UICONTROL Unique User ID]（[!UICONTROL UUID]）と呼ばれます。[!DNL Audience Manager] と [!UICONTROL DPID] を使用してユーザーを識別し、そ [!UICONTROL UUID] れらを [!UICONTROL traits]、 [!UICONTROL segments]、オーディエンスグループ、およびレポートの対象とします。 また、アドビのデータ収集コード（[!UICONTROL DIL]）は、Web サイトからの訪問者データをキャプチャするために、これらの ID を探します。When this step is complete, [!DNL Audience Manager] and your offline repository should contain corresponding IDs for each user record.

この手順に関する重要な考慮事項：

* **クライアント ID の配置：**[!DNL Audience Manager] は、クライアント ID が Web サイトのどこに表示されるかを把握する必要があります（例：Cookie、Analytics 変数、ページコードなどに格納されるか）。
* **[!DNL PII] の除外：**&#x200B;ユーザー ID には、個人を特定できる情報（[!DNL PII]）が含まれないようにする必要があります。
* **大文字と小文字およびコンテンツの区別：**[!DNL Audience Manager]リアルタイムデータ同期の間、 によってサイトでキャプチャされたユーザー ID は、オフラインリポジトリから渡された ID に一致する必要があります。例えば、オフラインレコードが [!DNL User123] に関する情報を保持するが、サイトがこの ID を [!DNL USER123] としてレンダリングする場合、 は、これらを異なる訪問者と見なします。[!DNL Audience Manager]結果として、この訪問者のオンライン情報は、オフラインデータベース内の対応するレコードに関連付けることができません。ID は、正確に一致する必要があります。

詳しくは、[受信データ転送のための ID 同期](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)を参照してください。

## 手順 2：データファイル形式

ファイル名およびコンテンツは、厳密なガイドラインに従います。このガイドのこれらの仕様に従って、データファイルの命名や編成をおこなう&#x200B;*必要があります。*&#x200B;以下を参照してください。

* [受信データファイルの Amazon S3 の名前に関する要件](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [ 受信データファイルコンテンツ：構文、変数、例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## オフラインマーケティング活動に使用可能なオンラインデータ

オフラインデータをオンラインにする場合、この情報をオフラインキャンペーンに使用できます。To do this, [!DNL Audience Manager] exports trait and segment information to an [!DNL FTP] or [!DNL Amazon S3] location of your choice. その他の情報やサポートについては、担当のパートナーソリューションマネージャーにお問い合わせください。

## 環境

[!DNL Audience Manager] ファイルのドロップオフに次の環境を使用できます。

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

システムエンジニア、開発者、技術／実装チームは、[バッチデータ転送プロセスの説明](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)と、この節の他の記事を確認してください。これらの記事には、転送プロトコル、ファイルコンテンツおよびファイル名の要件に関する詳細が記載されています。
