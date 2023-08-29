---
description: 独自のAmazon S3 バケットからAudience Managerにデータを送信するには、まず専用のAmazon S3 ロールの設定をリクエストする必要があります。
solution: Audience Manager
title: 受信ファイルにAmazon S3 のクロスアカウントのバケットのアクセス許可を使用する
feature: Inbound Data Transfers
source-git-commit: 17cee6971ca1d5cda8f272558a46220227fc51f7
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# 受信ファイルにAmazon S3 のクロスアカウントのバケットのアクセス許可を使用する {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

独自のAmazon S3 バケットからAudience Managerにデータを送信するには、まず専用のAmazon S3 ロールの設定をリクエストする必要があります。

これをおこなうには、次の手順に従います。

1. カスタマーケアに問い合わせ、ファイルをAudience Managerに送信する代替方法をリクエストします。
2. カスタマーケアに [!DNL Amazon Resource Name (ARN)] ファイルの送信に使用するAmazon S3 アカウントの役割用。 _このロールは、カスタマーケアに連絡する前に作成する必要があります_. 設定が完了すると、カスタマーケアから [!DNL Amazon Resource Name (ARN)] 新しく作成された役割用。
3. 既存のAmazon S3 の役割の権限を編集して、カスタマーケアが提供する役割を引き受けます。

>[!NOTE]
>
>受信データをAudience ManagerAmazon S3 バケットに転送する場合は、必ず `bucket-owner-full-control` [アクセス制御リスト](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) Audience Manager でデータを正しく処理するために使用されます。
>
>Amazon Web Servicesコマンドの例： `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`

