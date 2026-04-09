---
description: 一括リクエストでは、更新、作成、推定および削除の各ワークシートの様々なヘッダーで使用できるデータを返します。
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: 一括リクエスト
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
TQID: https://experienceleague.adobe.com/9VACsTAdf5nqwXAeQCqA7ME7M1sTOwt-eW-fyVdE-Ag
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6cid: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 253
ht-degree: 89%

---

# 一括リクエスト{#bulk-requests}

一括リクエストでは、更新、作成、推定および削除の各ワークシートの様々なヘッダーで使用できるデータを返します。

>[!IMPORTANT]
>
>一括管理ツールは、公式にサポートされているAdobe製品ではありません。 カスタマーサポートによるトラブルシューティングおよびサポートは、ケースバイケースで対応します。

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
