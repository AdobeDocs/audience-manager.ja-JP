---
description: Audience Manager は、毎日膨大な量のデータを受信します。これは、データの処理とレポート結果の生成にかかる時間に影響を及ぼします。この節では、これらの時間が Audience Manager アカウントに及ぼす影響について説明します。また、ここで説明している期間やスケジュールは一般的なガイドラインにすぎません。これらのスケジュールは、データ配信に関するサービス契約（SLA）や責務には含まれていません。アドビは、これらの期間やスケジュールをいつでも予告なしに変更する権利を留保します。
seo-description: Audience Manager は、毎日膨大な量のデータを受信します。これは、データの処理とレポート結果の生成にかかる時間に影響を及ぼします。この節では、これらの時間が Audience Manager アカウントに及ぼす影響について説明します。また、ここで説明している期間やスケジュールは一般的なガイドラインにすぎません。これらのスケジュールは、データ配信に関するサービス契約（SLA）や責務には含まれていません。アドビは、これらの期間やスケジュールをいつでも予告なしに変更する権利を留保します。
seo-title: データ配信やファイル処理の時間がレポートに及ぼす影響
solution: Audience Manager
title: データ配信やファイル処理の時間がレポートに及ぼす影響
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# データ配信やファイル処理の時間がレポートに及ぼす影響{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager は、毎日膨大な量のデータを受信します。これは、データの処理とレポート結果の生成にかかる時間に影響を及ぼします。この節では、これらの時間が Audience Manager アカウントに及ぼす影響について説明します。また、ここで説明している期間やスケジュールは一般的なガイドラインにすぎません。これらのスケジュールは、データ配信に関するサービス契約（SLA）や責務には含まれていません。アドビは、これらの期間やスケジュールをいつでも予告なしに変更する権利を留保します。

## レポートの数値 {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

アドビの一般的なレポートとリアルタイムレポートの期間を次の表で説明します。

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> データタイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>リアルタイムデータ</b> </p> </td> 
   <td colname="col2"> <p> 今日のリアルタイム数値は、昨日の 00:00 から 23:59:59 UTC までのものです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>一般レポートデータ</b> </p> </td> 
   <td colname="col2"> <p>Folio Builder<a href="../reporting/general-reports.md#general-reports-overview">一般レポート</a>のデータは、他のジョブ処理が正常に完了するかどうかや特定の日に受信したデータ量によって異なります。ほとんどの場合、<span class="wintitle">一般レポート</span>データは毎日 18:00 UTC に更新されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 受信および送信ファイル転送 {#inbound-outbound-file-transfers}

[!DNL Audience Manager] は、このセクションで説明したスケジュールに従って、受信および送信 [!UICONTROL Server-to-Server (S2S)] ファイル転送を処理して送信します。これらのスケジュールおよび締め切り時間を考えると、リアルタイムセグメント数と合計セグメント数で新規セグメント数が食い違う場合があります。

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファイルタイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>受信ファイル取り込み（オフラインデータ）</b> </p> </td> 
   <td colname="col2"> <p>ファイル処理は、1 日に 2 回実行されます。これらの手順では、データを取り込んで配信用に準備します。 </p> <p>処理が必要な顧客データの総量の影響を受けるので、ファイル配信時間は変わります。<span class="keyword">Audience Manager</span> でファイルがアップロードされてからデータがレポートおよびアクティブ化に使用できるようになるまで、最大 48 時間の遅延を想定してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>送信（書き出し）ファイル</b> </p> </td> 
   <td colname="col2"> <p>ファイル処理および配信は、1 日に 1 回、14:00 UTC 前後に実行されます。処理および配信は、これらのファイルの合計数およびサイズの影響を受けることに注意してください。場合によっては、ファイル処理に 24 時間の遅延が発生する可能性があります。これが発生すると、<span class="keyword">Audience Manager</span> は、特定の日に 1 つではなく 2 つのファイルを送信します。<span class="keyword">Audience Manager</span> がファイルの処理を完全に停止する必要がある稀なケースでは、アドビのお客様に通知されます。これらの条件を考慮すると、送信データの配信時間を見積もるのは困難です。 </p> <p>完全なファイルセットを受信したかどうかを判断するには、タイムスタンプを確認して、足りない日付がないかどうかを調べます。これは、ファイルの作成時刻を記録した 13 桁の UNIX UTC タイムスタンプです。詳しくは、<a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> リアルタイム送信データ転送</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [顧客データのインバウンドの取得に関するよくある質問](../faq/faq-inbound-data-ingestion.md)

