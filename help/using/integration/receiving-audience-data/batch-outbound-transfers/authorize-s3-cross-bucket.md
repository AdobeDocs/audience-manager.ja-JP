---
description: Amazon Simple Storage Service （Amazon S3）を使用しているお客様の場合、アウトバウンドのデータ転送プロセスにおいて、バケットを通してアウトバウンドデータファイルを配信するために、Amazon S3 のアクセスキーおよび秘密鍵を提供していただく必要があります。
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: 送信ファイルに Amazon S3 のクロスアカウントのバケットのアクセス許可を使用する
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
TQID: https://experienceleague.adobe.com/Ji1ltYPv4eoY5-eZiX62JyQ5SJzdMjFZdKeRzJnwKZg
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 186
ht-degree: 69%

---

# 送信ファイルに Amazon S3 のクロスアカウントのバケットのアクセス許可を使用する {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

[!DNL Amazon Simple Storage Service]（[!DNL Amazon S3]）を使用して[!UICONTROL Outbound Data Transfer]プロセスを実行する場合、送信データファイルをお客様のバケットに配信するために、お客様に [!DNL Amazon S3] のアクセスキーおよび秘密鍵を提供していただく必要があります。

[!DNL Amazon S3]のアクセスキーと秘密鍵をアドビと共有しない場合は、[!DNL Audience Manager] コンサルタントまたはカスタマーケアにお問い合わせください。お客様に[!DNL Cross-Account Bucket Permissions]を設定します。

[Amazon S3 に関するドキュメント](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)に従って、送信データファイルを受信する [!DNL S3] バケットの [!DNL Amazon S3] アカウント ID を許可リストに登録するだけで済みます。担当の [!DNL Audience Manager]コンサルタントまたはカスタマーケアがアドビの [!DNL Amazon S3] アカウント ID をお渡しします。

>[!NOTE]
>
>Amazon S3 オブジェクトサイズの制限により、Audience Managerでは最大1 TBの分割サイズをサポートしています。 分割サイズを指定しない場合、1 TBの制限が自動的に適用されます。

