---
description: 一括削除では、複数のセグメント、特性、フォルダー、派生シグナルおよび送信先を 1 回の操作で削除できます。一括削除リクエストをおこなうには、以下の手順に従ってください。
seo-description: 一括削除では、複数のセグメント、特性、フォルダー、派生シグナルおよび宛先を 1 回の操作で削除できます。一括削除リクエストをおこなうには、以下の手順に従ってください。
seo-title: 一括削除
solution: Audience Manager
title: 一括削除
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 一括削除{#bulk-delete}

一括削除では、複数のセグメント、特性、フォルダー、派生シグナルおよび送信先を 1 回の操作で削除できます。一括削除の要求をおこなうには、以下の手順に従ってください。

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. このツールはあくまで情報提供および便宜を目的として提供されています。一括変更については、代わりに [Audience Manager API](../../api/rest-api-main/aam-api-getting-started.md) を使用することを推奨します。[UIで割り当てられたRBACグループ権限](../../features/administration/administration-overview.md)[!DNL Audience Manager] は、で使用さ [!UICONTROL Bulk Management Tools]れます。

>[!NOTE]
>
>宛先にセグメントがマッピングされている場合、宛先マッピングの一括削除は失敗します。宛先を一括削除する前に、ユーザーインターフェイスで宛先からセグメントを削除します。また、特性フォルダーとセグメントフォルダーを削除するには、そのフォルダーが空でなければなりません。

To delete multiple items, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. 「**[!UICONTROL Headers]**」タブをクリックして、追加する項目の作成ヘッダーをコピーします。
2. Click the **[!UICONTROL Delete]** tab.
3. 削除ヘッダーを、更新ワークシートの 1 行目に貼り付けます。
4. 削除するオブジェクトの ID を、ヘッダーの下の列に貼り付けるか入力します。
5. 必要な[ログオン情報](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)を入力し、「**[!UICONTROL Submit]**」をクリックします。

   ワークシートに「[!UICONTROL Results]」列が作成されます。「[!UICONTROL Results]」列に、アイテムが削除されたかどうかを表すメッセージ、またはエラーメッセージが返されます。データを入力する前の一括更新ワークシートは、次のようになります。

![](assets/delete.png)

一括更新でエラーが発生した場合や失敗した場合は、[一括管理ツールのトラブルシューティング](../../reference/bulk-management-tools/bulk-troubleshooting.md)を参照してください。
