---
description: 一括更新では、複数のセグメント、特性、およびセグメントフォルダーまたは特性フォルダーの要素を 1 回の操作で編集できます。一括更新をおこなうには、以下の手順に従ってください。
keywords: baaam
seo-description: 一括更新では、複数のセグメント、特性、およびセグメントフォルダーまたは特性フォルダーの要素を 1 回の操作で編集できます。一括更新をおこなうには、以下の手順に従ってください。
seo-title: 一括更新
solution: Audience Manager
title: 一括更新
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 一括更新{#bulk-updates}

一括更新では、複数のセグメント、特性、およびセグメントフォルダーまたは特性フォルダーの要素を 1 回の操作で編集できます。一括更新をおこなうには、以下の手順に従ってください。

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. このツールはあくまで情報提供および便宜を目的として提供されています。一括変更については、代わりに [Audience Manager API](../../api/rest-api-main/aam-api-getting-started.md) を使用することを推奨します。[UIで割り当てられたRBACグループ権限](../../features/administration/administration-overview.md)[!DNL Audience Manager] は、で使用さ [!UICONTROL Bulk Management Tools]れます。

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. 「**[!UICONTROL Headers]**」タブをクリックして、編集する項目の更新ヘッダーをコピーします。
1. Click the **[!UICONTROL Update]** tab.
1. 更新ヘッダーを、更新ワークシートの 1 行目に貼り付けます。以下のことに注意してください。

   * フォルダーの更新時には、すべてのヘッダーが必須です。
   * セグメントまたは特性を更新する場合、必要なのはセグメント ID（SID）と、変更が必要なヘッダー要素のみです。使用していないヘッダーは削除してください。

1. ヘッダーラベルに基づいて、変更するデータを対応する列に貼り付けるか入力します。
1. ワークシートのツールバーで、更新する項目に対応する更新ボタンをクリックします。This action opens the [!UICONTROL Account Information] dialog box.

1. 必要な[ログオン情報](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)を入力し、「**[!UICONTROL Submit]**」をクリックします。

   ワークシートに「[!UICONTROL Results]」列が作成されます。「[!UICONTROL Results]」列には、成功した操作の JSON レスポンスが返されます。See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. データを入力する前の一括更新ワークシートは、次のようになります。

![](assets/update.png)

一括更新でエラーが発生した場合や失敗した場合は、[一括管理ツールのトラブルシューティング](../../reference/bulk-management-tools/bulk-troubleshooting.md)を参照してください。
