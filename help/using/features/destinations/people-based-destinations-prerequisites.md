---
description: '以下に、Peopleベースの宛先にサインアップする前に満たす必要のある顧客要件の概要を示します。  '
seo-description: '以下に、Peopleベースの宛先にサインアップする前に満たす必要のある顧客要件の概要を示します。  '
seo-title: 人に基づく宛先の前提条件と考慮事項
solution: Audience Manager
title: 前提条件と考慮事項
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# 前提条件と考慮事項 {#prerequisites-considerations}

サインアップする前に満たす必要のある顧客要件の概要については、以下をお読み [!DNL People-Based Destinations]ください。

>[!IMPORTANT]
> 実装段階に進む前に、この記事をよく読んでください。

## 人物ベースの宛先へのサインアップ {#signing-up}

[!DNL People-Based Destinations] は、ユーザーベースの環境でファーストパーティのオーディエンスセグメントをアクティブ化することで、オーディエンスマネージャーのエクスペリエンスを強化するプレミアム機能です。これにより、ソーシャルネットワーク上または電子メールマーケティングによって、カスタマイズされたオファーを使用してオーディエンスをターゲット設定できます。

サインアップ方法について詳しくは、アドビのセールス担当者にお問い合わせ [!DNL People-Based Destinations]ください。

## パートナー固有の前提条件 {#partner-prerequisites}

### [!DNL Facebook]

オーディエンスセグメントの送信 [!DNL People-Based Destinations] に使用する前に、以下 [!DNL Facebook]の要件を満たしていることを確認してください。

1. [!DNL Facebook] 使用する予定の広告アカウントに対して **、ユーザーアカウントに「管理キャンペーン** 」権限が有効になっている必要があります。
1. Adobe **Experience Cloud** ビジネスアカウントを広告パートナーとして追加 [!DNL Facebook Ad Account]します。 `business ID=206617933627973`. 詳しくは、「パートナー [をビジネスマネージャー](https://www.facebook.com/business/help/708679622611131) に追加」を参照してください。
   >[!IMPORTANT]
   > Adobe Experience Cloudの権限を設定する場合は、キャンペーンの **管理** 権限を有効にする必要があります。これは [!DNL People-Based Destinations] 統合に必要です。
1. サービス [!DNL Facebook Custom Audiences] 利用規約を読み、署名します。これを行うには、先 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`に進み `accountID`[!DNL Facebook Ad Account ID]ます。

## データオンボーディング {#data-onboarding}

現在のデータ取り込みで [!DNL People-Based Destinations] は、1つの顧客ID（[!DNL CRM ID]）にリンクされている、1つのバッチ転送につき最大10のハッシュ化された電子メールアドレスをサポートしています。1つの顧客IDにリンクされている10を超えるハッシュ化された電子メールアドレスをアップロードすると、Audience Managerによって10個のハッシュされた電子メールアドレスが、特定の順序ではなくインジェストされます。

複数のバッチ転送で1つの顧客IDにリンクされている10を超えるハッシュ化された電子メールアドレスをアップロードすると、Audience Managerは追加された最新10個の電子メールアドレスを保持します。

## データのプライバシー {#data-privacy}

電子メールアドレスに基づいてオーディエンスをターゲットにする [!DNL People-Based Destinations] ことができますが、訪問者情報を直接特定することはできません。オンボーディング段階で、使用する予定の電子メールアドレスが [!DNL SHA256] アルゴリズムとハッシュ化されていることを確認する必要があります。それ以外の場合は、で使用できません [!DNL People-Based Destinations]。

## データのハッシュと暗号化 {#data-hashing-encryption}

暗号化は双方向関数です。暗号化された情報は、復号化キーを使用して復号化することもできます。個人的に特定できる情報の暗号化された形式は復号化されることがあるので、Audience Managerのコンテキストでデータを暗号化することで、機密性の高いプライバシーリスクを実現できます。暗号化とは異なり、ターゲティング [!DNL People-Based Destinations] に使用する顧客データを保護するように、ハッシュ化されたデータを使用するように設計されています。

ハッシュは、入力をスクランブルして一意の結果を生成する一方向関数です。適切 [!DNL SHA256]なハッシュアルゴリズムを使用することで、ハッシュ関数を反転してアンスクランブル情報を表示する方法がなくなります。Audience Managerに付属する電子メールアドレスは [!DNL SHA256] 、アルゴリズムとハッシュ化する必要があります。これにより、顧客データの安全性を維持したまま、個人を特定できる情報はAudience Managerに提供されません。

## ハッシュ要件 {#hashing-requirements}

電子メールアドレスをハッシュする場合は、以下の要件に従ってください。

* 電子メール文字列から先頭および末尾の空白文字をすべてトリミングします。例: `johndoe@example.com`; not `<space>johndoe@example.com<space>`;
* ハッシュ化された文字列がすべて小文字であることを確認してください。例: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`; not `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 文字列をソルトしないでください。

Adobe Experience Cloudでは、Experience Cloud IDサービスで顧客IDをハッシュ化できます。顧客 [IDにECIDを使用する方法について詳しくは、setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) のSHA256ハッシュサポートを参照してください。

## ユーザー権限の取得 {#obtaining-user-permission}

ファーストパーティのオーディエンスデータをユーザーベースのチャネルでアクティブ化 [!DNL People-Based Destinations] するのに役立つので、広告目的でのデータの使用方法を顧客に通知することをお勧めします。

入会する前に [!DNL People-Based Destinations]、広告の目的に使用する前に、顧客の同意を必ず入手してください。

広告キャンペーンのオプトアウトを行う場合は、 [Audience Managerを停止してデータを収集する停止方法の詳細に](../../overview/data-security-and-privacy/opt-out-management.md) ついては、オプトアウト管理を参照してください。

## ファーストパーティデータ有効化の強制 {#enforcing-first-party-activation}

使用 [!DNL People-Based Destinations]する場合、ファーストパーティデータを使用して、ユーザーベースのチャネルでオーディエンスセグメントをアクティブ化できます。ユーザーベースのチャネルでオーディエンスのアクティブ化に第2または第三者のデータを使用することはできません。

## 事前に定義された認証済みのID（宣言済みIDターゲティング経由） {#onboard-authenticated-declared-id}

オフラインデータをAudience Managerに取り込むには、2つの方法があり [!DNL People-Based Destinations]ます。

* [ハッシュデータ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) をAudience Managerに送信して、ハッシュ化された電子メールアドレスを取り込みます。この方法を使用すると、データベースからすべてのハッシュ化された電子メールアドレス [!DNL CRM] を使用 [!DNL People-Based Destinations]できます。さらに、この方法を使用する場合、オンボーブされた特性の [ハッシュ化された電子メールアドレスを修飾](../traits/trait-qualification-reference.md)することもできます。
* [宣言済みID](../declared-ids.md) を使用して、認証済みの顧客IDを渡すときにハッシュ化された電子メールアドレスを宣言します。この方法を使用すると、Audience Managerはオンラインで認証されたユーザーからのハッシュされた電子メールアドレスに [!DNL People-Based Destinations] のみ送信されます。Facebookでアクティブ化される電子メールアドレスは、宣言されているIDイベント呼び出しのもののみです。顧客IDに関連付けられているその他の電子メールアドレスは、リアルタイムでは送信されません。
