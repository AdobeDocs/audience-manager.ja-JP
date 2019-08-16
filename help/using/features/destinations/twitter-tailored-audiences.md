---
description: この記事では、新しい統合と既存の統合の両方について、Twitterにカスタマイズされたオーディエンスを設定する方法について説明します。
seo-description: この記事では、新しい統合と既存の統合の両方について、Twitterにカスタマイズされたオーディエンスを設定する方法について説明します。
seo-title: Twitterにカスタマイズされたオーディエンスをセルフサービスデバイスベースの宛先として設定する
solution: Audience Manager
title: Twitterにカスタマイズされたオーディエンスをセルフサービスデバイスベースの宛先として設定する
translation-type: tm+mt
source-git-commit: 0ca286bd391c9c3a5298508ecc5a42ec61a64044

---


# セルフサービスデバイスベースの宛先 [!DNL Twitter Tailored Audiences] としての設定 {#configure-twitter}

この記事では、新しい統合と既存の統合の両方に [ついて、Twitterにカスタマイズさ](https://business.twitter.com/en/targeting/tailored-audiences.html) れたオーディエンスを設定する方法について説明します。

## 前提条件 {#prerequisites}

送信先を [!DNL Twitter Tailored Audiences] 設定する前に、以下のTwitterの前提条件を確認してください。

1. [!DNL Twitter Ads] アカウントは広告の資格がある必要があります。新規 [!DNL Twitter Ads] アカウントは、作成後の最初の2週間で広告の資格がありません。
2. Audience Managerでアクセス権限を付与したTwitterユーザーアカウントに [は、パートナーAudience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 権限が有効になっている必要があります。
3. 既存のTwitter統合をセルフサービス管理に [更新する場合、Twitterユーザーアカウント](#update-existing-twitter-integrations)に [は広告マネージャー](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) の権限が有効になっている必要があります。



## [!DNL Twitter Tailored Audiences] 新しい宛先の追加 {#add-new-twitter-destination}

ここでは、新しいデバイスベースの宛先を設定する際に従う必要のある手順について説明 [!DNL Twitter Tailored Audiences]します。このシナリオでは、アドビコンサルタントまたはカスタマーケアによって設定された既存 [!DNL Twitter Tailored Audiences] の宛先がないことを前提としています。

### 手順 1. 認証する [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

デバイスベースの宛先を追加するには、Audience Managerと [!DNL Twitter Tailored Audiences] アカウントをリンクする必要があります。手順は次のとおりです。

1. Audience Managerアカウントにログインして、に移動 **[!DNL Administration > Integrated Accounts]**&#x200B;します。以前に設定したプラットフォームとの統合が設定されている場合は、このページに表示されていることを確認してください。それ以外の場合、ページは空です。
2. **[!DNL Add Account]**&#x200B;をクリックします。
3. 認証ページにリダイレクトするには、選択 [!DNL Twitter Tailored Audiences] してクリック **[!DNL Confirm]** します。![統合プラットフォーム](assets/dbd-integrated-platforms.png)
4. 認証が完了すると、関連する広告主アカウントを表示するAudience Managerにリダイレクトされます。使用する広告主アカウントを選択し、をクリック **[!DNL Confirm]**&#x200B;します。

### 手順 2：新しいデバイスベースの宛先の作成 {#step2-create-new-destination}

Audience Managerとユーザーが [!DNL Twitter Tailored Audiences]リンクされた後、新しい宛先を作成できます。手順は次のとおりです。

>[!NOTE]
>
>既存のデバイスベースの宛先の名前を変更することはできません。宛先を正しく識別するために役立つ名前を指定してください。

1. Audience Managerアカウントにログインし、アクセスして **[!DNL Audience Data > Destinations]**&#x200B;クリック **[!DNL Create Destination]**&#x200B;します。
2. **[!DNL Basic Information]** セクションで **[!DNL Name]** 、および **[!DNL Description]** 新しい宛先を入力し、次の設定を使用します。 ![セットアップ](assets/dbd-new-basic.png)
3. **[!DNL Next]**&#x200B;をクリックします。
4. この宛先に設定する [データのエクスポートラベル](/help/using/features/data-export-controls.md#controls-labels) を選択します。
5. **[!DNL Save]**&#x200B;をクリックします。
6. **[!DNL Segment Mappings]** セクションで、この宛先に送信するオーディエンスセグメントを選択します。
7. 宛先を保存します。

## 既存のTwitter統合をセルフサービス管理に更新 {#update-existing-twitter-integrations}

ユーザーエクスペリエンスを向上し、設定プロセスを効率化するために、Audience Manager UIから独自の設定を行うセルフサービスモデルに [!DNL Twitter Tailored Audiences] 統合をアップグレードします。ここでは、既存のTwitter統合を更新するために必要な手順について説明します。

>[!IMPORTANT]
>
>以下の手順は、Audience [!DNL Twitter Tailored Audiences]Managerコンサルタントまたはカスタマーケアによって設定された既存の統合がある場合にのみ適用されます。セルフサービスモデルへの宛先の完全アップグレードプロセスには、最大5営業日かかる場合があります。それまでの間、宛先はアクティブになり、Audience Managerは引き続きオーディエンスを送信します。
> セルフサービスモデルに移行する前に [、前提条件](#prerequisites) の項目 [!DNL Twitter Tailored Audiences] 番号3を参照してください。

次の手順に従って、既存 [!DNL Twitter Tailored Audiences] の宛先をセルフサービスモデルに移行します。

1. Audience Managerアカウントにログインして、に移動 **[!DNL Administration > Integrated Accounts]**&#x200B;します。
2. **[!DNL Add Account]**&#x200B;をクリックします。
3. 認証ページにリダイレクトするには、選択 [!DNL Twitter Tailored Audiences] してクリック **[!DNL Confirm]** します。![統合プラットフォーム](assets/dbd-integrated-platforms.png)
4. Twitterアカウントで認証されると、関連する広告主アカウントを表示するAudience Managerにリダイレクトされます。使用する広告主アカウントを選択し、をクリック **[!DNL Confirm]**&#x200B;します。

## セグメントマッピングの考慮事項 {#segment-mapping-considerations}

オーディエンスセグメントをTwitterにマッピングする場合は、以下のセグメント命名要件を満たしていることを確認してください。

* 人間が読み取り可能なセグメントマッピング名を指定する。Audience Managerセグメントに使用したものと同じ名前を使用することをお勧めします。
* セグメントおよびセグメントマッピング名ではコンマを使用しないでください。

**例**

* 正しいセグメントまたはマッピング名:"US and European Shoppers";
* 正しくないセグメントまたはマッピング名:"US， European5h0PP3rs".

>[!IMPORTANT]
>
>既にマッピングされているセグメントの名前を変更することはできません。Audience Managerでは、セグメント名を使用して統合のセグメントを正しく識別します。