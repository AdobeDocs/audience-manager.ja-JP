---
description: Amazon Simple Storage Service（Amazon S3）についての情報です。
seo-description: Amazon Simple Storage Service（Amazon S3）についての情報です。
seo-title: Amazon S3：概要
solution: Audience Manager
title: Amazon S3：概要
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 100%

---

# Amazon S3：概要 {#amazon-s-about}

Amazon Simple Storage Service（Amazon S3）についての情報です。

パートナーとの間でファイルのやり取りをおこなう方法としては、FTP の代わりに Amazon S3 を使用することをお勧めします。Amazon S3 が提供するシンプルな Web サービスのインターフェイスを使用することで、あらゆるサイズのデータの保存および取得が Web 上でいつでもどこでも可能になります。

Amazon S3 には次のようなメリットがあります。

* **拡張性：** Amazon S3 には、ほぼ無限の拡張性があります。
* **信頼性と可用性：** Amazon S3 は、耐久性および可用性に優れたストレージサービスを提供します。
* **スピード：** Amazon S3 は高速なデータ転送が可能です。
* **使いやすさ：** Amazon S3 は非常に使いやすく、簡単に導入できます。1 時間ほどの導入時間で稼動を開始できます。FTP ディレクトリの導入はこれよりも大幅に時間がかかります。
* **マルチパートのアップロード：**&#x200B;マルチパートのファイルアップロードで、大きなファイルを短時間で効率的にアップロードできます。
* **セキュリティ：** Amazon S3 は強力なセキュリティを備えています。

   * すべてのディレクトリは、該当する顧客またはクライアントのみがアクセスできます。
   * アップロードおよびダウンロードでは、HTTPS プロトコルがサポートされます。[!DNL Audience Manager] へのファイル転送では必ず HTTPS を使用する必要があります。
   * Amazon S3 では、[送信データファイル](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)の保存時暗号化を使用できます。アドビは暗号化方式として、Amazon S3 によって暗号キーが自動生成および管理される [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) を採用しています。

* **デバッグおよびバックアップのサポート：**[!DNL Audience Manager]Amazon S3 を使用した場合、 はファイルの正確なコピーを保持できるので、デバッグまたは再転送が容易になります。

Amazon S3 の詳細については、以下のリソースを参照してください。

[Amazon Simple Storage Service（Amazon S3）](https://aws.amazon.com/s3/)（アマゾンウェブサービスの Web サイト）

[Amazon Simple Storage Service の使用開始](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html)（AWS ドキュメントの Web サイト）
