---
description: この記事では、Audience Manager UIから新しいデバイスベースの宛先を設定する方法について説明します。
seo-description: この記事では、Audience Manager UIから新しいデバイスベースの宛先を設定する方法について説明します。
seo-title: 新しいデバイスベースの宛先の追加
solution: Audience Manager
title: 新しいデバイスベースの宛先の追加
translation-type: tm+mt
source-git-commit: c206246a4a586d1148c18e0bce734d07963a85f6

---


# 新しいデバイスベースの宛先の追加 {#add-new-device-based-destinations}

この記事では、Audience Manager UIから新しいデバイスベースの宛先を設定する方法について説明します。

## 概要 {#overview}

新しいデバイスベースの宛先を追加するプロセスは、2つの主な手順で構成されます。 まず、Audience Managerと宛先パートナーの間の統合を設定する必要があります。 その後、新しいデバイスベースの宛先を作成できます。

## 前提条件 {#prerequisites}

統合プラットフォームを使用して最初のデバイスベースの宛先を作成する場合は、アドビコンサルティングまたはカスタマーケアに連絡して、Audience Managerとアカウントの統合プラットフォームとの間でID同期を有効にしてください。 これは、Audience Managerと宛先プラットフォームとの間で正しい同期をとるために必要です。

>[!IMPORTANT]
>
>セルフサービス設定ワークフローには、すべてのデバイスベースの宛先が該当するわけではありません。 追加する必要があるデバイスベースの宛先が宛先リストに表示されない場合は、アドビコンサルタントまたはカスタマーサポートにお問い合わせください。

## 手順 1. 宛先プラットフォームでの認証 {#step1}

新しいデバイスベースの宛先を作成する前に、Audience Managerと宛先プラットフォームの間の統合を設定する必要があります。 手順は次のとおりです。

1. Audience Managerアカウントにログインし、に移動します **[!DNL Administration > Integrated Accounts]**。 以前に宛先プラットフォームとの統合を設定した場合は、このページに表示されます。 それ以外の場合、ページは空です。
1. 「**[!DNL Add Account]**」をクリックします。
1. 認証に使用する宛先プラットフォームを選択し、選択したプラッ **[!DNL Confirm]** トフォームの認証ページにリダイレクトされるようにクリックします。 ![統合プラットフォーム](assets/dbd-integrated-platforms.png)
1. 目的のプラットフォームアカウントに対して認証が完了すると、Audience Managerにリダイレクトされ、関連付けられた広告主アカウントが表示されます。 使用する広告主アカウントを選択し、をクリックしま **[!DNL Confirm]**&#x200B;す。

## 手順 2：新しいデバイスベースの宛先の作成 {#step2}

宛先プラットフォーム統合を設定した後、新しい宛先を作成できます。 手順は次のとおりです。

>[!NOTE]
>
>既存のデバイスベースの宛先の名前は変更できません。 宛先を正しく識別するのに役立つ名前を指定してください。

1. Audience Managerアカウントにログインし、に移動して、をク **[!DNL Audience Data > Destinations]**&#x200B;リックします **[!DNL Create Destination]**。
1. セクション **[!DNL Basic Information]** で、新しい宛先 **[!DNL Name]** の「 **[!DNL Description]** 」と「」を入力し、以下のリストの設定を使用します。設 ![定](assets/dbd-new-basic.png)
   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**:オーディエンスセグメントの送信先プラットフォームを選択します。
   * **[!DNL Account]**:選択したプラットフォームに関連付ける広告主アカウントを選択します。
1. 「**[!DNL Next]**」をクリックします。
1. この宛先 [に設定するデータ書き出し](/help/using/features/data-export-controls.md#controls-labels) 「ラベル」を選択します。
1. 「**[!DNL Save]**」をクリックします。
1. セクション **[!DNL Segment Mappings]** で、この宛先に送信するオーディエンスセグメントを選択します。
1. 宛先を保存します。
