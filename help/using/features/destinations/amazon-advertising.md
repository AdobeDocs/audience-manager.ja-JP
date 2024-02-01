---
description: この記事では、新しい統合と既存の統合の両方に対してAmazon Advertising を設定する方法について説明します。
solution: Audience Manager
title: Amazon Advertising をセルフサービスデバイスベースの宛先として設定する
source-git-commit: 01f3c2d813a91b8541bd8ba8a8b030f67a4f979e
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 53%

---


# [!DNL Amazon Advertising] をセルフサービスデバイスベースの宛先として設定する  {#configure-amazon}

この記事では、 [Amazon Advertising](https://advertising.amazon.com/API/docs/en-us).

## 前提条件 {#prerequisites}

[!DNL Amazon Advertising] 宛先を設定する前に、次の前提条件を満たしていることを確認してください。

* お使いの [!DNL Amazon] アカウントは広告を利用する資格を持つ必要があります。
* Audience Manager インスタンスで最初の [!DNL Amazon Advertising] の宛先を作成する場合は、アドビコンサルティングまたはカスタマーケアに連絡して、お使いのアカウントの [!DNL Amazon] ID 同期（データソース ID = 139200）を有効にしてください。これは、Audience Manager と [!DNL Amazon] の間で正しい同期を行うために必要です。
* 新しいデータプロバイダーオーディエンスを作成したら、次の手順を実行します。 [メタデータを更新](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put) をクリックし、 **[!DNL audience fees]**. この操作では、 [Amazon Ads API](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access) または [Amazon Advertising UI](https://advertising.amazon.com/).

## 新しい [!DNL Amazon Advertising] の宛先の追加 {#add-new-amazon-destination}

ここでは、[!DNL Amazon Advertising] 用に新しいデバイスベースの宛先を設定する際に従う必要のある手順について説明します。このシナリオでは、アドビコンサルタントまたはカスタマーケアによって設定された既存の [!DNL Amazon Advertising] の宛先がないことを前提としています。

### 手順 1.[!DNL Amazon Advertising] での認証  {#step1-authenticate-with-amazon}

デバイスベースの宛先を追加するには、Audience Managerと [!DNL Amazon Advertising] アカウントをリンクさせる必要があります。手順は次のとおりです。

1. Audience Manager アカウントにログインして、**[!UICONTROL Administration > Integrated Accounts]** に移動します。宛先プラットフォームとの統合を設定したことがある場合は、このページに表示されます。それ以外の場合、ページは空になります。
1. 選択 **[!UICONTROL Add Account]**.
1. 選択 [!UICONTROL Amazon Data Provider].

   ![integrated-platforms](assets/dbd-amazon-without-options.png)

1. 次のいずれかを選択します。 **[!UICONTROL Amazon Data Provider]** オプションを選択します。 [!DNL Amazon Ads] アカウントを作成し（北米、ヨーロッパ、極東）、「 **[!DNL Confirm]** 認証ページにリダイレクトされます。

   ![integrated-platforms](assets/dbd-amazon-with-options.png)

1. 認証が完了すると、Audience Manager にリダイレクトされ、関連する広告主アカウントが表示されます。使用する広告主アカウントを選択し、 **[!UICONTROL Confirm]**. これにより、Audience Managerがオーディエンスの更新を送信するためのアクセスを承認しました。

### 手順 2.新しいデバイスベースの宛先を作成する {#step2-create-new-destination}

Audience Managerと [!DNL Amazon Advertising] アカウントを使用する場合は、新しい宛先を作成できます。 手順は次のとおりです。

>[!NOTE]
>
>既存のデバイスベースの宛先の名前を変更することはできません。宛先を正しく識別するために役立つ名前を指定してください。

1. Audience Managerアカウントにログインし、に移動します。 **[!UICONTROL Audience Data > Destinations]**&#x200B;をクリックし、次を選択します。 **[!UICONTROL Create Destination]**.
1. Adobe Analytics の **[!UICONTROL Basic Information]** セクションに、 **[!UICONTROL Name]** および **[!UICONTROL Description]** を新しい宛先に追加し、以下の設定を使用します。

   ![設定](assets/dbd-new-account-amazon.png)

1. 選択 **[!UICONTROL Next]**.
1. この宛先に設定する[データ書き出しラベル](/help/using/features/data-export-controls.md#controls-labels)を選択します。
1. 選択 **[!UICONTROL Save]**.
1. 「**[!UICONTROL Segment Mappings]**」セクションで、この宛先に送信するオーディエンスセグメントを選択します。
1. 宛先を保存します。

## マッチ率に関する考慮事項 {#match-rates-considerations}

Audience Manager と [!DNL Amazon Advertising] の統合では、履歴オーディエンスのバックフィルがサポートされます。宛先を作成すると、すべてのセグメント認定が [!DNL Amazon] に送信されます。

## トラブルシューティング {#troubleshooting}

データを設定するか、に送信する際に [!DNL Amazon Advertising] の宛先に到達した場合、以下に説明するエラーが発生する可能性があります。 この節では、エラーの原因とその修正方法について説明します。

| エラーメッセージ | 原因／理由 | 解決策 |
|---|---|---|
| `Internal server error` | このエラーメッセージは、新しい [!DNL Amazon] Amazon API の古いバージョンを使用しているアカウント。 | アドビカスタマーケアに連絡してください。 |
| `Amazon Error: Account XXXXXXXXX was not found` | このエラーメッセージは、宛先に対して設定された資格情報が、対応するAmazon Ads アカウントへのアクセスを許可されていない場合に、Audience ManagerUI に表示されます。 | <ul><li>使用しているアカウント資格情報が[前提条件](#prerequisites)を満たしていることを確認してください。</li><li>同じ資格情報を使用してAmazon Ads UI に移動し、対応するアカウントの下に正しいオーディエンスが表示されているかどうかを確認します。 </li></ul> |
