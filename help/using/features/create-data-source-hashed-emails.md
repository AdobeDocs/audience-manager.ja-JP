---
title: ハッシュ化されたメールワークフロー用のデータソースの設定
description: ハッシュ化されたメールワークフロー用にハッシュ化されたメールを保存するデータソースの作成方法を説明します。
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
source-git-commit: d55dbc4f9630e3d22dfb988f6725f33993229c48
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 49%

---

# ハッシュ化されたメールワークフロー用のデータソースの設定

人物ベースの宛先などのハッシュ化されたメールワークフローでは、ハッシュ化されたメールアドレスを保存するために、データソースを作成する必要があります。

ハッシュ化されたメールのデータソースを作成して設定するには、次の手順に従います。

1. Audience Managerアカウントにログインし、**[!UICONTROL Audience Data]**／**[!UICONTROL Data Sources]** に移動して、**[!UICONTROL Add New]**&#x200B;をクリックします。
1. 新しいデータソースに、**[!UICONTROL Name]** と **[!UICONTROL Description]** を入力します。
1. **[!UICONTROL ID Type]** ドロップダウンメニューで、「**[!UICONTROL Cross Device]**」を選択します。
   ![ データソースの詳細セクションを示すAudience Manager UI 画像。](../features/assets/create-hashed-email-data-source.png)
1. **[!UICONTROL Data Source Settings]** セクションで、**[!UICONTROL Inbound]** と **[!UICONTROL Outbound]** のオプションを両方選択し、**[!UICONTROL Share associated cross-device IDs in people-based destinations]** オプションを有効にします。
1. ドロップダウンメニューを使用して、このデータソースの **[!UICONTROL Emails(SHA256, lowercased)]** ラベルを選択します。

   >[!IMPORTANT]
   >
   >このオプションは、データソースに、特定のアルゴリズムでハッシュ化されたデータを含んでいるというラベルのみを付けます。Audience Manager は、この手順ではデータをハッシュ化しません。このデータソースに保存する予定の電子メールアドレスが、[!DNL SHA256] アルゴリズムで既にハッシュ化されていることを確認してください。そうでない場合、ハッシュ化されたメールワークフローで使用することはできません。

   ![ 「データソース設定」セクションを示すAudience Manager UI 画像。](../features/assets/data-source-settings.png)
