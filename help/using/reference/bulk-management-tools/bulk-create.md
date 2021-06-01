---
description: 一括作成により、複数のデータソース、派生シグナル、セグメント、特性およびその他の項目を 1 回の操作で作成できます。一括作成のリクエストをおこなうには、以下の手順に従ってください。
seo-description: 一括作成により、複数のデータソース、派生シグナル、セグメント、特性およびその他の項目を 1 回の操作で作成できます。一括作成のリクエストをおこなうには、以下の手順に従ってください。
seo-title: 一括作成
solution: Audience Manager
title: 一括作成
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 100%

---

# 一括作成 {#bulk-create}

一括作成により、複数のデータソース、派生シグナル、セグメント、特性およびその他の項目を 1 回の操作で作成できます。一括作成のリクエストをおこなうには、以下の手順に従ってください。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[!DNL Audience Manager] UI で割り当てられる [RBAC グループ権限](../../features/administration/administration-overview.md)は、[!UICONTROL Bulk Management Tools] に対しても適用されます。

>[!CAUTION]
>
>一括作成リクエストではオブジェクトタイプが混在しないようにしてください。各オブジェクトのヘッダーは一意で、結合できません。ワークシートをクリアして、項目ごとに別のリクエストを作成します。

オブジェクトを一括作成するには、「[!UICONTROL Bulk Management Tools]」ワークシートを開いてから、以下の手順に従ってください。

1. 「**[!UICONTROL Headers]**」タブをクリックして、追加する項目の作成ヘッダーをコピーします。
2. 「**[!UICONTROL Create]**」タブをクリックします。
3. 作成ヘッダーを、更新ワークシートの 1 行目に貼り付けます。
4. ヘッダーラベルに基づいて、変更するデータを対応する列に貼り付けるか入力します。
5. ワークシートのツールバーで、更新する項目の作成ボタンをクリックします。これにより、[!UICONTROL Account Information] ダイアログボックスが開きます。
6. 必要な[ログオン情報](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)を入力し、「**[!UICONTROL Submit]**」をクリックします。

ワークシートに「[!UICONTROL Results]」列が作成されます。「[!UICONTROL Results]」列には、成功した操作の JSON レスポンスが返されます。例については[ REST API](../../api/rest-api-main/rest-api-main.md) を参照してください。データを入力する前の一括作成ワークシートは、次の例のようになります。ただし、作成オプションのすべてがここに表示されているわけではありません。この例は、完成したワークシートの概要を把握するためのものです。

![](assets/cretetraits.png)

一括更新でエラーが発生した場合や失敗した場合は、[一括管理ツールのトラブルシューティング](../../reference/bulk-management-tools/bulk-troubleshooting.md)を参照してください。
