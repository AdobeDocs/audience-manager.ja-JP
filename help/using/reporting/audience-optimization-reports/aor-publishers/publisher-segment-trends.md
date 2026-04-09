---
description: セグメントトレンドレポートは、マッピングされたセグメントとマッピングされていないセグメントのインプレッション数およびクリックスルー率の時間的変化に関するデータを返します。マッピングされたセグメントとは、作成してターゲティングのために宛先に送信したセグメントのことです。マッピングされていないセグメントとは、作成したもののターゲティングのために宛先に送信していないセグメントのことです。選択した指標のトレンドやボリュームを比較すると、オーディエンスの行動の時間的変化を正確に把握することができます。
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-title: Segment Trend Report
solution: Audience Manager
title: セグメントトレンドレポート
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
TQID: https://experienceleague.adobe.com/EUu52qZvB-oRsIunk-ZNXxgRfdYFUmamyQ-Yk1lG-4Q
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 537
ht-degree: 100%

---

# セグメントトレンドレポート{#segment-trend-report}

セグメントトレンドレポートは、マッピングされたセグメントとマッピングされていないセグメントのインプレッション数およびクリックスルー率の時間的変化に関するデータを返します。

マッピングされたセグメントとは、作成してターゲティングのために宛先に送信したセグメントのことです。マッピングされていないセグメントとは、作成したもののターゲティングのために宛先に送信していないセグメントのことです。

選択した指標のトレンドやボリュームを比較すると、オーディエンスの行動の時間的変化を正確に把握することができます。

## ユースケース {#use-cases}

[!UICONTROL Segment Trend]レポートを使用すると、セグメントのパフォーマンスの時間的変化を確認したり、高いパフォーマンスまたはスケールに基づいてトレンドを特定したりできます。

このレポートにより、低下または誤った増加を示す Web プロパティを把握し、必要に応じてトラブルシューティングすることができます。このレポートは、関心のあるオーディエンスを[!UICONTROL Segment Performance]レポートで特定した後に実行する手順で、「[!UICONTROL Segment Performance]」タブに表示された高いパフォーマンスまたは低いパフォーマンスが時間的に一貫していることを確認できます。

## セグメントトレンドレポートの使用 {#using-the-report}

「**[!UICONTROL Mapped]**」と「**[!UICONTROL Unmapped]**」を切り替えて、宛先にマッピングされているセグメントとマッピングされていないセグメントのどちらかを選択します。「**[!UICONTROL All]**」を選択すると、すべてのセグメントがレポートに含まれます。

**[!UICONTROL Date Through]** スライダーでルックバック期間を調整します。

**[!UICONTROL Date Through]** スライダーの下で任意のセグメントをクリックすると、そのセグメントのみレポートに残す、または除外するためのオプションが表示されます。

「**[!UICONTROL Line Item]**」ドロップダウンボックスを使用して、情報を求めている、ポートフォリオ内のプロパティを選択します。

「**[!UICONTROL Segment Data Source]**」ドロップダウンボックスで、レポートに表示するセグメントが含まれているデータソースを選択します。

「**[!UICONTROL Segment]**」ドロップダウンボックスを使用して、レポートに表示するセグメントを選択します。

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers] を有効にする際には、[Google Ad Manager（旧称 DFP）データファイルを Audience Manager に読み込む](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)の手順 3 に記載されているように、[!UICONTROL Line Item] ID の記述メタデータを含める必要があります。これにより、Web プロパティの詳細が [!UICONTROL Line Item] ID ではなく [!UICONTROL Line Item] として表示されるようになります。

## 結果の解釈 {#interpreting-results}

[!UICONTROL Segment Trend]レポートには、14 日間のデータのみが線グラフで返されます。この例では、レポートには、一連のマッピングされたセグメントおよびマッピングされていないセグメントについてのインプレッションおよびクリックスルーのトレンドが表示されます。

任意の行の上にマウスポインターを置くと、その特定のセグメントトレンドに関する詳細が表示されます。追加情報については、サンプルレポートの下の表を参照してください。

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment</span> </p> </td> 
   <td colname="col2"> <p>このセグメントに割り当てた名前（英数字）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment ID</span> </p> </td> 
   <td colname="col2"> <p>このセグメントの一意な ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Line item</span> </p> </td> 
   <td colname="col2"> <p>このレポートの対象となっている Web プロパティ。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Clicks</span> </p> </td> 
   <td colname="col2"> <p>この特性のメンバーが Web プロパティ内の項目をクリックした回数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>この特性のメンバーにインベントリが表示された回数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>クリックスルー率。この指標は、クリックで遂行されたインプレッションの割合（パーセント）を示します。クリック数をインプレッション数で除算すると、この指標が得られます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment Uniques</span> </p> </td> 
   <td colname="col2"> <p>過去 30 日間のセグメントメンバーの数。 </p> </td> 
  </tr> 
 </tbody> 
</table>
