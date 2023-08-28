---
description: Amazon Simple Storage Service （Amazon S3）を使用しているお客様の場合、アウトバウンドのデータ転送プロセスにおいて、バケットを通してアウトバウンドデータファイルを配信するために、Amazon S3 のアクセスキーおよび秘密鍵を提供していただく必要があります。
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: 送信ファイルに Amazon S3 のクロスアカウントのバケットのアクセス許可を使用する
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 7302fafa537ad15144a64cc96f7150c5b0233c12
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 100%

---

# 送信ファイルに Amazon S3 のクロスアカウントのバケットのアクセス許可を使用する {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

[!DNL Amazon Simple Storage Service]（[!DNL Amazon S3]）を使用して[!UICONTROL Outbound Data Transfer]プロセスを実行する場合、送信データファイルをお客様のバケットに配信するために、お客様に [!DNL Amazon S3] のアクセスキーおよび秘密鍵を提供していただく必要があります。

[!DNL Amazon S3] のアクセスキーおよび秘密鍵の提供を希望されない場合、[!DNL Audience Manager] の担当コンサルタントまたはカスタマーケアにお問い合わせください。お客様に代わって [!DNL Cross-Account Bucket Permissions]のセットアップをおこないます。

[Amazon S3 に関するドキュメント](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)に従って、送信データファイルを受信する [!DNL S3] バケットの [!DNL Amazon S3] アカウント ID を許可リストに登録するだけで済みます。担当の [!DNL Audience Manager]コンサルタントまたはカスタマーケアがアドビの [!DNL Amazon S3] アカウント ID をお渡しします。
