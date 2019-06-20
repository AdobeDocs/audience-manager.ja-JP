---
description: Audience Manager では、これらの仕様に従って、バッチデータをサードパーティコンテンツプロバイダーに送信します。
seo-description: Adobe Audience Manager（AAM）は、これらの仕様に従って、バッチデータをサードパーティのコンテンツプロバイダーに送信します。
seo-title: Adobe Audience Manager（AAM）でのバッチアウトバウンドデータ転送
title: バッチ送信データ転送
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# バッチ送信データ転送

Audience Manager では、これらの仕様に従って、バッチデータをサードパーティコンテンツプロバイダーに送信します。

* [送信データファイル名：構文と例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

   送信データファイルの名前に使用される必須フィールド、構文および規則について説明します。

* [ログファイル転送のための転送制御ファイル](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

   転送制御（.info）ファイルは、ファイル転送に関するメタデータ情報を提供するので、パートナーは、Audience Manager がファイル転送を正しく処理したことを検証できます。

* [アウトバウンドテンプレートマクロ](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

   送信テンプレートの作成に使用できるマクロの一覧を示します。ファイル名マクロ、ヘッダーマクロ、コンテンツマクロなどがあります。

* [アウトバウンドマクロの例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

   送信ファイルテンプレートの作成に、一部の一般的なマクロがどのように使用されるかを示す例です。

* [アウトバウンドファイルに Amazon S3 のクロスアカウントのバケットのアクセス許可を使用する](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

   お客様が Amazon Simple Storage Service（Amazon S3）を使用して送信データ転送プロセスを実行する場合、送信データファイルをお客様のバケットに配信するために、お客様に Amazon S3 アクセスキーおよびシークレットキーを提供していただく必要があります。
