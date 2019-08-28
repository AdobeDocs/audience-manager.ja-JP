---
description: '人ベースの宛先に関するよくある質問への回答を紹介します。  '
seo-description: '人ベースの宛先に関するよくある質問への回答を紹介します。  '
seo-title: 人物ベースの宛先FAQ
solution: Audience Manager
title: 人物ベースの宛先FAQ
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 人物ベースの宛先FAQ {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**Audience Managerアカウント[!DNL People-Based Destinations]には表示されません。可用性について知っておく必要はありますか?**

[!DNL People-Based Destinations] は、購入時に利用可能なプレミアムAudience Manager機能です。価格と可用性について詳しくは、アドビのセールス担当者にお問い合わせください。

## データオンボーディング {#data-onboarding}

**顧客の電子メールアドレスをAudience Managerに入力して、それを使用[!DNL People-Based Destinations]できるようにするにはどうすればよいですか。**

オフラインデータをAudience Managerに取り込むには、2つの方法があり [!DNL People-Based Destinations]ます。

* **ファイルベースのID同期**&#x200B;を使用します。ID [同期ファイルの表示形式について詳しくは、ID同期ファイル](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) の名前とコンテンツ要件を参照してください。この方法を使用する場合、 [!DNL CRM] データベースからすべてのハッシュ化された電子メールアドレスをターゲットにすることができます。
* **宣言済みID** を使用して、認証済みの顧客IDを渡すときにハッシュ化された電子メールアドレスを宣言します。この方法を使用すると、Audience Managerはオンラインで認証されたユーザーからのハッシュされた電子メールアドレスのみをアクティブにします。Facebookでアクティブ化される電子メールアドレスは、宣言されているIDイベント呼び出しのもののみです。顧客IDに関連付けられているその他の電子メールアドレスは、リアルタイムではアクティブ化されません。

**Webフォームやモバイルアプリを通してハッシュ化された電子メールアドレスを収集できますか。それとも、バッチファイルにアクセスする必要がありますか。**

宣言済みID [!DNL ECID] を使用 [して、Web認証を通じてハッシュ化された電子メールアドレスを収集](../features/declared-ids.md)できます。バッチファイルを使用すると、認証を通じて送信できないハッシュ化された電子メールアドレス（[!DNL CRM]）を収集したり、ユーザーベースの宛先でアクティブ化したりできます。

**ハッシュ化された電子メールアドレスをWebフォーム経由で取り込み、バッチファイルを使用してハッシュ化された電子メールアドレスを取り込む方法を教えてください。**

オフラインデータ取り込みは、認証を使用しないユースケースをサポートするように設計されており、認証に関係なく[!UICONTROL All Cross-Device Profiles]、すべてのオフライン [!DNL CRM] プロファイルで実行される新しいプロファイル結合ルール（）を使用 [!DNL People-Based Destinations]できます。この方法は、認証されたオーディエンスのオンラインソースからの取り込みを補完するためのものです。

**ハッシュ化された電子メールアドレスを送信または更新できる最大頻度は何ですか。**

* 宣言済みIDを使用する場合、Audience Managerはハッシュ化された電子メールアドレスをリアルタイムで送信先に送信します。
* ID同期ファイルを使用してデータを取り込む場合、Audience Managerはそれらを毎日処理します。

**電子メールアドレスのハッシュが正しく行われているかどうかを確認するにはどうしますか。**

Audience Managerで生の電子メールアドレスを取り込みません。ハッシュが正しく行われたことを検証できません。オンボードデータのハッシュ化方法について詳しくは [、前提条件と考慮事項](../features/destinations/people-based-destinations-prerequisites.md) を参照してください。

## プロファイル結合ルール {#profile-merge-rules}

**使用できる新しいプロファイル結合ルールはあり[!DNL People-Based Destinations]ますか。**

はい。また、オフ [!DNL People-Based Destinations] ラインセグメント用の新しいプロファイル結合ルールへのアクセス権も付与されます。ルールが呼び出さ [!DNL All Cross-Device Profiles] れ、オフラインのみのセグメント化に使用されます。サインアップすると [!DNL People-Based Destinations]、これは、3つの既存の認証ベースのルールとは別に作成できる4つ目のプロファイル結合ルールです。

**既存のオーディエンスセグメントを複製してアクティブ化する必要[!DNL People-Based Destinations]があるか。**

使用例によって異なります。既存のファーストパーティセグメントをユーザーベースのチャネルでアクティブ化する場合は、新しいセグメントを作成する必要はありません。セグメントをユーザーベースの宛先にマップするだけです。

ユーザーベースのチャネルで新しいオフラインオーディエンスをアクティブにする場合は、 [!DNL All Cross-Device Profiles] 結合ルールを使用して新しいファーストパーティセグメントを作成する必要があります。
>[!NOTE]
>
> セグメントは、ファーストパーティデータによってのみマッピング [!DNL People-Based Destinations]できます。アドビの宛先プラットフォームでは、サードパーティおよびサードパーティのデータを使用してセグメントを受け入れません。

## 一致率 {#match-rates}

**一致[!DNL People-Based Destinations]率またはアドレス可能なオーディエンスを表示できますか。**

いいえ。オーディエンスセグメントを送信するとき [!DNL People-Based Destinations]、パートナー側でオーディエンスの一致が発生します。アドビはこれらの指標にアクセスできません。Audience Managerには、各宛先の共有可能な最大オーディエンスと、セグメントに属する人のリアルタイムカウントが表示されます。この情報は、キャンペーンの計画と予測に役立ちます。

**[!DNL People-Based Destinations]理論的には、オーディエンスを宛先プラットフォームに送信する他の方法との一致率をどのように比較しますか。**

電子メールアドレスがハッシュ化およびインジェストされる限り、一致率と他のメソッドの一致率に違い [!DNL People-Based Destinations] はありません。一致率が100%未満の理由は、Audience Managerに取り込んだ電子メールアドレスが宛先プラットフォームのユーザーベースの電子メールアドレスと一致しない場合のみです。

**ソーシャルネットワークで使用されている個人の電子メールアドレスとは異なる、顧客から作業用の電子メールアドレスを収集します。複数の電子メールアドレスにわたってIDを一致させる方法を教えてください。**

Audience Managerでは、ユーザーごとに最大10個の電子メールを収集して送信できますが、電子メールアドレスは同期ファイルを使用してキャプチャする必要があります。Audience Managerが宛先プラットフォームに電子メールアドレスを送信した後、その電子メールアドレスを独自のユーザーベースに対比させることができます。一部のプラットフォームには、Audience Managerからユーザープロファイルに送信されるアドレスと一致する、追加の電子メールアドレスグラフがあります。

## データ書き出しコントロール {#data-export-controls}

**[!DNL Data Export Controls][!DNL People-Based Destinations]使用方法**

[!DNL Data Export Controls] は、ユーザーが送信しようとした第2および第三者のデータを含むセグメントをブロック [!DNL People-Based Destinations]します。[!DNL People-Based Destinations] のみを使用して、ターゲティングにファーストパーティデータを使用できます。[!DNL Data Export Controls] は、デバイスグラフ [!DNL Profile Merge Rules] を使用してセグメントをブロックします。[!DNL People-Based Destinations] が作成された場合、適切なデータエクスポートラベルを使用して作成され、エクスポート設定を上書きすることはできません。

## パートナー固有の質問 {#partner-specific-questions}

### [!DNL Facebook]

**オーディエンスセグメントを送信できるようにするには、どうすれば[!DNL Facebook]よいですか。**

オーディエンスセグメントの送信 [!DNL People-Based Destinations] に使用する [!DNL Facebook]前に、以下の設定タスクを実行する必要があります。

1. Adobe Experience Cloudビジネスアカウントを広告パートナーとして追加 [!DNL Facebook Ad Account]します。 `business ID=206617933627973`. 詳しくは、「パートナーをビジネスマネージャーに追加」を参照してください。

   >[!IMPORTANT]
   >
   > Adobe Experience Cloudの権限を設定する場合は、キャンペーンの管理権限を有効にする必要があります。これは [!DNL People-Based Destinations] 統合に必要です。

1. 読み取りと署名 [!DNL Facebook Custom Audiences Terms of Service]を行います。これを行うには、先 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`に進み `accountID`[!DNL Facebook Ad Account ID]ます。

**他のアプリでのオーディエンスのターゲット設定[!DNL People-Based Destinations][!DNL Facebook]をサポート[!DNL Instagram]しているか。**

[!DNL People-Based Destinations] サポート [!DNL Facebook]対象のアプリケーションのファミリーを使用する [!DNL Custom Audiences]ことができ [!DNL Facebook][!DNL Instagram][!DNL Audience Network][!DNL Messenger]ます。キャンペーンを実行するアプリの選択範囲が、の配置レベルで示さ [!DNL Facebook Ads Manager]れます。

**[!DNL People-Based Destinations]と[!DNL Website Custom Audiences]との違い**

[!DNL People-Based Destinations][!DNL Custom Audiences (CA)][!DNL Facebook]との統合を利用できます。顧客がオーディエンス [!DNL WCA][!DNL CA] を送信する際に使用するキーは、両者の違い [!DNL Facebook]です。[!DNL WCA][!DNL Facebook] は、ハッシュ化された電子メールアドレスを使用する際 [!DNL People-Based Destinations] に、ピクセル（WebサイトのユーザーID）を使用 [!DNL CA]します。

追加費用なしでAudience Managerの [!DNL Facebook][!DNL WCA] 統合 [!DNL URL Destinations] を使用できます。

これら2つの統合は補完的です。両方を使用して、オーディエンスのカバーを向上させることができます。例えば、会社 [!DNL WCA] がアカウントを登録していないWebサイト訪問者をターゲットにしたい場合に、貴社の電子メールアドレス [!DNL People-Based Destinations] を指定したがWebサイトを訪問していない既存の顧客をターゲットにするのに役立ちます。
