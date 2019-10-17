---
description: この記事では、新しい統合と既存の統合の両方について、Twitter 用にカスタマイズされたオーディエンスを設定する方法について説明します。
seo-description: この記事では、新しい統合と既存の統合の両方について、Twitter 用にカスタマイズされたオーディエンスを設定する方法について説明します。
seo-title: Twitter 用にカスタマイズされたオーディエンスをセルフサービスデバイスベースの宛先として設定する
solution: Audience Manager
title: Twitter 用にカスタマイズされたオーディエンスをセルフサービスデバイスベースの宛先として設定する
translation-type: ht
source-git-commit: 7966cac59b982b5f36af6975607df64545b74058

---


# [!DNL Twitter Tailored Audiences] をセルフサービスデバイスベースの宛先として設定する {#configure-twitter}

この記事では、新しい統合と既存の統合の両方について、[Twitter 用にカスタマイズされたオーディエンス](https://business.twitter.com/ja/targeting/tailored-audiences.html)を設定する方法について説明します。

## 前提条件 {#prerequisites}

[!DNL Twitter Tailored Audiences] の宛先を設定する前に満たす必要がある、以下の Twitter の前提条件を確認してください。

1. [!DNL Twitter Ads] アカウントは広告を利用する資格を持っている必要があります。新規 [!DNL Twitter Ads] アカウントは、最初に作成してから 2 習慣の間は、広告を利用する資格がありません。
1. Audience Manager でアクセス権限を付与した Twitter ユーザーアカウントで、[パートナーオーディエンスマネージャー](https://business.twitter.com/ja/help/troubleshooting/multi-user-login-faq.html#accesslevels)権限を有効化しておく必要があります。
1. [既存の Twitter 統合をセルフサービス管理にアップデートする](#update-existing-twitter-integrations)場合は、Twitter ユーザーアカウントで[広告マネージャー](https://business.twitter.com/ja/help/troubleshooting/multi-user-login-faq.html#accesslevels)権限を有効にしておく必要があります。
1. Audience Manager インスタンスで最初の [!DNL Twitter Tailored Audiences] の宛先を作成する場合は、アドビコンサルティングまたはカスタマーケアに連絡して、お使いのアカウントの [!DNL Twitter] ID 同期（データソース ID = 1123）を有効にしてください。これは、Audience Manager と [!DNL Twitter] の間で正しい同期を行うために必要です。

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

## 既存の Twitter 統合をセルフサービス管理にアップデート {#update-existing-twitter-integrations}

ユーザーエクスペリエンスを向上し、設定プロセスを効率化するために、[!DNL Twitter Tailored Audiences] を、Audience Manager UI から自身で設定できるセルフサービスモデルへと独自の設定を行うセルフサービスモデルへとアップグレードします。ここでは、既存の Twitter 統合をアップデートするために必要な手順について説明します。

>[!IMPORTANT]
>
>以下の手順は、Audience Manager コンサルタントまたはカスタマーケアによって設定された、[!DNL Twitter Tailored Audiences] との既存の統合がある場合にのみ適用されます。
> [!DNL Twitter Tailored Audiences] をセルフサービスモデルに移行する前に、[前提条件](#prerequisites)の項目番号 3 を確認してください。

次の手順に従って、既存 [!DNL Twitter Tailored Audiences] の宛先をセルフサービスモデルに移行します。

1. Audience Manager アカウントにログインして、**[!DNL Administration > Integrated Accounts]** に移動します。
1. **[!DNL Add Account]**&#x200B;をクリックします。
1. 認証ページにリダイレクトするには、[!DNL Twitter Tailored Audiences]を選択してから&#x200B;**[!DNL Confirm]**&#x200B;をクリックします。![integrated-platforms](assets/dbd-integrated-platforms.png)
1. [!DNL Twitter] アカウントを認証すると、Audience Manager にリダイレクトされ、関連する広告主アカウントが表示されます。使用する広告主アカウントを選択し、**[!DNL Confirm]**&#x200B;をクリックします。
1. **[!UICONTROL Audience Data]**／**[!UICONTROL Destinations]** に移動し、設定する必要のある Twitter の宛先をクリックします。
1. **[!UICONTROL Edit]**&#x200B;をクリックします。**[!UICONTROL Basic Information]** セクションで **[!UICONTROL Integrated Account]** ドロップダウンメニューをクリックし、手順 4 で認証した [!DNL Twitter] アカウントを選択します。
1. **[!UICONTROL Save]** 宛先です。

<!-- ## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## セグメントマッピングに関する考慮事項 {#segment-mapping-considerations}

オーディエンスセグメントを Twitter にマッピングする場合は、以下のセグメント命名要件を満たしていることを確認してください。

* 人間が読み取り可能なセグメントマッピング名を指定する。Audience Manager セグメントに使用したものと同じ名前を使用することをお勧めします。
* セグメントおよびセグメントマッピング名ではコンマを使用しない。

### 例

* 正しいセグメントまたはマッピング名："US and European Shoppers"
* 誤ったセグメントまたはマッピング名："US, European 5h0pP3rs"

>[!IMPORTANT]
>
>既にマッピングされているセグメントの名前を変更することはできません。Audience Manager では、セグメント名を使用して統合のセグメントを正しく識別します。

## マッチ率に関する考慮事項 {#match-rates-considerations}

[!UICONTROL Twitter Tailored Audiences] を使用する場合、宛先ページの [!UICONTROL Segment Addressable Audience] と [!UICONTROL Segment Match Rate] の指標niha値が表示されません。この宛先のマッチ率で一致するオーディエンスは、アドビではなく、[!UICONTROL Twitter] によって処理およびホストされるので、これは通常の動作です。
