---
description: 特性および期間が同じレポートにおける、ユニークユーザーの合計数の変動について説明します。
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: 重複レポートと一般レポートでのユニークユーザーのカウント
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
TQID: https://experienceleague.adobe.com/zQamEx1r5buK4Q4FN-meT3l-8-j3f9Q5Kw2RtO0iPQ8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 90%

---

# 重複レポートと一般レポートでのユニークユーザーのカウント{#counting-unique-users-in-overlap-and-general-reports}

このページでは、同じ特性および期間のレポート間に見られるユニークユーザー総数の変化について説明します。

<!-- 

c_unique_user_counts.xml

 -->

## 重複レポート：ユニークユーザー数

重複レポートでは、次の場合に特性で絞り込まれているユーザーをユニークユーザーとしてカウントします。

* レポートに選択した期間。
* これには、レポートで選択した時間間隔よりも長い[有効期間](../features/traits/segment-ttl-explained.md)の値があります。
* 過去 60 日間にユーザーがシステムでアクティブと見られる（その他の特性で絞り込まれている、ID が同期されているなど）場合。

## 一般レポート：ユニークユーザー数

一般レポートでは、選択した期間中に特性で絞り込まれているサイト訪問者を個別ユーザーとしてカウントします。

>[!MORELIKETHIS]
>
>* [インタラクティブレポート](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [一般レポート](../reporting/general-reports.md#general-reports-overview)
