---
description: Audience Manager は、毎日膨大な量のデータを受信します。これは、データの処理とレポート結果の生成にかかる時間に影響を及ぼします。この節では、これらの時間が Audience Manager アカウントに及ぼす影響について説明します。また、ここで説明している期間やスケジュールは一般的なガイドラインにすぎません。これらのスケジュールは、データ配信に関するサービス契約（SLA）や責務には含まれていません。アドビは、これらの期間やスケジュールをいつでも予告なしに変更する権利を留保します。
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: データ配信やファイル処理の時間がレポートに及ぼす影響
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 92%

---

# データ配信やファイル処理の時間がレポートに及ぼす影響{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager は、毎日膨大な量のデータを受信します。これは、データの処理とレポート結果の生成にかかる時間に影響を及ぼします。この節では、これらの時間が Audience Manager アカウントに及ぼす影響について説明します。また、ここで説明している期間やスケジュールは一般的なガイドラインにすぎません。これらのスケジュールは、データ配信に関するサービス契約（SLA）や責務には含まれていません。アドビは、これらの期間やスケジュールをいつでも予告なしに変更する権利を留保します。

## レポートの数値 {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

アドビの一般的なレポートとリアルタイムレポートの期間を次の表で説明します。


| データタイプ | 説明 |
|---|---|
| リアルタイムデータ | 今日のリアルタイム数は、昨日の 00:00 ～ 23:59:59 UTC の時間です。 |
| 一般レポートデータ | [一般レポート](../reporting/general-reports.md#general-reports-overview)のデータは、他のジョブ処理が正常に完了するかどうかや特定の日に受信したデータ量によって異なります。ほとんどの場合、データ [!UICONTROL General Report] 毎日 18:00 UTC で更新される必要があります。 |

## 受信および送信ファイル転送 {#inbound-outbound-file-transfers}

[!DNL Audience Manager] は、このセクションで説明したスケジュールに従って、受信および送信 [!UICONTROL Server-to-Server (S2S)] ファイル転送を処理して送信します。これらのスケジュールおよび締め切り時間を考えると、リアルタイムセグメント数と合計セグメント数で新規セグメント数が食い違う場合があります。

| ファイルタイプ | 説明 |
|---|---|
| 受信ファイル取り込み（オフラインデータ） | ファイル処理は、1 日に 2 回実行されます。これらの手順では、データを取り込んで配信用に準備します。処理が必要な顧客データの総量の影響を受けるので、ファイル配信時間は変わります。Audience Manager でファイルがアップロードされてからデータがレポートおよびアクティブ化に使用できるようになるまで、最大 48 時間の遅延を想定してください。 |
| 送信（書き出し）ファイル | ファイルの処理と配信は、1 日に 1 回、約 14:00 （UTC）に行われます。 処理および配信は、これらのファイルの合計数およびサイズの影響を受けることに注意してください。場合によっては、ファイル処理に 24 時間の遅延が発生する可能性があります。これが発生すると、Audience Manager は、特定の日に 1 つではなく 2 つのファイルを送信します。Audience Manager がファイルの処理を完全に停止する必要がある稀なケースでは、アドビのお客様に通知されます。これらの条件を考慮すると、送信データの配信時間を見積もるのは困難です。完全なファイルセットを受信したかどうかを判断するには、タイムスタンプを確認して、足りない日付がないかどうかを調べます。これは、ファイルの作成時刻を記録した 13 桁の UNIX UTC タイムスタンプです。[&#x200B; リアルタイム送信データ転送 &#x200B;](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md) を参照してください。 |
| 広告サーバーログファイル | ファイル処理はほぼリアルタイムで実行され、時間別ファイルの準備が整った時点で、ログファイルレコードを取り込みます。ファイルのレポート準備プロセスは、1 日 1 回実行されます。処理が必要な顧客データの総量の影響を受けるので、ファイル配信時間は変わります。Audience Manager でファイルがアップロードされてからデータがレポートおよびアクティブ化に使用できるようになるまで、最大 48 時間の遅延を想定してください。 |

>[!MORELIKETHIS]
>
>* [顧客データのインバウンドの取得に関するよくある質問](../faq/faq-inbound-data-ingestion.md)
