---
description: 転送制御（.info）ファイルは、ファイル転送に関するメタデータ情報を提供するので、パートナーは、Audience Manager がファイル転送を正しく処理したことを検証できます。
seo-description: 転送制御（.info）ファイルは、ファイル転送に関するメタデータ情報を提供するので、パートナーは、Audience Manager がファイル転送を正しく処理したことを検証できます。
seo-title: ログファイル転送のための転送制御ファイル
solution: Audience Manager
title: ログファイル転送のための転送制御ファイル
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
translation-type: ht
source-git-commit: 033057e080a72c82ec8ff9233e199d5e204a622c
workflow-type: ht
source-wordcount: '307'
ht-degree: 100%

---


# ログファイル転送のための転送制御ファイル {#transfer-control-files-for-log-file-transfers}

転送制御（[!DNL .info]）ファイルは、ファイル転送に関するメタデータ情報を提供するので、パートナーは、Audience Manager がファイル転送を正しく処理したことを検証できます。

[!DNL Audience Manager] は、ファイル転送ごとに転送制御ファイルをパートナーに送信します。[!DNL FTP] パブリッシャーのマルチスレッド性により、転送制御ファイルは、実際のファイルの転送が完了する前に送信される可能性があります。

[!DNL .info] ファイルのメタデータを使用すると、パートナーは以下のことができます。

* 完全転送サイクルが完了する（シーケンス内のすべてのファイルが配信された）タイミングを判断する。
* シーケンス内の特定のファイルが完成／修正された場所を（ファイルのサイズ（バイト）および合計行数を調査することで）判断する。
* 生ファイルの行数とファイルが受信側のデータベースに読み込まれた後の行数（ファイルのサイズ（行数））を比較して検証する。

## ファイル命名規則 {#file-naming-conventions}

転送制御ファイルには、バッチ／シーケンスのルートと同じ名前で、[!DNL .info] ファイル拡張子が付きます。

例えば、シーケンスの最初のファイルの名前が [!DNL ftp_12345_67890_full_1500727351632-1.sync] の場合、制御ファイルの名前は [!DNL ftp_12345_67890_iter_1500727351632.info] になります。

## ファイル形式 {#file-format}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

>[!NOTE]
>
> バッチの合計数からは、[!DNL .info] ファイル自体は除外されます。つまり、合計数には、[!DNL .info] ファイル、そのバイトサイズまたは行数は含まれません。
>
> ファイルのバイトサイズおよび行数には、ヘッダーおよびスペーサー（空白）の行数が含まれます。実際のデータの行数をカウントするためには、ヘッダー分を減算します。
>
> バッチの合計行数および合計バイトサイズには、ヘッダーおよびスペース行が含まれます。