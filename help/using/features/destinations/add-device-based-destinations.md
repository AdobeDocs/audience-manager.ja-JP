---
description: この記事では、Audience Manager UIから新しいデバイスベースの宛先を設定する方法について説明します。
seo-description: この記事では、Audience Manager UIから新しいデバイスベースの宛先を設定する方法について説明します。
seo-title: 新しいデバイスベースの宛先の追加
solution: Audience Manager
title: 新しいデバイスベースの宛先の追加
translation-type: tm+mt
source-git-commit: d185a1d418e99abb99c36b28dfb419a1fb3b60f5

---


# 新しいデバイスベースの宛先の追加 {#add-new-device-based-destinations}

この記事では、Audience Manager UIから新しいデバイスベースの宛先を設定する方法について説明します。

## 概要 {#overview}

新しいデバイスベースの宛先を追加するプロセスは、2つの主な手順で構成されます。まず、Audience Managerと宛先パートナーの統合を設定する必要があります。その後、新しいデバイスベースの宛先を作成できます。

>[!IMPORTANT]
>
>すべてのデバイスベースの宛先に、セルフサービス設定ワークフローの資格があるわけではありません。追加する必要があるデバイスベースの宛先が宛先リストに表示されない場合は、アドビコンサルタントまたはカスタマーサポートにお問い合わせください。

## 手順 1. 宛先プラットフォームの認証 {#step1}

新しいデバイスベースの宛先を作成するには、Audience Managerと宛先プラットフォームの統合を設定する必要があります。手順は次のとおりです。

1. Audience Managerアカウントにログインして、に移動 **[!DNL Administration > Integrated Accounts]**&#x200B;します。以前に設定したプラットフォームとの統合が設定されている場合は、このページに表示されていることを確認してください。それ以外の場合、ページは空です。
2. **[!DNL Add Account]**&#x200B;をクリックします。
3. 認証する宛先プラットフォームを選択し、クリック **[!DNL Confirm]** して選択したプラットフォームの認証ページにリダイレクトします。![統合プラットフォーム](assets/dbd-integrated-platforms.png)
4. 宛先プラットフォームアカウントを認証すると、関連する広告主アカウントを表示するAudience Managerにリダイレクトされます。使用する広告主アカウントを選択し、をクリック **[!DNL Confirm]**&#x200B;します。

## 手順 2：新しいデバイスベースの宛先の作成 {#step2}

宛先プラットフォーム統合を設定したら、新しい宛先を作成できます。手順は次のとおりです。

>[!NOTE]
>
>既存のデバイスベースの宛先の名前を変更することはできません。宛先を正しく識別するために役立つ名前を指定してください。

1. Audience Managerアカウントにログインし、アクセスして **[!DNL Audience Data > Destinations]**&#x200B;クリック **[!DNL Create Destination]**&#x200B;します。
2. **[!DNL Basic Information]** セクションで **[!DNL Name]** 、および **[!DNL Description]** 新しい宛先を入力し、以下のリストの設定を使用します。 ![セットアップ](assets/dbd-new-basic.png)
   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**:オーディエンスセグメントを送信する宛先プラットフォームを選択します。
   * **[!DNL Account]**:選択したプラットフォームに関連付けられている広告主アカウントを選択します。
3. **[!DNL Next]**&#x200B;をクリックします。
4. この宛先に設定する [データのエクスポートラベル](/help/using/features/data-export-controls.md#controls-labels) を選択します。
5. **[!DNL Save]**&#x200B;をクリックします。
6. **[!DNL Segment Mappings]** セクションで、この宛先に送信するオーディエンスセグメントを選択します。
7. 宛先を保存します。

