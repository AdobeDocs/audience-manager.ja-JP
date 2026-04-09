---
title: ハッシュ化されたメールワークフローのデータソースの設定
description: データソースを作成して、ハッシュ化されたメールワークフローのハッシュ化されたメールを保存する方法を説明します。
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
TQID: https://experienceleague.adobe.com/dPV7bJC5zIBkj1EX43q4FWU7XP0gs-dhBYTcW8mApL4
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 191
ht-degree: 49%

---

# ハッシュ化されたメールワークフローのデータソースの設定

ピープルベースの宛先などのハッシュ化されたメールワークフローでは、ハッシュ化されたメールアドレスを保存するデータソースを作成する必要があります。

ハッシュ化されたメールのデータソースを作成および設定するには、次の手順に従います。

1. Audience Managerアカウントにログインし、**[!UICONTROL Audience Data]**／**[!UICONTROL Data Sources]** に移動して、**[!UICONTROL Add New]**&#x200B;をクリックします。
1. 新しいデータソースに、**[!UICONTROL Name]** と **[!UICONTROL Description]** を入力します。
1. **[!UICONTROL ID Type]** ドロップダウンメニューで、「**[!UICONTROL Cross Device]**」を選択します。
   データソースの詳細セクションを示す![Audience Manager UI画像。](../features/assets/create-hashed-email-data-source.png)
1. **[!UICONTROL Data Source Settings]** セクションで、**[!UICONTROL Inbound]** と **[!UICONTROL Outbound]** のオプションを両方選択し、**[!UICONTROL Share associated cross-device IDs in people-based destinations]** オプションを有効にします。
1. ドロップダウンメニューを使用して、このデータソースの **[!UICONTROL Emails(SHA256, lowercased)]** ラベルを選択します。

   >[!IMPORTANT]
   >
   >このオプションは、データソースに、特定のアルゴリズムでハッシュ化されたデータを含んでいるというラベルのみを付けます。Audience Manager は、この手順ではデータをハッシュ化しません。このデータソースに保存する予定の電子メールアドレスが、[!DNL SHA256] アルゴリズムで既にハッシュ化されていることを確認してください。そうしなければ、ハッシュ化されたメールワークフローに使用することはできません。

   ![&#x200B; データソース設定セクションを示すAudience Manager UI画像。](../features/assets/data-source-settings.png)
