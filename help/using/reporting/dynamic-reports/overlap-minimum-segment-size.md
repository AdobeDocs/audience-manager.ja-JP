---
description: 重複レポートの更新プロセスで必要なセグメントサイズと作成時間の要件について説明します。
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: 重複レポート：更新スケジュールと最小セグメントサイズ
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
TQID: https://experienceleague.adobe.com/-oG7496J-Wd8brHH2T7GWax-u9HGo7CiXmaVoiKygeQ
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6c
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 340
ht-degree: 100%

---

# 重複レポート：更新スケジュールと最小セグメントサイズ {#overlap-reports-update-schedule-and-minimum-segment-size}

重複レポートの更新プロセスで必要な特性およびセグメントサイズと作成時間の要件について説明します。

## 更新スケジュールと要件 {#update-schedule}

[!UICONTROL Overlap]レポートは毎週日曜日に更新されます。レポートの事前処理は土曜日に始まります。これにより、月曜日に新規や既存のセグメントが重複レポートにどのように表示されるかが変わります。重複レポートに記載されるには、次の条件を満たす必要があります。

* 過去 14 日間で、セグメントのリアルタイムユーザー数の合計数が 70,000 人以上でなければなりません。
* 過去 14 日間で、特性の[個別の特性満足数](/help/using/features/traits/trait-and-segment-qualification-reference.md)が 28,000 件である必要があります。
* UTC で木曜日の午後 12 時（毎週の重複レポート更新処理が開始される 2 日前）までにセグメントが作成されていなければなりません。
* 会社が完全な [!DNL Audience Manager] ユーザーである必要があります。詳しくは、[!DNL Audience Manager] コンサルタントまたはカスタマーケアにお問い合わせください。

## セグメントのサイズや作成時間によるレポートへの影響 {#segment-size}

どの[!UICONTROL Overlap]レポートにもセグメントが表示されない場合、そのセグメントが最小要件を満たしていない可能性があります。

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ユースケース </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>セグメントのサイズが小さすぎる</b> </p> </td> 
   <td colname="col2"> <p>UTC で木曜日の午後 12 時より前にセグメントを作成し、そのセグメントに含まれるリアルタイムユーザーの合計が 70,000 人より少ないとします。このセグメントは、ユーザー数のしきい値の要件を満たすまで、<span class="wintitle">重複レポート</span>に表示されません。また、セグメントは木曜日の締切時刻までにユーザー数要件を満たしていなければなりません。週の締切の時点で要件を満たしていない場合、セグメントは次の日曜日にデータを実行した後に週の<span class="wintitle">重複レポート</span>に表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>セグメントの作成が遅すぎる</b> </p> </td> 
   <td colname="col2"> <p>セグメントを金曜日に作成し、そのセグメントに含まれるリアルタイムユーザー数の合計が 70,000 人を超えているとします。このセグメントはレポート更新の 2 日前より後に作成されているので、次の週の<span class="wintitle">重複レポート</span>には表示されません。ただし、このセグメントは次の週の更新後に<span class="wintitle">重複レポート</span>に表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [特性間重複レポート](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [セグメント／特性間重複レポート](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [セグメント間重複レポート](../../reporting/dynamic-reports/segment-segment-overlap-report.md)
