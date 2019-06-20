---
description: データファイルを Audience Manager に送信する際に、オプションとして、データファイルを圧縮することができます。
seo-description: データファイルを Audience Manager に送信する際に、オプションとして、データファイルを圧縮することができます。
seo-title: インバウンドのデータ転送ファイルにおけるファイルの圧縮
solution: Audience Manager
title: インバウンドのデータ転送ファイルにおけるファイルの圧縮
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 受信データ転送ファイルのファイル圧縮{#file-compression-for-inbound-data-transfer-files}

データファイルを Audience Manager に送信する際に、オプションとして、データファイルを圧縮することができます。

<!-- inbound-file-compression.xml -->

Audience Manager では、インバウンドの非同期データ転送に対して gzip （`.gz`）形式の圧縮がサポートされています。

また、非圧縮ファイルもサポートされています。

>[!IMPORTANT]
>
>現在、同じインバウンドのデータファイルに対する暗号化および圧縮はサポートされていません。インバウンドファイルに対して、[暗号化](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)または圧縮のいずれかを選択できます。

## Amazon S3 における圧縮

[!DNL Amazon S3] に送信する場合、`.gz` または非圧縮ファイルを使用する必要があります。圧縮ファイルのサイズは 1 GB 以下である必要があります。ファイルがこれよりも大きい場合、ファイルおよび転送プロセスについてカスタマーケアと相談してください。[!DNL Audience Manager] は非常に大きなサイズのファイルを扱うことができますが、ファイルサイズを小さくしたり、データ転送を効率化したりできる方法があるかもしれません。

>[!IMPORTANT]
>
>圧縮ファイルまたは暗号化ファイルを転送する場合、[!DNL FTP] クライアントではバイナリモードを使用する必要があります。Compressed or encrypted files sent in [!DNL ASCII] mode will corrupt the data transfer file.

## ベストプラクティス

* Files should be [!DNL .gzip] compressed (and have a [!DNL .gz] file extension.)
* `.gz` 形式の圧縮ファイルの最大サイズは 1 GB です。
* ファイルを最速で処理するために最適な分割サイズは、非圧縮の場合はおよそ 1 GB、圧縮の場合は 200～300 MB です。
* [!DNL Amazon S3] では、アップロードファイルに対して独自に 5 GB のサイズ制限が課されています。