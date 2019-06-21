---
description: 一括リクエストでは、更新、作成、予測および削除の各ワークシートの様々なヘッダーで使用できるデータを返します。
seo-description: 一括リクエストでは、更新、作成、予測および削除の各ワークシートの様々なヘッダーで使用できるデータを返します。
seo-title: 一括リクエスト
solution: Audience Manager
title: 一括リクエスト
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 一括要求{#bulk-requests}

一括リクエストでは、更新、作成、予測および削除の各ワークシートの様々なヘッダーで使用できるデータを返します。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. このツールはあくまで情報提供および便宜を目的として提供されています。一括変更については、代わりに [Audience Manager API](../../api/rest-api-main/aam-api-getting-started.md) を使用することを推奨します。[UIで割り当てられたRBACグループ権限](../../features/administration/administration-overview.md)[!DNL Audience Manager] は、で使用さ [!UICONTROL Bulk Management Tools]れます。

「[!UICONTROL Request]」ワークシートには独自の列ヘッダーはなく、ID を列にコピーする必要はありません。代わりに、ツールバーでクリックしたアクションボタンに基づいて、データが返されます。また、オプションのレポート機能により、ピクセル実行の頻度と、複数の固定期間での個別ユーザー数が返されます。

To make bulk requests, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Request]** tab.
2. ワークシートの上部にあるツールバーで、目的のデータに対応するリクエストボタンをクリックします。次のものをリクエストできます。

   * データプロバイダー ID
   * 派生シグナル
   * 宛先マッピング
   * ルールベースの特性とオンボードの特性
   * セグメント
   * 特性フォルダーとセグメントフォルダーの ID
   [!DNL Audience Manager] API は一括データを [!UICONTROL Request] ワークシートに書き込みます。

>[!NOTE]
>
>結果の `createTime` 列と `updateTime` 列では、データが指数表記で返されます。基になる日時スタンプは UNIX UTC 時間で記録されます。現在、このワークシートでは日時スタンプは読み取り可能な形式で返されません。

一括更新でエラーが発生した場合や失敗した場合は、[一括管理ツールのトラブルシューティング](../../reference/bulk-management-tools/bulk-troubleshooting.md)を参照してください。
