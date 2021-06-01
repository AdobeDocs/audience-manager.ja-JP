---
description: データファイルを Audience Manager に送信する際に、オプションとして、データファイルを圧縮することができます。
seo-description: データファイルを Audience Manager に送信する際に、オプションとして、データファイルを圧縮することができます。
seo-title: 受信データ転送ファイルのファイル圧縮
solution: Audience Manager
title: 受信データ転送ファイルのファイル圧縮
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: 受信データ転送
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 100%

---

# 受信データ転送ファイルのファイル圧縮 {#file-compression-for-inbound-data-transfer-files}

データファイルを Audience Manager に送信する際に、データファイルを圧縮することができます。

<!-- inbound-file-compression.xml -->

Audience Manager では、インバウンドの非同期データ転送に対して gzip （`.gz`）形式の圧縮がサポートされています。

また、非圧縮ファイルもサポートされています。

>[!IMPORTANT]
>
>gzip（`.gz`）を使用して圧縮された受信ファイルの暗号化はサポートされません。
>
>受信ファイルを暗号化および圧縮するには、[PGP 暗号化](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)を使用してください。[!DNL PGP] 暗号化にはファイル圧縮が含まれます。

## Amazon S3 における圧縮

[!DNL Amazon S3] に送信する場合、`.gz` または非圧縮ファイルを使用する必要があります。圧縮ファイルのサイズは 1 GB 以下である必要があります。ファイルがこれよりも大きい場合、ファイルおよび転送プロセスについてカスタマーケアと相談してください。[!DNL Audience Manager] は非常に大きなサイズのファイルを扱うことができますが、ファイルサイズを小さくしたり、データ転送を効率化したりできる方法があるかもしれません。

>[!IMPORTANT]
>
>圧縮ファイルまたは暗号化ファイルを転送する場合、[!DNL FTP] クライアントではバイナリモードを使用する必要があります。圧縮ファイルまたは暗号化ファイルを [!DNL ASCII] モードで送信した場合、データ転送ファイルが破損します。

## ベストプラクティス

* ファイルは [!DNL .gzip] 形式で圧縮してください（また、ファイルの拡張子を [!DNL .gz] にする）。
* `.gz` 形式の圧縮ファイルの最大サイズは 1 GB です。
* ファイルを最速で処理するために最適な分割サイズは、非圧縮の場合はおよそ 1 GB、圧縮の場合は 200～300 MB です。
* [!DNL Amazon S3] では、アップロードファイルに対して独自に 5 GB のサイズ制限が課されています。
