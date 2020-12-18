---
description: インバウンドのサーバー間ファイルが処理されるたびに、パートナーソリューションに対してレシートが電子メールで送信されます。また、設定によってはパートナーにも送信されます。
seo-description: インバウンドのサーバー間ファイルが処理されるたびに、パートナーソリューションに対してレシートが電子メールで送信されます。また、設定によってはパートナーにも送信されます。
seo-title: 受信処理後パートナーに送信されるメッセージの例
solution: Audience Manager
title: 受信処理後パートナーに送信されるメッセージの例
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
translation-type: ht
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: ht
source-wordcount: '661'
ht-degree: 100%

---


# 受信処理後パートナーに送信されるメッセージの例 {#sample-message-to-partners-after-inbound-processing}

インバウンドの [!UICONTROL Server-to-Server] ファイルが処理されるたびに、パートナーソリューションに対してレシートが電子メールで送信されます。また、設定によってはパートナーにも送信されます。

<!-- r_inbound_message.xml -->

次の例は、サンプルの電子メールメッセージです。メッセージの後の表は、メッセージの各行の説明です。

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>From: aam-noreply@adobe.com </b> </p> <p> <b>Subject: Adobe Audience Manager Server-To-Server Processing Result:</b> </p> <p> <b>Dear Adobe Partner: (ID:7)</b> <b></b> </p> <p> <b>We have received your Adobe Audience Manager Server-To-Server file delivery</b> </p> <p> <b>File name:</b> <i></i> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>Records received: 40669900</b> </p> <p><b>Format Errors: 0</b> </p> <p> <b>Invalid AAM ID: 112 </b> </p> <p> <b>No Matching AAM ID: 0 </b> </p> <p> <b>No Trait Realized: 26730823 </b> </p> <p> <b>Records processed: 40669900 </b> </p> <p> <b>Stored Records: 13938958 </b> </p> <p> <b>Total devices: 21 </b> </p> <p> <b>Total signals: 918878926 </b> </p> <p> <b>Total unused signals: 660348376 </b> </p> <p> <b>Total realized traits: 258086908 </b> </p> <p> <b>Total removed traits: 0 </b> </p> <p> <b>Total traits failed validation: 0 </b> </p> <p> <b>Total users that have traits which failed validation: 0 </b> </p> <p> <b>Job start time: 2018-05-17 18:07:49 </b> </p> <p> <b>Job end time: 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

次の表の各行は、受け取る電子メールメッセージの各行に対応しています。

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 行 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> File name </td> 
   <td colname="col2"> <p>このパートナーについてアドビが受け取り、一括で処理されたすべての受信ファイルのリスト。前述のサンプル電子メールメッセージでは、パートナー ID は 7 で、データ所有者 ID は 901 です。 </p> <p>末尾の番号（1、2、3、...）は、ユーザーまたは受信配布者により追加される分割番号です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Records received </td> 
   <td colname="col2"> <p>アドビがすべてのファイルで受け取ったレコードの合計数。ほとんどの場合、これは受信ファイルの行の合計数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Format Errors </td> 
   <td colname="col2"> <p>所定の形式と一致しない行の数です。これらの行は受信ジョブでは認識されていません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Invalid AAM ID </td> 
   <td colname="col2"> <p>所定の 38 桁の形式と一致しない Audience Manager UUID の数。または、ファイルで送信された Audience Manager UUID が数値ではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> No Matching AAM ID </td> 
   <td colname="col2"> <p>Audience Manager が該当する UUID を検出できなかったユーザーの合計数。これらのファイルは ID 同期されていないので、Audience Manager は UUID を参照できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> No Trait Realized </td> 
   <td colname="col2"> <p>行のシグナルがいずれも Audience Manager 特性にマッピングされていないレコードの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Records processed </td> 
   <td colname="col2"> <p>Audience Manager が処理したレコードの合計数。ほとんどの場合、この数は「Records received」と同じです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stored Records </td> 
   <td colname="col2"> <p>データが最終的にシステムにロードされたレコードの数 = Records processed - Format Errors - Invalid AAM IDs - No Matching AAM ID - No Trait Realized。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total devices </td> 
   <td colname="col2"> <p>データがシステムにロードされたデバイスの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total signals </td> 
   <td colname="col2"> <p> すべての受信ファイルでの、すべてのユーザーに対するシグナルの合計数（処理済みレコードのキーと値のペアの合計数）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total unused signals </td> 
   <td colname="col2"> <p>すべての受信ファイルでの、すべてのユーザーに対する未使用シグナルの合計数（Audience Manager 特性にマッピングされていないキーと値のペア）。ほとんどの場合、これは Audience Manager でこのシグナルに対してルールが定義されていないことを表します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total realized traits </td> 
   <td colname="col2"> <p>すべての受信ファイルでの、すべてのユーザーに対する Audience Manager 特性の数を、シグナルに基づいて算出したもの。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total removed traits </td> 
   <td colname="col2"> <p> すべての受信ファイルでの、すべてのユーザーについて削除された特性の合計数。完全同期の場合、ユーザーが前回の実行時に特性を持ち、今回の実行時に特性がなかった場合に発生します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total traits failed validation </td> 
   <td colname="col2"> <p>ファイル名で宣言されたデータソースに属していない特定の数を表します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total users that have traits which failed validation </td> 
   <td colname="col2"> <p>検証に失敗した特性が含まれていたレコードの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Job start time </td> 
   <td colname="col2"> <p>受信ジョブが開始した時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Job end time </td> 
   <td colname="col2"> <p>受信ジョブが終了した時間。 </p> </td> 
  </tr> 
 </tbody> 
</table>