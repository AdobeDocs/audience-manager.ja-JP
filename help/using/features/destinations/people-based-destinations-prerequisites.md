---
description: 'People-Based Destinations に新規登録する前に満たす必要のある顧客要件の概要については、以下をお読みください。  '
seo-description: 'People-Based Destinations に新規登録する前に満たす必要のある顧客要件の概要については、以下をお読みください。  '
seo-title: People-Based Destinations の前提条件と考慮事項
solution: Audience Manager
title: 前提条件と考慮事項
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# 前提条件と考慮事項 {#prerequisites-considerations}

>[!IMPORTANT]
>この記事には、この機能の設定と使用方法を説明する製品ドキュメントが含まれています。 法律上の助言は何も含まれません。 法律上の手引きについては、自分の弁護士にお問い合わせください。

[!DNL People-Based Destinations] に新規登録する前に満たす必要のある顧客要件の概要については、以下をお読みください。

>[!IMPORTANT]
> 実装段階に進む前に、この記事をよくお読みください。

## People-Based Destinations への新規登録 {#signing-up}

[!DNL People-Based Destinations] は、ソーシャルネットワーク上のカスタマイズされたオファーや電子メールマーケティングを使用してオーディエンスをターゲット化することで、Audience Managerのエクスペリエンスを強化するプレミアム機能です。

このプレミアム機能を活用するには、アドビの担当者にお問い合わせください。

## パートナー固有の前提条件 {#partner-prerequisites}

### [!DNL Facebook]

Before you can use [!DNL People-Based Destinations] to send your first-party audience segments to [!DNL Facebook], make sure you meet the following requirements:

1. お使いの [!DNL Facebook] ユーザーアカウントで、使用するプランの広告アカウントに対する&#x200B;**キャンペーンの管理**&#x200B;権限が有効になっている必要があります。
1. **Adobe Experience Cloud** ビジネスアカウントを [!DNL Facebook Ad Account] の広告パートナーとして追加します。`business ID=206617933627973` を使用します。See [Add Partners to Your Business Manager](https://www.facebook.com/business/help/708679622611131) for details.
   >[!IMPORTANT]
   > Adobe Experience Cloud の権限を設定する場合は、**キャンペーンの管理**&#x200B;権限を有効にする必要があります。これは、[!DNL People-Based Destinations] 統合に必要です。
1. [!DNL Facebook Custom Audiences] 利用規約を読み、署名します。これをおこなうには、`https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]` に進みます（`accountID` は [!DNL Facebook Ad Account ID] です）。

## データオンボーディング {#data-onboarding}

[!DNL People-Based Destinations] のデータ取り込みでは現在、バッチ転送 1 回あたり、1 つの顧客 ID（[!DNL CRM ID]）とリンクされている最大 10 個のハッシュ化された電子メールアドレスをサポートしています。1 つの顧客 ID にリンクされている 10 を超えるハッシュ化された電子メールアドレスをアップロードすると、Audience Manager が、それらのうち 10 個の電子メールアドレスを取り込みます（特定の順序はありません）。

1 つの顧客 ID にリンクされている 10 を超えるハッシュ化された電子メールアドレスを、複数の一括転送でアップロードすると、Audience Manager は最近追加された 10 個の電子メールアドレスを保持します。

## データのプライバシー {#data-privacy}

自分が [!DNL People-Based Destinations] アップロードしたハッシュ化された電子メールアドレスに基づいてオーディエンスをターゲット設定できますが、直接識別可能な訪問者情報をAudience Managerにアップロードすることは禁止されたままです。 オンボーディング段階で、使用する予定の電子メールアドレスが [!DNL SHA256] アルゴリズムでハッシュ化されていることを確認する必要があります。そうでない場合、[!DNL People-Based Destinations] で使用することはできません 。

## データのハッシュと暗号化 {#data-hashing-encryption}

暗号化は双方向関数です。暗号化された情報は、復号化キーを使用して復号化することもできます。Audience Managerのコンテキストでデータを暗号化すると、個人を特定できる情報の暗号化も復号化できるので、深刻なリスクを伴います。 As opposed to encryption,  are designed to work with hashed data instead.[!DNL People-Based Destinations]

ハッシュは、入力をスクランブル処理して一意の結果を生成する一方向関数です。[!DNL SHA256] などの適切なハッシュアルゴリズムを使用した場合、ハッシュ関数を反転させてスクランブルされていない情報を表示する方法はありません。Audience Manager にオンボーディングする電子メールアドレスは、[!DNL SHA256] アルゴリズムでハッシュ化する必要があります。This way, you can ensure that no unhashed email addresses reach Audience Manager.

## ハッシュ要件 {#hashing-requirements}

電子メールアドレスをハッシュ化する場合は、以下の要件に従ってください。

* 電子メール文字列から先頭および末尾の空白文字をすべてトリミングします。例：`johndoe@example.com`（`<space>johndoe@example.com<space>` ではない）
* ハッシュ化された文字列がすべて小文字であることを確認します。例：`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`（`55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149` ではない）
* 文字列にソルトを使用しないでください。

Adobe Experience Cloud では、Experience Cloud IDサービスで顧客 ID をハッシュ化できます。See SHA256 Hashing Support for setCustomerIDs for detailed information on how to use ECID to hash customer IDs.[](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html)

## ユーザー権限の取得 {#obtaining-user-permission}

Since [!DNL People-Based Destinations] helps you activate first-party audience data in people-based channels, it is your responsibility to inform and obtain any necessary consents from your customers of how you will use their data for advertising or other purposes.

[!DNL People-Based Destinations] に新規登録する前に必ず、顧客の同意を得てから広告目的で顧客の情報を使用するようにしてください。

広告キャンペーンのオプトアウトをおこなう場合は、Audience Manager を停止してそれ以降のデータを収集する停止方法について詳しくは、「[オプトアウト管理](../../overview/data-security-and-privacy/opt-out-management.md)」を参照してください。

## ファーストパーティデータのアクティブ化を強制する{#enforcing-first-party-activation}

[!DNL People-Based Destinations] を使用する際は、ファーストパーティデータを使用して、ユーザーベースのチャネルでオーディエンスセグメントをアクティブ化できます。ユーザーベースのチャネルでオーディエンスのアクティブ化にセカンドパーティデータやサードパーティデータを使用することはできません。

## 宣言済み ID のターゲティングを介して認証済みの ID のオンボーディングをおこなう{#onboard-authenticated-declared-id}

オフラインデータを [!DNL People-Based Destinations] 用に Audience Manager に取り込む方法は次の 2 つです。

* Audience Manager に[バッチデータを送信](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)して、ハッシュ化された電子メールアドレスを取り込みます。With this method, you can choose to use the hashed email addresses from your [!DNL CRM] database in [!DNL People-Based Destinations]. さらに、この方法を使用する場合、[オンボード特性](../traits/trait-qualification-reference.md)のハッシュ化された電子メールアドレスも絞り込みます。
* [宣言済み ID を使用](../declared-ids.md)して、認証済みの顧客 ID を渡す際にハッシュ化された電子メールアドレスを宣言します。When using this method, Audience Manager, on your behalf, only sends to [!DNL People-Based Destinations] the hashed email addresses from users who have authenticated online. ユーザーベースのチャネルを通じてアクティブ化された電子メールアドレスは、宣言されたIDイベント呼び出しの中のアドレスのみです。 顧客 ID に関連付けられているその他の電子メールアドレスは、リアルタイムでは送信されません。
