---
description: 一括予測では、セグメントルールに基づきセグメントサイズデータが返されます。一括予測リクエストをおこなうには、以下の手順に従ってください。
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: 一括予測
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
TQID: https://experienceleague.adobe.com/FDD4gSg00I8p4sRqxE9sEpO5dSkGEXpH3hUD6h5CAtI
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 86%

---

# 一括予測{#bulk-estimates}

一括予測では、セグメントルールに基づきセグメントサイズデータが返されます。一括予測リクエストをおこなうには、以下の手順に従ってください。

>[!IMPORTANT]
>
>一括管理ツールは、公式にサポートされているAdobe製品ではありません。 カスタマーサポートによるトラブルシューティングおよびサポートは、ケースバイケースで対応します。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[!DNL Audience Manager] UI で割り当てられる [RBAC グループ権限](../../features/administration/administration-overview.md)は、[!UICONTROL Bulk Management Tools] に対しても適用されます。

一括更新をおこなうには、[!UICONTROL Bulk Management Tools] ワークシートを開き、以下の手順に従ってください。

1. 「**[!UICONTROL Headers]**」タブをクリックして、[!UICONTROL Estimate Segment Size] ヘッダーをコピーします。
2. 「**[!UICONTROL Estimate]**」タブをクリックします。
3. 予測ヘッダーを、予測ワークシートの 1 行目に貼り付けます。
4. ヘッダーラベルに基づいて、変更するデータを対応する列に貼り付けるか入力します。
5. ワークシートのツールバーで、更新する項目の作成ボタンをクリックします。これにより、[!UICONTROL Account Information] ダイアログボックスが開きます。
6. 必要な[ログオン情報](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)を入力し、「**[!UICONTROL Submit]**」をクリックします。

この操作により、ワークシートに「[!UICONTROL Response]」列が作成され、セグメントの予測サイズのデータが格納されます。データを入力する前の一括予測ワークシートは、次のようになります。

![](assets/estimate.png)
一括更新でエラーが発生した場合や失敗した場合は、[一括管理ツールのトラブルシューティング](../../reference/bulk-management-tools/bulk-troubleshooting.md)を参照してください。
