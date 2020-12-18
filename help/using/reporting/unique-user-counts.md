---
description: 特性および期間が同じレポートにおける、ユニークユーザーの合計数の変動について説明します。
seo-description: Adobe Audience Manager の特性および期間が同じレポートにおける、ユニークユーザーの合計数の変動について説明します
seo-title: AAM での重複レポートと一般レポートでのユニークユーザーのカウント
solution: Audience Manager
title: 重複レポートと一般レポートでのユニークユーザーのカウント
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: reporting reference
translation-type: ht
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: ht
source-wordcount: '171'
ht-degree: 100%

---


# 重複レポートと一般レポートでのユニークユーザーのカウント {#counting-unique-users-in-overlap-and-general-reports}

このページでは、同じ特性および期間のレポート間に見られるユニークユーザー総数の変化について説明します。

<!-- 

c_unique_user_counts.xml

 -->

## 重複レポート：ユニークユーザー数

重複レポートでは、次の場合に特性で絞り込まれているユーザーを個別ユーザーとしてカウントします。

* レポートに選択した期間。
* 特性の[有効期間](../features/traits/segment-ttl-explained.md)の値が、レポートに選択した期間より長い場合。
* 過去 60 日間にユーザーがシステムでアクティブと見られる（その他の特性で絞り込まれている、ID が同期されているなど）場合。

## 一般レポート：ユニークユーザー数

一般レポートでは、選択した期間中に特性で絞り込まれているサイト訪問者を個別ユーザーとしてカウントします。

>[!MORELIKETHIS]
>
>* [インタラクティブレポート](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [一般レポート](../reporting/general-reports.md#general-reports-overview)

