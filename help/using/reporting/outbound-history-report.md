---
description: 指定した宛先と期間について、アウトバウンドの一括ジョブの履歴情報を表示できます。
seo-description: 指定した宛先と期間について、アウトバウンドの一括ジョブの履歴情報を表示できます。
seo-title: 送信ファイル履歴
solution: Audience Manager
title: 送信ファイル履歴
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: インバウンドレポートとアウトバウンドレポート
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 100%

---

# 送信ファイル履歴 {#outbound-file-history}

指定した宛先と期間について、アウトバウンドの一括ジョブの履歴情報を表示できます。

<!-- 

t_reports_outbound_history.xml

 -->

1. **[!UICONTROL Analytics]**／**[!UICONTROL Outbound File History]** をクリックします。

   ![手順の結果](assets/outbound_history.png)

1. 「**[!UICONTROL Search for a Destination]**」ボックスで、入力を開始し、目的の宛先を選択します。
1. 「**[!UICONTROL Select a Date Range]**」ボックスで、レポートの開始日と終了日を指定し、「**[!UICONTROL Apply Date Filter]**」をクリックします。

   ![手順の結果](assets/outbound_history_stats.png)

   次の表は、レポートの各列に関する情報です。

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 行 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Data Sync File Name </td> 
   <td colname="col2"> <p>この宛先について<span class="keyword">アドビ</span>が生成し、一括で処理されたすべてのアウトバウンドファイルのリスト。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Successful </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> から宛先への送信が成功したレコードの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Failed </td> 
   <td colname="col2"> <p>宛先に送信できなかったレコードの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Records Received </td> 
   <td colname="col2"> <p><span class="keyword">アドビ</span>がファイルに生成し、宛先への送信を試行したレコードの合計数。ほとんどの場合、この値は成功したファイルと失敗したファイルの合計数です。 </p> </td> 
  </tr> 
 </tbody> 
</table>
