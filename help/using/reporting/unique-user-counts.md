---
description: 特性および期間が同じレポートにおける、ユニークユーザーの合計数の変動について説明します。
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: 重複レポートと一般レポートでのユニークユーザーのカウント
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '142'
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
* [ 有効期間 ](../features/traits/segment-ttl-explained.md) の値が、レポートに対して選択された時間間隔より長い。
* 過去 60 日間にユーザーがシステムでアクティブと見られる（その他の特性で絞り込まれている、ID が同期されているなど）場合。

## 一般レポート：ユニークユーザー数

一般レポートでは、選択した期間中に特性で絞り込まれているサイト訪問者を個別ユーザーとしてカウントします。

>[!MORELIKETHIS]
>
>* [インタラクティブレポート](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [一般レポート](../reporting/general-reports.md#general-reports-overview)
