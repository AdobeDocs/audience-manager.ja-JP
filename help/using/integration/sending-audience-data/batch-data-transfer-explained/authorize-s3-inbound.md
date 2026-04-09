---
description: 独自のAmazon S3 バケットからAudience Managerにデータを送信するには、まず専用のAmazon S3 ロールの設定をリクエストする必要があります。
solution: Audience Manager
title: インバウンドファイルに対するAmazon S3のクロスアカウントバケット権限を活用する
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
TQID: https://experienceleague.adobe.com/DR-nafoDKl-1VPK2xwq-iqpwkuTYk2nN3ywOycVJ3jM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 191
ht-degree: 0%

---

# インバウンドファイルに対するAmazon S3のクロスアカウントバケット権限を活用する {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

独自のAmazon S3 バケットからAudience Managerにデータを送信するには、まず専用のAmazon S3 ロールの設定をリクエストする必要があります。

そのためには、次の手順に従います。

1. Audience Managerにファイルを送信する別の方法については、カスタマーケアにお問い合わせください。
2. ファイルの送信に使用するAmazon S3 アカウントの役割に対して、カスタマーケアに[!DNL Amazon Resource Name (ARN)]を提供します。 _この役割は、カスタマーケアに連絡する前に作成する必要があります_。 設定が完了すると、カスタマーケアから新しく作成した役割の[!DNL Amazon Resource Name (ARN)]が提供されます。
3. 既存のAmazon S3 ロールの権限を編集して、カスタマーケアが提供するロールを引き受けます。

>[!NOTE]
>
>インバウンドデータをAudience Manager Amazon S3 バケットに転送する場合は、Audience Mangerがデータを正しく処理するために、`bucket-owner-full-control` [&#x200B; アクセス制御リスト &#x200B;](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html)を使用してください。
>
>Amazon Web Services コマンドの例：`aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`
