---
description: ワークシートでエラーが返された場合や、一括リクエストが失敗した場合の対処方法。
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: 一括管理ツールのトラブルシューティングのヒント
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
TQID: https://experienceleague.adobe.com/uWVaqQvvckobXGwoggSEgf4ePCGfInmSUIE2uicScWI
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 91%

---

# 一括管理ツールのトラブルシューティングのヒント{#troubleshooting-tips-for-bulk-management-tools}

ワークシートでエラーが返された場合や、一括リクエストが失敗した場合の対処方法。

>[!IMPORTANT]
>
>一括管理ツールは、公式にサポートされているAdobe製品ではありません。 カスタマーサポートによるトラブルシューティングおよびサポートは、ケースバイケースで対応します。

<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[!DNL Audience Manager] UI で割り当てられる [RBAC グループ権限](../../features/administration/administration-overview.md)は、[!UICONTROL Bulk Management Tools] に対しても適用されます。

大量のネットワークトラフィック、サーバーの使用状況、大規模なデータセットなどの要因により、一括リクエストが失敗したりタイムアウトすることがあります。問題がある場合、ワークシートはデータの書き込みを停止し、エラーメッセージを表示します。このような状況が発生した場合は、以下の手順に従います。

* エラーメッセージを読む。
* 問題を解決する。
* 更新済みの行をすべて削除する。
* 再度一括リクエストを試行する。

## 認証エラー、長い遅延、または応答しない動作 {#delays-behavior}

次の表は、ワークシートで一括リクエストをおこなう場合に発生する可能性がある一般的な問題のリストです。推奨される解決策により問題の解決を試してください。推奨される解決策で問題が解決しない場合、作業内容を保存し、コンピューターを再起動して、他のアプリケーションの起動や操作をおこなわずにリクエストを再度試行してください。

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題点 </th> 
   <th colname="col2" class="entry"> 解決策 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>認証エラー</b> </td> 
   <td colname="col2"> 
    <b>Microsoft Excel の最新バージョンに更新する</b>：新しいバージョンの Microsoft Excel がリリースされ、古いバージョンを使用している場合、一括管理ワークシートで認証エラーが発生する可能性があります。認証エラーを解決するには、最新バージョンの Microsoft Excel に更新してください。
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延が長い</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>互換モードを無効にする</b>：他のワークシートが Microsoft Excel の互換モードで開いていないか確認します。互換モードを使用すると実行時間が増加することがあります。このモードで開いているスプレッドシートをすべて閉じてから、一括リクエストを再試行してください。 </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>システムリソース</b>：システムリソースが限られている場合、遅延が長くなります。一括リクエストをおこなう前に、他のプログラムをすべて閉じてください。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>レスポンスがない</b> </td> 
   <td colname="col2">アクションボタンをクリックしても何も起こらない場合は、次の手順に従います。 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">選択アクションのヘッダーのセットが正しいことを確認します。 </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">コピーしたヘッダーについて正しいワークシートを使用していることを確認します。 </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">一括操作で使用するデータの位置を確認します。すべてのヘッダーは A 列 1 行目から始まります。すべてのデータは、対応するヘッダーにあわせて配置され、A 列 2 行目から始まります（ヘッダーの直下）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## エラーメッセージ

一括変更をおこなう際にエラーメッセージが表示される場合があります。エラーメッセージを解釈するには、API ドキュメントの[定義されているレスポンスコード](/help/using/api/rest-api-main/aam-api-getting-started.md)を参照してください。
