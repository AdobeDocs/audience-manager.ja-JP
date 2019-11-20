---
description: この記事では、新しい統合と既存の統合の両方について、Twitter 用にカスタマイズされたオーディエンスを設定する方法について説明します。
seo-description: この記事では、新しい統合と既存の統合の両方について、Twitter 用にカスタマイズされたオーディエンスを設定する方法について説明します。
seo-title: Twitter 用にカスタマイズされたオーディエンスをセルフサービスデバイスベースの宛先として設定する
solution: Audience Manager
title: Twitter 用にカスタマイズされたオーディエンスをセルフサービスデバイスベースの宛先として設定する
translation-type: tm+mt
source-git-commit: 4af2d7a4e2162f8d69273cf76aecb5f1ff00e7b6

---


# [!DNL Twitter Tailored Audiences] をセルフサービスデバイスベースの宛先として設定する {#configure-twitter}

この記事では、 [Twitter Cloudオーディエンスとの統合を設定する方法を説明します](https://business.twitter.com/en/targeting/tailored-audiences.html)。

## 前提条件 {#prerequisites}

[!DNL Twitter Tailored Audiences] の宛先を設定する前に満たす必要がある、以下の Twitter の前提条件を確認してください。

1. [!DNL Twitter Ads] アカウントは広告を利用する資格を持っている必要があります。新規 [!DNL Twitter Ads] アカウントは、最初に作成してから 2 習慣の間は、広告を利用する資格がありません。
2. Audience Managerでア [!DNL Twitter] クセスを承認したユーザーアカウントで、パートナーのAudience Manager権限が有効にな [っている](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 必要があります。
3. Audience Manager インスタンスで最初の [!DNL Twitter Tailored Audiences] の宛先を作成する場合は、アドビコンサルティングまたはカスタマーケアに連絡して、お使いのアカウントの [!DNL Twitter] ID 同期（データソース ID = 1123）を有効にしてください。これは、Audience Manager と [!DNL Twitter] の間で正しい同期を行うために必要です。

## 新しい [!DNL Twitter Tailored Audiences] の宛先の追加 {#add-new-twitter-destination}

ここでは、[!DNL Twitter Tailored Audiences] 用に新しいデバイスベースの宛先を設定する際に従う必要のある手順について説明します。このシナリオでは、アドビコンサルタントまたはカスタマーケアによって設定された既存の [!DNL Twitter Tailored Audiences] の宛先がないことを前提としています。

### 手順 1.[!DNL Twitter Tailored Audiences] での認証 {#step1-authenticate-with-twitter}

デバイスベースの宛先を追加するには、Audience Managerと [!DNL Twitter Tailored Audiences] アカウントをリンクさせる必要があります。手順は次のとおりです。

1. Audience Manager アカウントにログインして、**[!DNL Administration > Integrated Accounts]** に移動します。宛先プラットフォームとの統合を設定したことがある場合は、このページに表示されます。それ以外の場合、ページは空になります。
1. **[!DNL Add Account]**&#x200B;をクリックします。
1. 認証ページにリダイレクトするには、[!DNL Twitter Tailored Audiences]を選択してから&#x200B;**[!DNL Confirm]**&#x200B;をクリックします。![integrated-platforms](assets/dbd-integrated-platforms.png)
1. 認証が完了すると、Audience Manager にリダイレクトされ、関連する広告主アカウントが表示されます。使用する広告主アカウントを選択し、**[!DNL Confirm]**&#x200B;をクリックします。

### 手順 2.新しいデバイスベースの宛先を作成する {#step2-create-new-destination}

Audience Manager と [!DNL Twitter Tailored Audiences] をリンクさせたら、新しい宛先を作成できます。手順は次のとおりです。

>[!NOTE]
>
>既存のデバイスベースの宛先の名前を変更することはできません。宛先を正しく識別するために役立つ名前を指定してください。

1. Audience Manager アカウントにログインし、**[!DNL Audience Data > Destinations]** に移動して、**[!DNL Create Destination]**&#x200B;をクリックします。
1. **[!DNL Basic Information]** セクションで、新しい宛先の **[!DNL Name]** および **[!DNL Description]** を入力し、以下の設定を使用します：![setup](assets/dbd-new-basic.png)
1. **[!DNL Next]**&#x200B;をクリックします。
1. この宛先に設定する[データ書き出しラベル](/help/using/features/data-export-controls.md#controls-labels)を選択します。
1. **[!DNL Save]**&#x200B;をクリックします。
1. **[!DNL Segment Mappings]** セクションで、この宛先に送信するオーディエンスセグメントを選択します。
1. 宛先を保存します。

<!--
## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the [!DNL Twitter Tailored Audiences] integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with [!DNL Twitter Tailored Audiences], configured by an Audience Manager consultant or Customer Care.
> See item number 3 in [Prerequisites](#prerequisites) before migrating your [!DNL Twitter Tailored Audiences] to the self-service model.

Follow the steps below to migrate your existing [!DNL Twitter Tailored Audiences] destination to the self-service model.

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**.
2. Click **[!DNL Add Account]**.
3. Select [!DNL Twitter Tailored Audiences] and click **[!DNL Confirm]** to be redirected to the authentication page. ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated with your [!DNL Twitter] account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.
5. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** and click the Twitter destination that you need to configure.
6. Click **[!UICONTROL Edit]**. In the **[!UICONTROL Basic Information]** section, click the **[!UICONTROL Integrated Account]** drop-down menu and select the [!DNL Twitter] account that you have authenticated with at Step 4.
7. **[!UICONTROL Save]** the destination.

## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## セグメントマッピングに関する考慮事項 {#segment-mapping-considerations}

When mapping audience segments to [!UICONTROL Twitter], make sure to meet the following segment naming requirements:

* 人間が読み取り可能なセグメントマッピング名を指定する。Audience Manager セグメントに使用したものと同じ名前を使用することをお勧めします。
* Do not use special characters (`,` `%` `:` `;` `@` `/` `=` `?` `$`) in segment and segment mapping names. Audience Managerのセグメント名にこれらの文字が含まれている場合は、セグメントを宛先にマッピングする前に、これらの文字を削除してく [!UICONTROL Twitter] ださい。

### 例

* 正しいセグメントまたはマッピング名："US and European Shoppers"
* 誤ったセグメントまたはマッピング名："US, European 5h0pP3rs"

>[!IMPORTANT]
>
>既にマッピングされているセグメントの名前を変更することはできません。Audience Manager では、セグメント名を使用して統合のセグメントを正しく識別します。

## マッチ率に関する考慮事項 {#match-rates-considerations}

* [!UICONTROL Twitter Tailored Audiences] を使用する場合、宛先ページの [!UICONTROL Segment Addressable Audience] と [!UICONTROL Segment Match Rate] の指標niha値が表示されません。この宛先のマッチ率で一致するオーディエンスは、アドビではなく、[!UICONTROL Twitter] によって処理およびホストされるので、これは通常の動作です。
* 現在、Audience Managerとの統合では、履歴オーディエンスのバ [!UICONTROL Twitter Tailored Audiences] ックフィルはサポートされていません。 つまり、セグメントがTwitterの宛先にマッピ *ングされた* 後に発生するセグメントの資格のみが、リアルタイムで [!UICONTROL Twitter] 送信されます。
