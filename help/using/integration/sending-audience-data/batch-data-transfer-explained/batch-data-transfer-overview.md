---
description: 技術系／非技術系を問わず、他のシステム（オフライン）から Audience Manager にデータを取り込むお客様を対象とした概要説明です。
keywords: インバウンド、バッチ、バッチのアップロード、バッチデータ
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Audience Manager へのバッチデータ送信の概要
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 98%

---

# [!DNL Audience Manager] へのバッチデータ送信の概要  {#send-batch-data-to-audience-manager-overview}

他のシステム（オフライン）から [!DNL Audience Manager] にデータを取り込む、あらゆる技術レベルのお客様を対象とした概要説明です。

## メリット

他のシステムからのデータが [!DNL Audience Manager] で使用できるようになります。アドビのシステムは、値のロック解除および以前収集したユーザーデータの活用に役立ちます。これには、購入、顧客調査、登録データ、[!DNL CRM] データベースなどに関する情報が含まれます。統合ごとに課題がありますが、それらはすべてこれらの一般的な手順を共有します。この資料に目を通せば、オフラインデータをオンラインにするのに必要な労力を削減するうえで役に立ちます。

## 手順 1：ユーザー ID の同期

同期の際に、[!DNL Audience Manager] は一意の ID をクライアントおよびそのユーザーに割り当てます。これらの ID はそれぞれ、[!UICONTROL Data Provider ID]（[!UICONTROL DPID]）および [!UICONTROL Unique User ID]（[!UICONTROL UUID]）と呼ばれます。[!DNL Audience Manager] は、[!UICONTROL DPID] および [!UICONTROL UUID] を使用して、ユーザーを特定し [!UICONTROL traits]、[!UICONTROL segments]、オーディエンスグループおよびレポートの対象として認定します。また、アドビのデータ収集コード（[!UICONTROL DIL]）は、Web サイトからの訪問者データをキャプチャするために、これらの ID を探します。この手順が完了したら、[!DNL Audience Manager] およびオフラインリポジトリに、各ユーザーレコードに対応する ID を含める必要があります。

この手順に関する重要な考慮事項：

* **クライアント ID の配置：**[!DNL Audience Manager] は、クライアント ID が Web サイトのどこに表示されるかを把握する必要があります（例：Cookie、Analytics 変数、ページコードなどに格納されるか）。
* **[!DNL PII] の除外：**&#x200B;ユーザー ID には、個人を特定できる情報（[!DNL PII]）が含まれないようにする必要があります。
* **大文字と小文字およびコンテンツの区別：**&#x200B;リアルタイムデータ同期の間、[!DNL Audience Manager] によってサイトでキャプチャされたユーザー ID は、オフラインリポジトリから渡された ID に一致する必要があります。例えば、オフラインレコードが [!DNL User123] に関する情報を保持するが、サイトがこの ID を [!DNL USER123] としてレンダリングする場合、 は、これらを異なる訪問者と見なします。[!DNL Audience Manager]結果として、この訪問者のオンライン情報は、オフラインデータベース内の対応するレコードに関連付けることができません。ID は、正確に一致する必要があります。

[ 受信データ転送の ID 同期 ](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) を参照してください。

## 手順 2：データファイル形式

ファイル名およびコンテンツは、厳密なガイドラインに従います。このガイドのこれらの仕様に従って、データファイルの命名や編成をおこなう&#x200B;*必要があります。*&#x200B;以下を参照してください。

* [受信データファイルの Amazon S3 の名前に関する要件](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [受信データファイルの内容：構文、変数、例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## オフラインマーケティング活動に使用可能なオンラインデータ

オフラインデータをオンラインにする場合、この情報をオフラインキャンペーンに使用できます。これをおこなうため、[!DNL Audience Manager] では、選択した [!DNL FTP] または [!DNL Amazon S3] の場所に特性およびセグメント情報を書き出します。その他の情報やサポートについては、担当のパートナーソリューションマネージャーにお問い合わせください。

## 環境

[!DNL Audience Manager] は、ファイルのドロップオフ用に以下の環境を提供します。

| 環境 | サービス | 場所 |
|---------|----------|---------|
| 実稼動 | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| ベータ環境 | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## その他の技術情報

システムエンジニア、開発者、技術／実装チームは、[バッチデータ転送プロセスの説明](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)と、この節の他の記事を確認してください。これらの記事には、転送プロトコル、ファイルコンテンツおよびファイル名の要件に関する詳細が記載されています。
