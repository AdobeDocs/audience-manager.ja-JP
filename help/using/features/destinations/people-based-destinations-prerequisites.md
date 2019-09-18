---
description: '人ベースの宛先に登録する前に満たす必要がある顧客要件の概要を以下に示します。  '
seo-description: '人ベースの宛先に登録する前に満たす必要がある顧客要件の概要を以下に示します。  '
seo-title: 人ベースの宛先の前提条件と考慮事項
solution: Audience Manager
title: 前提条件と考慮事項
translation-type: tm+mt
source-git-commit: f3fe6abe913d98549ae6c090a2d5f721485308c2

---


# 前提条件と考慮事項 {#prerequisites-considerations}

新規登録する前に満たす必要がある顧客の要件の概要を以下に示します [!DNL People-Based Destinations]。

>[!IMPORTANT]
> 実装段階に進む前に、この記事をよく読んでください。

## ユーザーベースの宛先へのサインアップ {#signing-up}

[!DNL People-Based Destinations] は、ソーシャルネットワーク上のカスタマイズされたオファーや電子メールマーケティングを使用してオーディエンスをターゲット化することで、人ベースの環境でファーストパーティのオーディエンスセグメントをアクティブ化でき、Audience Managerのエクスペリエンスを強化するプレミアム機能です。

このプレミアム機能を利用するには、アドビの担当者にお問い合わせください。

## パートナー固有の前提条件 {#partner-prerequisites}

### [!DNL Facebook]

を使用してオーディエン [!DNL People-Based Destinations] スセグメントをに送信する前に、 [!DNL Facebook]次の要件を満たしていることを確認します。

1. 使用す [!DNL Facebook] る広告アカウントに対し **て** 、「キャンペーンを管理」権限を有効にする必要があります。
1. Adobe Experience cloudビジネス **アカウントを** 、広告パートナーとして貴社に追加しま [!DNL Facebook Ad Account]す。  `business ID=206617933627973`. 詳しくは [、「Add Partners to Your Business Manager](https://www.facebook.com/business/help/708679622611131) 」を参照してください。
   >[!IMPORTANT]
   > Adobe Experience cloudの権限を設定する場合は、「キャンペーンを管理」権限を有効にする **必要があります** 。 これは統合に必要で [!DNL People-Based Destinations] す。
1. サービス規約を読んで [!DNL Facebook Custom Audiences] 署名します。 これを行うには、に進み、 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`どこに `accountID` いる [!DNL Facebook Ad Account ID]。

## データオンボーディング {#data-onboarding}

のデータインジェストで [!DNL People-Based Destinations] は、現在、1回のバッチ転送で、1つの顧客ID()にリンクされた最大10個のハッシュ化された電子メ[!DNL CRM ID]ールアドレスをサポートしています。 1つの顧客IDにリンクされた10個を超えるハッシュ化された電子メールアドレスをアップロードすると、Audience Managerでそのうち10個が特定の順序で取り込まれなくなります。

1つの顧客IDにリンクされた、10を超えるハッシュ化された電子メールアドレスを複数のバッチ転送でアップロードすると、Audience Managerで、追加された最新の10個の電子メールアドレスが保持されます。

## データのプライバシー {#data-privacy}

電子メー [!DNL People-Based Destinations] ルアドレスに基づいてオーディエンスをターゲット設定できますが、直接識別可能な訪問者情報がAudience Managerに到達することはありません。 データのオンボーディングフェーズでは、使用する予定の電子メールアドレスがアルゴリズムとハッシュ化されていることを確認する必要が [!DNL SHA256] あります。 そうしないと、で使用できなくなります [!DNL People-Based Destinations]。

## データのハッシュと暗号化 {#data-hashing-encryption}

暗号化は双方向関数です。 また、暗号化された情報は、正しい復号鍵を用いて復号化することもできる。 Audience Managerのコンテキストでデータを暗号化すると、個人を特定できる情報の暗号化された形式も復号化され、機密性の高い顧客データが表示されるので、プライバシーに関する深刻なリスクが生じます。 暗号化とは異なり、ハッシュ化さ [!DNL People-Based Destinations] れたデータを使用するように設計されており、ターゲット設定に使用する顧客データを保護します。

ハッシュは、入力をスクランブルして一意の結果を生成する一方向の関数です。 例えば、適切なハッシュアルゴリズムを使用す [!DNL SHA256]ることで、ハッシュ関数を逆にして、スクランブルされていない情報を表示する方法はありません。 Audience Managerにオンボードする電子メールアドレスは、アルゴリズムでハッシュ化する必要があ [!DNL SHA256] ります。 この方法では、個人を特定できる情報がAudience Managerに届かず、顧客データを安全に保つことができます。

## ハッシュ要件 {#hashing-requirements}

電子メールアドレスをハッシュする場合は、次の要件を満たしていることを確認します。

* 電子メール文字列の先頭と末尾のスペースをすべて削除します。例： `johndoe@example.com`違う `<space>johndoe@example.com<space>`。
* ハッシュ化された文字列がすべて小文字であることを確認します。例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`違う `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`。
* 文字列を塩漬けにしないでください。

Adobe Experience cloudでは、Experience Cloud IDサービスを使用して顧客IDをハッシュ化するオプションが提供されます。 ECIDを使用して顧客IDをハッシュ化する方法について詳しくは、 [SHA256 「setCustomerIDsのハッシュのサポート](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) 」を参照してください。

## ユーザー権限の取得 {#obtaining-user-permission}

ユーザ [!DNL People-Based Destinations] ーベースのチャネルでファーストパーティのオーディエンスデータをアクティブにするのに役立つので、広告用にデータをどのように使用するかを顧客に知らせるのは責任があります。

新規登録する前に、顧 [!DNL People-Based Destinations]客の情報を広告用に使用する前に、顧客の同意を必ず取得してください。

顧客が広告キャンペーンのオプトアウトを希望する場合は、Audience Managerがこれ以上データを収集できないようにする方法について [](../../overview/data-security-and-privacy/opt-out-management.md) 、「オプトアウトの管理」を参照してください。

## ファーストパーティデータのアクティブ化の強制 {#enforcing-first-party-activation}

を使用する場合、フ [!DNL People-Based Destinations]ァーストパーティデータを使用して、ユーザーベースのチャネルのオーディエンスセグメントをアクティブ化することのみできます。 ユーザーベースのチャネルでのオーディエンスのアクティブ化には、サードパーティまたはサードパーティのデータを使用できません。

## 宣言済みIDターゲティングを使用したオンボード認証済みハッシュID {#onboard-authenticated-declared-id}

Audience Managerにオフラインデータを取り込むには、次の2つの方法がありま [!DNL People-Based Destinations]す。

* [バッチデータを](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Audience Managerに送信して、ハッシュ化された電子メールアドレスを取り込みます。 この方法を使用すると、でデータベースのハッシュ化された電子メールアドレスをすべて使 [!DNL CRM] 用できま [!DNL People-Based Destinations]す。 また、この方法を使用する場合は、ハッシュ化された電子メールアドレスをオンボード特性に対して修飾す [ることもできま](../traits/trait-qualification-reference.md)す。
* 認証済み [顧客IDを渡す際に](../declared-ids.md) 、ハッシュ化された電子メールアドレスを宣言するには、宣言済みIDを使用します。 この方法を使用する場合、Audience Managerは、オンラインで認証されたユ [!DNL People-Based Destinations] ーザーからハッシュ化された電子メールアドレスにのみ送信します。 Facebookを通じてアクティブ化された電子メールアドレスは、宣言されたIDイベント呼び出しの中のアドレスのみです。 顧客IDに関連付けられた他の電子メールアドレスは、リアルタイムで送信されません。
