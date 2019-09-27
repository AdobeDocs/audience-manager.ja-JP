---
description: この記事では、新しい統合と既存の統合の両方について、Twitter 用にカスタマイズされたオーディエンスを設定する方法について説明します。
seo-description: この記事では、新しい統合と既存の統合の両方について、Twitter 用にカスタマイズされたオーディエンスを設定する方法について説明します。
seo-title: Twitter 用にカスタマイズされたオーディエンスをセルフサービスデバイスベースの宛先として設定する
solution: Audience Manager
title: Twitter 用にカスタマイズされたオーディエンスをセルフサービスデバイスベースの宛先として設定する
translation-type: tm+mt
source-git-commit: c6318921b49603015b4670a361ec85ffa29abb30

---


# [!DNL Twitter Tailored Audiences] をセルフサービスデバイスベースの宛先として設定する{#configure-twitter}

This article explains how to configure [Twitter Tailored Audiences](https://business.twitter.com/en/targeting/tailored-audiences.html) for both new and existing integrations.

## 前提条件 {#prerequisites}

[!DNL Twitter Tailored Audiences] の宛先を設定する前に満たす必要がある、以下の Twitter の前提条件を確認してください。

1. [!DNL Twitter Ads] アカウントは広告を利用する資格を持っている必要があります。新規 [!DNL Twitter Ads] アカウントは、最初に作成してから 2 習慣の間は、広告を利用する資格がありません。
1. Your Twitter user account that you authorized access for in Audience Manager must have the [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) permission enabled.
1. If you are [updating your existing Twitter integration to self-service administration](#update-existing-twitter-integrations), your Twitter user account must have the [Ad manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) permission enabled.
1. Audience Manager インスタンスで最初の [!DNL Twitter Tailored Audiences] の宛先を作成する場合は、アドビコンサルティングまたはカスタマーケアに連絡して、お使いのアカウントの [!DNL Twitter] ID 同期（データソース ID = 1123）を有効にしてください。これは、Audience Manager と [!DNL Twitter] の間で正しい同期を行うために必要です。

## 新しい [!DNL Twitter Tailored Audiences] の宛先の追加{#add-new-twitter-destination}

ここでは、[!DNL Twitter Tailored Audiences] 用に新しいデバイスベースの宛先を設定する際に従う必要のある手順について説明します。このシナリオでは、アドビコンサルタントまたはカスタマーケアによって設定された既存の [!DNL Twitter Tailored Audiences] の宛先がないことを前提としています。

### 手順 1.[!DNL Twitter Tailored Audiences] での認証{#step1-authenticate-with-twitter}

デバイスベースの宛先を追加するには、Audience Managerと [!DNL Twitter Tailored Audiences] アカウントをリンクさせる必要があります。手順は次のとおりです。

1. Audience Manager アカウントにログインして、**[!DNL Administration > Integrated Accounts]** に移動します。宛先プラットフォームとの統合を設定したことがある場合は、このページに表示されます。それ以外の場合、ページは空になります。
2. 「**[!DNL Add Account]**」をクリックします。
3. 認証ページにリダイレクトするには、「[!DNL Twitter Tailored Audiences]」を選択してから「**[!DNL Confirm]**」をクリックします。![integrated-platforms](assets/dbd-integrated-platforms.png)
4. 認証が完了すると、Audience Manager にリダイレクトされ、関連する広告主アカウントが表示されます。使用する広告主アカウントを選択し、「**[!DNL Confirm]**」をクリックします。

### 手順 2：新しいデバイスベースの宛先を作成する {#step2-create-new-destination}

Audience Manager と [!DNL Twitter Tailored Audiences] をリンクさせたら、新しい宛先を作成できます。手順は次のとおりです。

>[!NOTE]
>
>既存のデバイスベースの宛先の名前を変更することはできません。宛先を正しく識別するために役立つ名前を指定してください。

1. Audience Manager アカウントにログインし、**[!DNL Audience Data > Destinations]** に移動して、「**[!DNL Create Destination]**」をクリックします。
2. **[!DNL Basic Information]** セクションで、新しい宛先の **[!DNL Name]** および **[!DNL Description]** を入力し、以下の設定を使用します：![setup](assets/dbd-new-basic.png)
3. 「**[!DNL Next]**」をクリックします。
4. この宛先に設定する[データ書き出しラベル](/help/using/features/data-export-controls.md#controls-labels)を選択します。
5. 「**[!DNL Save]**」をクリックします。
6. **[!DNL Segment Mappings]** セクションで、この宛先に送信するオーディエンスセグメントを選択します。
7. 宛先を保存します。

## 既存の Twitter 統合をセルフサービス管理にアップデート{#update-existing-twitter-integrations}

ユーザーエクスペリエンスを向上し、設定プロセスを効率化するために、[!DNL Twitter Tailored Audiences] を、Audience Manager UI から自身で設定できるセルフサービスモデルへと独自の設定を行うセルフサービスモデルへとアップグレードします。ここでは、既存の Twitter 統合をアップデートするために必要な手順について説明します。

>[!IMPORTANT]
>
>以下の手順は、Audience Manager コンサルタントまたはカスタマーケアによって設定された、[!DNL Twitter Tailored Audiences] との既存の統合がある場合にのみ適用されます。宛先からセルフサービスモデルへの完全なアップグレードプロセスには、最大 5 営業日かかる場合があります。それまでの間、宛先はアクティブのままとなり、Audience Manager は引き続きオーディエンスを送信します。
> [!DNL Twitter Tailored Audiences] をセルフサービスモデルに移行する前に、[前提条件](#prerequisites)の項目番号 3 を確認してください。

次の手順に従って、既存 [!DNL Twitter Tailored Audiences] の宛先をセルフサービスモデルに移行します。

1. Audience Manager アカウントにログインして、**[!DNL Administration > Integrated Accounts]** に移動します。
1. 「**[!DNL Add Account]**」をクリックします。
1. 認証ページにリダイレクトするには、「[!DNL Twitter Tailored Audiences]」を選択してから「**[!DNL Confirm]**」をクリックします。![integrated-platforms](assets/dbd-integrated-platforms.png)
1. [!DNL Twitter] アカウントを認証すると、Audience Manager にリダイレクトされ、関連する広告主アカウントが表示されます。使用する広告主アカウントを選択し、「**[!DNL Confirm]**」をクリックします。
1. **[!UICONTROL Audience Data]**／**[!UICONTROL Destinations]** に移動し、設定する必要のある Twitter の宛先をクリックします。
1. 「**[!UICONTROL Edit]**」をクリックします。**[!UICONTROL Basic Information]** セクションで **[!UICONTROL Integrated Account]** ドロップダウンメニューをクリックし、手順 4 で認証した [!DNL Twitter] アカウントを選択します。
1. **[!UICONTROL Save]** 宛先です。

## セルフサービス管理への移行の検証 {#migration-validation}

既存の [!DNL Twitter] 統からセルフサービス管理への完全な移行には、最大 7 日間かかることがあります。移行が完了すると、Audience Manager によって、UI に通知が表示されます。

また、[!DNL Twitter] アカウントに新しいオーディエンスのセットが表示され、名前には [!DNL Adobe DMP Audience] のプレフィックスが付けられます。オーディエンス母集団が完全にバックフィルされるまで最大 7 日間かかります。移行が完了したら、古いオーディエンスの代わりにこれらの新しいオーディエンスを使用する必要があります。

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

## Match Rates Considerations {#match-rates-considerations}

When using [!UICONTROL Twitter Tailored Audiences], the [!UICONTROL Segment Addressable Audience] and [!UICONTROL Segment Match Rate] metrics from the destination page will not display any values. This is normal behavior, since audience matching along with the match rates for this destination are handled and hosted by [!UICONTROL Twitter], not Adobe.
