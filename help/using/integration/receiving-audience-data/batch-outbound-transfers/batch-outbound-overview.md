---
description: Audience Manager では、これらの仕様に従って、バッチデータをサードパーティコンテンツプロバイダーに送信します。
seo-description: Adobe Audience Manager（AAM）では、これらの仕様に従って、バッチデータをサードパーティコンテンツプロバイダーに送信します。
seo-title: Adobe Audience Manager（AAM）でのバッチ送信データ転送
title: バッチ送信データ転送
feature: 送信データ転送
exl-id: 1fdcc971-3a71-4033-8501-ef3d1f1f0f47
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 98%

---

# バッチ送信データ転送

Audience Manager では、これらの仕様に従って、バッチデータをサードパーティコンテンツプロバイダーに送信します。

* [送信データファイル名：構文と例 ](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

   送信データファイルの名前に使用される必須フィールド、構文および規則について説明します。

* [バッチデータ転送統合の設定](batch-server-configuration.md)

   バッチデータ転送統合の設定方法について説明します。

* [ログファイル転送のための転送制御ファイル](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

   転送制御（.info）ファイルは、ファイル転送に関するメタデータ情報を提供するので、パートナーは、Audience Manager がファイル転送を正しく処理したことを検証できます。

* [送信テンプレートマクロ](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

   送信テンプレートの作成に使用できるマクロの一覧を示します。ファイル名マクロ、ヘッダーマクロ、コンテンツマクロなどがあります。

* [送信マクロの例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

   送信ファイルテンプレートの作成に、一部の一般的なマクロがどのように使用されるかを示す例です。

* [送信ファイルに Amazon S3 のクロスアカウントのバケットのアクセス許可を使用する](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

   Amazon Simple Storage Service （Amazon S3）を使用しているお客様の場合、アウトバウンドのデータ転送プロセスにおいて、バケットを通してアウトバウンドデータファイルを配信するために、Amazon S3 のアクセスキーおよび秘密鍵を提供していただく必要があります。
