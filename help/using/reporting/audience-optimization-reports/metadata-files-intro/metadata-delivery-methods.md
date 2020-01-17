---
description: メタデータファイルを送信または更新するには、メタデータファイルを Audience Manager アカウント用の特別な Amazon S3 ディレクトリに送信します。配信／ディレクトリパス、ファイル処理回数、データ更新については、この節を参照してください。
seo-description: メタデータファイルを送信または更新するには、メタデータファイルを Audience Manager アカウント用の特別な Amazon S3 ディレクトリに送信します。配信／ディレクトリパス、ファイル処理回数、データ更新については、この節を参照してください。
seo-title: メタデータファイルの配信方法
solution: Audience Manager
title: メタデータファイルの配信方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: de51f27cac0d165d043e90db978a6949d6a43761

---


# メタデータファイルの配信方法{#delivery-methods-for-metadata-files}

Send or update metadata files by sending them to a special [!DNL Amazon S3] directory for your Audience Manager account. 配信／ディレクトリパス、ファイル処理回数、データ更新については、この節を参照してください。

## Delivery Path Syntax and Example {#syntax}

Data is stored in separate namespace for each customer in an [!DNL Amazon S3] directory. ファイルパスは以下の構文に従います。注意：山括弧は可変プ `<>` レースホルダーを示します。 その他の要素は定数で、変動しません。

**構文：**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**例：**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

ファイル配信パスのこれらの各要素を次の表で定義します。


| ファイルパラメーター | 説明 |
---------|----------|
| `.../log_ingestion/` | ストレージのディレクトリパスの先頭。セットアップがすべて完了したら、完全パスが与えられます。 |
| `pid=<AAM ID>` | このキーと値のペアには、Audience Managerの顧客IDが含まれます。 |
| `dpid=<d_src>` | イベント呼び出し時に渡されるデータソース ID のキー値ペア。データソース ID は、ファイル内のすべてのコンテンツを、そのコンテンツが属する実際のデータに関連付ける値です。</br>例えば、ID が 123 で名前が「Advertiser Creative A」であるクリエイティブがあるとします。イベントの呼び出しでは ID しか渡されないので、メタデータファイルに「Advertiser Creative A」を入れる必要があります。キャンペーンとクリエイティブはデータソースに属しています。データソース ID はこれらをまとめるもので、これによりイベント呼び出しで送信される ID にファイルのコンテンツを正確に関連付けることができます。[イベント呼び出し ID によるファイル名、コンテンツ、配信パスの決定方法](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-filenames)を参照してください。 |
| `<yyyymmdd_0_child ID>` | ファイル名です。詳しくは、[メタデータファイルの命名規則](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)を参照してください。 |

## ファイル処理の回数と更新 {#processing-times}

メタデータファイルは 1 日 4 回、等間隔で処理されます。

メタデータレコードを更新するには、新しい情報が含まれるファイルを送信します。毎回すべての更新を送信する必要はありません。
