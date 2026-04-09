---
description: この記事では、Audience Manager ユーザーインターフェイスから新しいデバイスベースの宛先を設定する方法について説明します。
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: 新しいデバイスベースの宛先の追加
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
TQID: https://experienceleague.adobe.com/E8htvz6eNU2PBT3d-oCbQDzrFRf28-Wlb3HES8n69DE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: c138d302-73f0-4186-93ea-10c4ba52f943
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 98%

---

# 新しいデバイスベースの宛先の追加 {#add-new-device-based-destinations}

この記事では、Audience Manager ユーザーインターフェイスから新しいデバイスベースの宛先を設定する方法について説明します。

>[!IMPORTANT]
>
>現在、ほとんどのデバイスベースの宛先では、セルフサービス設定ワークフローを利用できません。追加する必要があるデバイスベースの宛先が宛先リストに表示されない場合は、アドビコンサルタントまたはカスタマーサポートにお問い合わせください。

## 概要 {#overview}

新しいデバイスベースの宛先を追加するプロセスは、2 つの主な手順で構成されます。まず、Audience Manager と宛先パートナーの統合を設定する必要があります。その後、新しいデバイスベースの宛先を作成できます。

## 前提条件 {#prerequisites}

統合プラットフォームを使用して初めてデバイスベースの宛先を作成する場合は、アドビコンサルティングまたはカスタマーケアに連絡して、Audience Manager とアカウントの統合プラットフォームの間の ID 同期を有効にしてください。Audience Manager と宛先プラットフォームの同期を正しくおこなうには必要な操作です。

## 手順 1.宛先プラットフォームを使用した認証 {#step1}

新しいデバイスベースの宛先を作成する前に、Audience Manager と宛先プラットフォームの統合を設定しておく必要があります。手順は次のとおりです。

1. Audience Manager アカウントにログインして、**[!DNL Administration > Integrated Accounts]** に移動します。宛先プラットフォームとの統合を設定したことがある場合は、このページに表示されます。それ以外の場合、ページは空になります。
1. 「**[!DNL Add Account]**」をクリックします。
1. 認証する宛先プラットフォームを選択し、「**[!DNL Confirm]**」をクリックすると、選択したプラットフォームの認証ページにリダイレクトされます。

   ![integrated-platforms](assets/dbd-integrated-platforms.png)

1. 宛先プラットフォームアカウントを認証すると、Audience Manager にリダイレクトされ、関連する広告主アカウントが表示されます。使用する広告主アカウントを選択し、「**[!DNL Confirm]**」をクリックします。

## 手順 2.新しいデバイスベースの宛先を作成する {#step2}

宛先プラットフォーム統合を設定したら、新しい宛先を作成できます。手順は次のとおりです。

>[!NOTE]
>
>既存のデバイスベースの宛先の名前を変更することはできません。宛先を正しく識別するために役立つ名前を指定してください。

1. Audience Manager アカウントにログインし、**[!DNL Audience Data > Destinations]** に移動して、「**[!DNL Create Destination]**」をクリックします。
1. 「**[!DNL Basic Information]**」セクションで、新しい宛先の「**[!DNL Name]**」および「**[!DNL Description]**」を入力し、次のリストの設定を使用します。

   ![設定](assets/dbd-new-basic.png)

   * **[!DNL Category]**：[!DNL Integrated Platforms]、
   * **[!DNL Type]**：[!DNL Device-Based]、
   * **[!DNL Platform]**：オーディエンスセグメントを送信する宛先プラットフォームを選択します。
   * **[!DNL Account]**：選択したプラットフォームに関連付けられている広告主アカウントを選択します。
1. 「**[!DNL Next]**」をクリックします。
1. この宛先に設定する[データ書き出しラベル](/help/using/features/data-export-controls.md#controls-labels)を選択します。
1. 「**[!DNL Save]**」をクリックします。
1. 「**[!DNL Segment Mappings]**」セクションで、この宛先に送信するオーディエンスセグメントを選択します。
1. 宛先を保存します。
