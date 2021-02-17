---
description: オプションとして、Audience Manager に送信するデータファイルを PGP で暗号化できます。
seo-description: オプションとして、Audience Manager に送信するデータファイルを PGP で暗号化できます。
seo-title: 受信データタイプのファイル PGP 暗号化
solution: Audience Manager
title: 受信データタイプのファイル PGP 暗号化
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 100%

---


# 受信データタイプのファイル PGP 暗号化 {#file-pgp-encryption-for-inbound-data-types}

Audience Manager に送信するデータファイルを [!DNL PGP] で暗号化できます。

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] 暗号化にはファイル圧縮が含まれます。[!DNL PGP] 暗号化された受信ファイルを送信する場合は、gzip（`.gz`）による[圧縮](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)を使用しないでください。
>
>[!DNL PGP] 暗号化され、[圧縮](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)された受信ファイルは、Audience Manager では無効です。

受信データファイルを暗号化するには、以下の手順に従います。

1. [Audience Manager 公開鍵](./assets/adobe_pgp.pub)をダウンロードします。
2. 信頼されているストアに公開鍵を読み込みます。

   例えば、[!DNL GPG] を使用している場合、コマンドは次のようになります。

   `gpg --import adobe_pgp.pub`

3. 次のコマンドを実行して、鍵が正しく読み込まれたことを検証します。

   `gpg --list-keys`

   次のようなメッセージが表示されるはずです。

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. 次のコマンドを使用して、受信データを暗号化します。

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   暗号化されたすべてのデータは、`.pgp` または `.gpg` をファイル拡張子として使用する必要があります（例：`ftp_dpm_100_123456789.sync.pgp` または `ftp_dpm_100_123456789.overwrite.gpg`）。

   >[!NOTE]
   >
   >Audience Manager は、[!DNL Advanced Encryption Standard (AES)] データ暗号化アルゴリズムのみサポートしています。Audience Manager は、任意のキーサイズをサポートします。
