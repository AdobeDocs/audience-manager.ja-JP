---
description: 一括作成により、複数のデータソース、派生シグナル、セグメント、特性およびその他の項目を 1 回の操作で作成できます。一括作成のリクエストをおこなうには、以下の手順に従ってください。
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: 一括作成
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
TQID: https://experienceleague.adobe.com/EbavgrTOfC5Wjx4IwGxt4Gi3-d-EkOSQjG3WaRAionU
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: c2c33729-f309-4bc2-92ba-87c475259df3id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 90%

---

# 一括作成{#bulk-create}

一括作成により、複数のデータソース、派生シグナル、セグメント、特性およびその他の項目を 1 回の操作で作成できます。一括作成のリクエストをおこなうには、以下の手順に従ってください。

>[!IMPORTANT]
>
>一括管理ツールは、公式にサポートされているAdobe製品ではありません。 カスタマーサポートによるトラブルシューティングおよびサポートは、ケースバイケースで対応します。

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
