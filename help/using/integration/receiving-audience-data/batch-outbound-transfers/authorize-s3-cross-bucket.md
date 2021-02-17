---
description: Amazon Simple Storage Service （Amazon S3）を使用しているお客様の場合、アウトバウンドのデータ転送プロセスにおいて、バケットを通してアウトバウンドデータファイルを配信するために、Amazon S3 のアクセスキーおよび秘密鍵を提供していただく必要があります。
seo-description: Amazon Simple Storage Service （Amazon S3）を使用しているお客様の場合、アウトバウンドのデータ転送プロセスにおいて、バケットを通してアウトバウンドデータファイルを配信するために、Amazon S3 のアクセスキーおよび秘密鍵を提供していただく必要があります。
seo-title: 送信ファイルに Amazon S3 のクロスアカウントのバケットのアクセス許可を使用する
solution: Audience Manager
title: 送信ファイルに Amazon S3 のクロスアカウントのバケットのアクセス許可を使用する
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 100%

---


# 送信ファイルに Amazon S3 のクロスアカウントのバケットのアクセス許可を使用する {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

[!DNL Amazon Simple Storage Service]（[!DNL Amazon S3]）を使用して[!UICONTROL Outbound Data Transfer]プロセスを実行する場合、送信データファイルをお客様のバケットに配信するために、お客様に [!DNL Amazon S3] のアクセスキーおよび秘密鍵を提供していただく必要があります。

[!DNL Amazon S3] のアクセスキーおよび秘密鍵の提供を希望されない場合、[!DNL Audience Manager] の担当コンサルタントまたはカスタマーケアにお問い合わせください。お客様に代わって [!DNL Cross-Account Bucket Permissions]のセットアップをおこないます。[Amazon S3 に関するドキュメント](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)に従って、送信データファイルを受信する [!DNL S3] バケットの [!DNL Amazon S3] アカウント ID を許可リストに登録するだけで済みます。担当の [!DNL Audience Manager]コンサルタントまたはカスタマーケアがアドビの [!DNL Amazon S3] アカウント ID をお渡しします。