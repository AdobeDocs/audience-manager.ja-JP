---
description: この記事では、新しい統合と既存の統合の両方について、Twitter 用にカスタマイズされたオーディエンスを設定する方法について説明します。
seo-description: この記事では、新しい統合と既存の統合の両方について、Twitter 用にカスタマイズされたオーディエンスを設定する方法について説明します。
seo-title: Twitter 用にカスタマイズされたオーディエンスをセルフサービスデバイスベースの宛先として設定する
solution: Audience Manager
title: Twitter 用にカスタマイズされたオーディエンスをセルフサービスデバイスベースの宛先として設定する
feature: People-Based Destinations
translation-type: ht
source-git-commit: 6716c871562cd0203239897fc096033160e2fc13
workflow-type: ht
source-wordcount: '555'
ht-degree: 100%

---


# [!DNL Twitter Tailored Audiences] をセルフサービスデバイスベースの宛先として設定する {#configure-twitter}

この記事では、[Twitter Cloud Audiences](https://business.twitter.com/ja/targeting/tailored-audiences.html) との統合を設定する方法を説明します。

## 前提条件 {#prerequisites}

[!DNL Twitter Tailored Audiences] の宛先を設定する前に満たす必要がある、以下の Twitter の前提条件を確認してください。

1. [!DNL Twitter Ads] アカウントは広告を利用する資格を持っている必要があります。新規 [!DNL Twitter Ads] アカウントは、最初に作成してから 2 習慣の間は、広告を利用する資格がありません。
2. Audience Manager でアクセスを承認した [!DNL Twitter] ユーザーアカウントで、[パートナーの Audience Manager](https://business.twitter.com/ja/help/troubleshooting/multi-user-login-faq.html#accesslevels) 権限が有効になっている必要があります。
3. Audience Manager インスタンスで最初の [!DNL Twitter Tailored Audiences] の宛先を作成する場合は、アドビコンサルティングまたはカスタマーケアに連絡して、お使いのアカウントの [!DNL Twitter] ID 同期（データソース ID = 1123）を有効にしてください。これは、Audience Manager と [!DNL Twitter] の間で正しい同期を行うために必要です。

## 新しい [!DNL Twitter Tailored Audiences] の宛先の追加 {#add-new-twitter-destination}

ここでは、[!DNL Twitter Tailored Audiences] 用に新しいデバイスベースの宛先を設定する際に従う必要のある手順について説明します。このシナリオでは、アドビコンサルタントまたはカスタマーケアによって設定された既存の [!DNL Twitter Tailored Audiences] の宛先がないことを前提としています。

### 手順 1.[!DNL Twitter Tailored Audiences] での認証 {#step1-authenticate-with-twitter}

デバイスベースの宛先を追加するには、Audience Managerと [!DNL Twitter Tailored Audiences] アカウントをリンクさせる必要があります。手順は次のとおりです。

1. Audience Manager アカウントにログインして、**[!DNL Administration > Integrated Accounts]** に移動します。宛先プラットフォームとの統合を設定したことがある場合は、このページに表示されます。それ以外の場合、ページは空になります。
1. 「**[!DNL Add Account]**」をクリックします。
1. 認証ページにリダイレクトするには、[!DNL Twitter Tailored Audiences]を選択してから、「**[!DNL Confirm]**」をクリックします。![integrated-platforms](assets/dbd-integrated-platforms.png)
1. 認証が完了すると、Audience Manager にリダイレクトされ、関連する広告主アカウントが表示されます。使用する広告主アカウントを選択し、「**[!DNL Confirm]**」をクリックします。

### 手順 2.新しいデバイスベースの宛先を作成する {#step2-create-new-destination}

Audience Manager と [!DNL Twitter Tailored Audiences] をリンクさせたら、新しい宛先を作成できます。手順は次のとおりです。

>[!NOTE]
>
>既存のデバイスベースの宛先の名前を変更することはできません。宛先を正しく識別するために役立つ名前を指定してください。

1. Audience Manager アカウントにログインし、**[!DNL Audience Data > Destinations]** に移動して、「**[!DNL Create Destination]**」をクリックします。
1. **[!DNL Basic Information]** セクションで、新しい宛先の **[!DNL Name]** および **[!DNL Description]** を入力し、以下の設定を使用します：![setup](assets/dbd-new-basic.png)
1. 「**[!DNL Next]**」をクリックします。
1. この宛先に設定する[データ書き出しラベル](/help/using/features/data-export-controls.md#controls-labels)を選択します。
1. 「**[!DNL Save]**」をクリックします。
1. 「**[!DNL Segment Mappings]**」セクションで、この宛先に送信するオーディエンスセグメントを選択します。
1. 宛先を保存します。

## セグメントマッピングに関する考慮事項 {#segment-mapping-considerations}

オーディエンスセグメントを [!UICONTROL Twitter] にマッピングする場合は、以下のセグメント命名要件を満たしていることを確認してください。

* 人間が読み取り可能なセグメントマッピング名を指定する。Audience Manager セグメントに使用したものと同じ名前を使用することをお勧めします。
* セグメントおよびセグメントマッピング名では特殊文字（`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`）を使用しないでください。Audience Manager のセグメント名にこれらの文字が含まれている場合は、セグメントを [!UICONTROL Twitter] 宛先にマッピングする前に、これらの文字を削除してください。

### 例

* 正しいセグメントまたはマッピング名：&quot;US and European Shoppers&quot;
* 誤ったセグメントまたはマッピング名：&quot;US, European 5h0pP3rs&quot;

>[!IMPORTANT]
>
>既にマッピングされているセグメントの名前を変更することはできません。Audience Manager では、セグメント名を使用して統合のセグメントを正しく識別します。

## マッチ率に関する考慮事項 {#match-rates-considerations}

* Audience Manager と [!UICONTROL Twitter Tailored Audiences] の統合では、履歴オーディエンスのバックフィルがサポートされます。宛先を作成すると、すべてのセグメント認定が [!UICONTROL Twitter] に送信されます。
