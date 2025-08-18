---
description: 独自のAmazon S3 バケットからAudience Managerにデータを送信するには、まず専用のAmazon S3 ロールの設定をリクエストする必要があります。
solution: Audience Manager
title: インバウンドファイル用にAmazon S3 のクロスアカウントバケットの権限を活用
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
source-git-commit: 65963c462f2a5abb1e2597b3d943628baa9d4730
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# インバウンドファイル用にAmazon S3 のクロスアカウントバケットの権限を活用 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

独自のAmazon S3 バケットからAudience Managerにデータを送信するには、まず専用のAmazon S3 ロールの設定をリクエストする必要があります。

これをおこなうには、以下に説明する手順に従います。

1. カスタマーケアに連絡し、別の方法でAudience Managerにファイルを送信するようリクエストしてください。
2. ファイルの送信に使用するAmazon S3 アカウントのロールの [!DNL Amazon Resource Name (ARN)] をカスタマーケアに提供します。 _この役割は、カスタマーケアに連絡する前に作成する必要があります_。 設定が完了すると、新しく作成した役割の [!DNL Amazon Resource Name (ARN)] がカスタマーケアから提供されます。
3. 既存のAmazon S3 の役割の権限を編集して、カスタマーケアが提供する役割を引き受けます。

>[!NOTE]
>
>受信データをAudience Manager Amazon S3 バケットに転送する場合は、Audience Manger がデータを正しく処理できるように、`bucket-owner-full-control`[ アクセス制御リスト ](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) を使用します。
>
>Amazon Web Services コマンドの例：`aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`
