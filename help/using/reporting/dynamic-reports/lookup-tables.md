---
description: 配信パフォーマンスレポートログファイルのデータを、ID のみを含むテーブルに格納します。ID 以外のメタデータを別個のルックアップテーブルに格納すると、ファイルサイズの縮小と処理時間の短縮に役立ちます。
seo-description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-title: Improve Log File Processing Times with Lookup Tables
solution: Audience Manager
title: ルックアップテーブルによるログファイル処理時間の改善
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
TQID: https://experienceleague.adobe.com/9eLSmpl5-daNV5NgXrPfLThoIlMibaOtbgrsuqfkeCI
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6cid: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 100%

---

# ルックアップテーブルによるログファイル処理時間の改善{#improve-log-file-processing-times-with-lookup-tables}

配信パフォーマンスレポートログファイルのデータを、ID のみを含むテーブルに格納します。ID 以外のメタデータを別個のルックアップテーブルに格納すると、ファイルサイズの縮小と処理時間の短縮に役立ちます。

<!-- 

c_lookup_tables.xml

 -->

## ログファイルメタデータによるファイルサイズおよび処理時間の増加

[!UICONTROL Delivery Performance]レポートで使用される典型的なログファイルには、通常、何万もの行と数十の列が含まれています。数値 ID および人間が判読できる情報（クリエイティブの名前、広告主、広告掲載の申し込みなど）で構成されます。

この ID 以外の情報は、*`metadata`*（例：他の情報に関する情報）と呼ばれ、ログファイルの各行に書き込まれます。

ただし、[!UICONTROL Delivery Performance]配レポートでは、主にログファイルの ID を使用します。メタデータは有用ですが、同じ情報を繰り返します。また、ファイルサイズおよびデータの取り込み時間が増えます。

## インデックステーブルを使用したファイルサイズの削減と処理時間の短縮

パフォーマンスの向上に役立てるには、メインのデータファイルには ID のみが含まれるようにする必要があります。メタデータを別個のルックアップ（またはインデックス）テーブルに格納し、これらのレコードを両方に共通するキー変数でメインファイルにリンクします。

## ルックアップテーブルによるファイルサイズの削減方法

以下に示すようなデータファイルがあるとします。

| ユーザー ID | 広告 ID | 広告名 | 注文 ID | 注文名 | 広告主 ID | 広告主名 |
|---|---|---|---|---|---|---|
| 1 | 111 | 靴 A | 456 | スニーカー | 27 | 会社 A |
| 2 | 111 | 靴 A | 456 | スニーカー | 27 | 会社 A |
| 3 | 111 | 靴 A | 456 | スニーカー | 27 | 会社 A |
| 4 | 222 | 靴 B | 789 | ハイキング | 14 | 会社 B |
| 5 | 222 | 靴 B | 789 | ハイキング | 14 | 会社 B |

<br> 

次に、メタデータが削除された同じログファイルを示します。ID のみで構成されると、ファイルは小さくなり、処理しやすくなります。

| ユーザー ID | 広告 ID | 注文 ID | 広告主 ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br>

以下のルックアップファイルにはメタデータが含まれており、広告 ID でメインファイルにリンクし直すことができます。サイズにも注意してください。各広告主を複数回繰り返す代わりに、それぞれに 1 つの参照のみが必要です。

| 広告 ID | 広告名 | 注文名 | 広告主名 |
|---|---|---|---|
| 111 | 靴 A | スニーカー | 会社 A |
| 222 | 靴 B | ハイキング | 会社 B |

## ルックアップテーブルを不要にする API

広告配信システムに API が用意されている場合は、ルックアップファイルにメタデータを送信する必要がない可能性があります。その情報を API を使用して取得できる可能性があります。この場合、ログファイルには ID のみを含める必要があります。アドビはお客様と協力して、API を使用してメタデータを取得できるかどうかを判断します。
