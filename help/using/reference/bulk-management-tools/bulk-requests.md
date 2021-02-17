---
description: 一括リクエストでは、更新、作成、推定および削除の各ワークシートの様々なヘッダーで使用できるデータを返します。
seo-description: 一括リクエストでは、更新、作成、推定および削除の各ワークシートの様々なヘッダーで使用できるデータを返します。
seo-title: 一括リクエスト
solution: Audience Manager
title: 一括リクエスト
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 100%

---


# 一括リクエスト {#bulk-requests}

一括リクエストでは、更新、作成、推定および削除の各ワークシートの様々なヘッダーで使用できるデータを返します。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[!DNL Audience Manager] UI で割り当てられる [RBAC グループ権限](../../features/administration/administration-overview.md)は、[!UICONTROL Bulk Management Tools] に対しても適用されます。

[!UICONTROL Request] ワークシートには独自の列ヘッダーはなく、ID を列にコピーする必要はありません。代わりに、ツールバーでクリックしたアクションボタンに基づいて、データが返されます。また、オプションのレポート機能により、ピクセル実行の頻度と、複数の固定期間でのユニークユーザー数が返されます。

一括リクエストをおこなうには、[!UICONTROL Bulk Management Tools] ワークシートを開き、以下の手順に従ってください。

1. 「**[!UICONTROL Request]**」タブをクリックします。
2. ワークシートの上部にあるツールバーで、目的のデータに対応するリクエストボタンをクリックします。次のものをリクエストできます。

   * アルゴリズムモデル
   * データソース
   * 派生シグナル
   * 宛先マッピング
   * アルゴリズムを使用した、ルールベースの特性とオンボードの特性
   * セグメント
   * 特性フォルダーとセグメントフォルダーの ID

   [!DNL Audience Manager] API は一括データを [!UICONTROL Request] ワークシートに書き込みます。

>[!NOTE]
>
>結果の `createTime` 列と `updateTime` 列では、データが指数表記で返されます。基になる日時スタンプは UNIX UTC 時間で記録されます。現在、このワークシートでは日時スタンプは読み取り可能な形式で返されません。

一括更新でエラーが発生した場合や失敗した場合は、[一括管理ツールのトラブルシューティング](../../reference/bulk-management-tools/bulk-troubleshooting.md)を参照してください。
