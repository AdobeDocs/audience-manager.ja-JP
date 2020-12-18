---
description: 'People-Based Destinations に関するよくある質問への回答を紹介します。  '
seo-description: 'People-Based Destinations に関するよくある質問への回答を紹介します。  '
seo-title: People-Based Destinations に関する FAQ
solution: Audience Manager
title: People-Based Destinations に関する FAQ
feature: People-Based Destinations
translation-type: ht
source-git-commit: 6e55d8bc5fe2c5cdcdd36107593215288d491331
workflow-type: ht
source-wordcount: '1138'
ht-degree: 100%

---


# People-Based Destinations に関する FAQ {#people-based-destinations-faq}

[!DNL People-Based Destinations] に関するよくある質問への回答

## 使用可否 {#availability}

**Audience Manager アカウントに [!DNL People-Based Destinations] が表示されません。使用可否について知っておく必要がある情報はありますか？**

[!DNL People-Based Destinations] は、購入時に利用可能な Audience Manager のプレミアム機能です。価格と使用可否について詳しくは、アドビのセールス担当者にお問い合わせください。

## データオンボーディング {#data-onboarding}

**顧客の電子メールアドレスを Audience Manager にオンボーディングして、それを [!DNL People-Based Destinations] で使用できるようにするにはどうすればよいですか？**

オフラインデータを [!DNL People-Based Destinations] 用に Audience Manager に取り込む方法は次の 2 つです。

* **ファイルベースの ID 同期を使用する**。ID 同期ファイルの表示形式について詳しくは、「[ID 同期ファイルの名前とコンテンツ要件](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)」を参照してください。この方法を使用すると、[!DNL CRM] データベースから、すべてのハッシュ化された電子メールアドレスをターゲットにすることができます。
* **宣言された ID を使用**&#x200B;して、認証済みの顧客 ID を渡す際にハッシュ化された電子メールアドレスを宣言します。この方法を使用すると、Audience Manager はオンラインで認証されたユーザーの、ハッシュされた電子メールアドレスのみをアクティブにします。Facebook でアクティブ化される電子メールアドレスは、宣言されている ID イベント呼び出しの電子メールアドレスのみです。顧客 ID に関連付けられているその他の電子メールアドレスは、リアルタイムではアクティブ化されません。

**Web フォームやモバイルアプリから、ハッシュ化された電子メールアドレスを収集できますか？それとも、バッチファイルから収集する必要がありますか？**

[宣言された ID](../features/declared-ids.md)と[!DNL ECID]を使用し、Web 認証を通じてハッシュ化された電子メールアドレスを収集できます。バッチファイルを使用すると、認証を通じて送信できないハッシュ化された電子メールアドレス（例：[!DNL CRM] の休止状態のユーザー）を収集したり、ユーザーベースの宛先でそれらをアクティブ化したりできます。

**ハッシュ化された電子メールアドレスを Web フォーム経由で取り込む場合と、バッチファイルを使用してハッシュ化された電子メールアドレスを取り込む場合の違いを教えてください。**

オフラインデータ取り込みは、認証を使用しないユースケースをサポートするように設計されており、すべてのオフライン [!DNL CRM] プロファイルで実行される新しいプロファイル結合ルール（[!UICONTROL All Cross-Device Profiles]）は、[!DNL People-Based Destinations] の一部として利用できます。この方法は、認証されたオーディエンスのオンラインソースからの取り込みを補完するためのものです。

**ハッシュ化された電子メールアドレスを送信または更新できる最大頻度は何ですか。**

* 宣言された ID を使用する場合、Audience Manager はハッシュ化された電子メールアドレスをリアルタイムで宛先に送信します。
* ID 同期ファイルを使用してデータを取り込む場合、Audience Manager はそれらを毎日処理します。

**電子メールアドレスのハッシュが正しく行われているかどうかを確認するにはどうすればよいですか。**

Audience Manager では、未加工の電子メールアドレスを取り込まないので、ハッシュ化が正しく行われたことを検証できません。オンボードデータのハッシュ化方法について詳しくは、「[前提条件と考慮事項](../features/destinations/people-based-destinations-prerequisites.md)」を参照してください。

## プロファイル結合ルール {#profile-merge-rules}

**[!DNL People-Based Destinations] で使用できる新しいプロファイル結合ルールはありますか。**

はい。また、[!DNL People-Based Destinations] を購入するユーザーには、オフラインセグメントに対する新しいプロファイル結合ルールへのアクセス権も付与されます。ルールは [!DNL All Cross-Device Profiles] と呼ばれ、オフラインのみのセグメント化に使用されます。[!DNL People-Based Destinations] に新規登録する場合、これは、3 つの既存の認証ベースのルールとは別に作成できる 4 つ目のプロファイル結合ルールです。

**既存のオーディエンスセグメントを複製してアクティブ化する必要はありますか[!DNL People-Based Destinations]。**

ユースケースによって異なります。ユーザーベースのチャネルで既存のファーストパーティセグメントをアクティブ化する予定がある場合は、新しいセグメントを作成する必要はありません。セグメントをユーザーベースの宛先にマッピングするだけです。

ユーザーベースのチャネルで新しいオフラインオーディエンスをアクティブ化する予定がある場合は、[!DNL All Cross-Device Profiles] 結合ルールを使用して新しいファーストパーティセグメントを作成する必要があります。
>[!NOTE]
>
> セグメントは、ファーストパーティデータによってのみ [!DNL People-Based Destinations] にマッピングできます。アドビの宛先プラットフォームでは、セカンドパーティとサードパーティのデータを使用したセグメントを使用できません。

## マッチ率 {#match-rates}

**[!DNL People-Based Destinations] は、マッチ率またはアドレス可能なオーディエンスを表示できますか。**

いいえ。オーディエンスセグメントを [!DNL People-Based Destinations] に送信する際は、パートナー側でオーディエンスの照合がおこなわれます。アドビはこれらの指標にアクセスできません。Audience Manager には、各宛先で共有可能なオーディエンスの最大数と、セグメントに属するユーザーのリアルタイムでのカウントが表示されます。この情報は、キャンペーンの計画と予測に役立ちます。

**[!DNL People-Based Destinations] を使用したマッチ率を、オーディエンスを宛先プラットフォームに送信する他の方法のマッチ率と理論的に比較するにはどうすればよいですか。**

電子メールアドレスが正しくハッシュ化され、取り込まれていれば、[!DNL People-Based Destinations] と他のメソッドのマッチ率は同じになります。マッチ率が 100％未満となるのは、Audience Manager に取り込んだ電子メールアドレスが、宛先プラットフォームのユーザーベースにある電子メールアドレスと一致しない場合のみです。

**ソーシャルネットワークで使用されている個人用電子メールアドレスとは異なる、業務用の電子メールアドレスを顧客から収集しています。複数の電子メールアドレスをまたいで ID を一致させるにはどうすればよいですか。**

Audience Manager では、ユーザーごとに最大 10 個の電子メールを収集して送信できますが、電子メールアドレスは同期ファイルを使用して取得する必要があります。Audience Manager が電子メールアドレスを宛先プラットフォームに送信した後、その電子メールアドレスを独自のユーザーベースと照合するかどうかは、プラットフォーム次第です。一部のプラットフォームには、Audience Manager からユーザープロファイルに送信されるアドレスを照合する、追加の電子メールアドレスグラフがあります。

## データ書き出しコントロール {#data-export-controls}

**[!DNL Data Export Controls] は [!DNL People-Based Destinations] とどのように連携しますか？**

[!DNL Data Export Controls] は、ユーザーが [!DNL People-Based Destinations] に送信しようとするセカンドパーティおよびサードパーティデータを含むセグメントをブロックします。[!DNL People-Based Destinations] では、ファーストパーティデータのみをターゲティングに使用できます。[!DNL Data Export Controls] は、[!DNL Profile Merge Rules] とデバイスグラフを使用してセグメントをブロックします。[!DNL People-Based Destinations] は適切なデータ書き出しラベルのチェックにチェックが付けられた状態で作成されており、エクスポート設定を上書きすることはできません。

## パートナー固有の質問 {#partner-specific-questions}

### [!DNL Facebook]

**オーディエンスセグメントを [!DNL Facebook] に送信できるようにするには、どうすればよいですか？**

[!DNL People-Based Destinations] を使用してオーディエンスセグメントを [!DNL Facebook] に送信する前に、以下の設定タスクを実行する必要があります。

1. Adobe Experience Cloud ビジネスアカウントを [!DNL Facebook Ad Account] の広告パートナーとして追加します。`business ID=206617933627973` を使用します。詳しくは、「パートナーをビジネスマネージャーに追加する」を参照してください。

   >[!IMPORTANT]
   >
   > Adobe Experience Cloud の権限を設定する場合は、キャンペーンの管理権限を有効にする必要があります。これは、[!DNL People-Based Destinations] 統合に必要です。

1. [!DNL Facebook Custom Audiences Terms of Service] を読んで署名します。これをおこなうには、`https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]` に進みます（`accountID` は [!DNL Facebook Ad Account ID] です）。

**Do [!DNL People-Based Destinations] は、他の [!DNL Facebook] アプリ（[!DNL Instagram] など）でのオーディエンスのターゲット設定をサポートしていますか？**

[!DNL Custom Audiences] でサポートされる [!DNL Facebook] のアプリケーションファミリー（[!DNL Facebook]、[!DNL Instagram]、[!DNL Audience Network] および [!DNL Messenger] など）をまたいで [!DNL People-Based Destinations] を使用できます。キャンペーンを実行するアプリの選択範囲が、[!DNL Facebook Ads Manager] の配置レベルで示されます。

**[!DNL People-Based Destinations] と [!DNL Website Custom Audiences] の違いを教えてください。**

[!DNL People-Based Destinations] では [!DNL Custom Audiences (CA)] と [!DNL Facebook] の統合を活用します。顧客がオーディエンスを [!DNL Facebook] に送信する際に鍵となるのは、[!DNL WCA] 統合と [!DNL CA] 統合の違いです。[!DNL WCA] は [!DNL Facebook] ピクセル（Web サイトのユーザー ID となります）を使用していますが、[!DNL People-Based Destinations] はハッシュ化された電子メールアドレスを使用して [!DNL CA] と統合します。

追加費用なしで、[!DNL URL Destinations] 機能から Audience Manager の [!DNL Facebook] [!DNL WCA] 統合を使用できます。

これら 2 つの統合は補完的です。両方を使用して、オーディエンス対象範囲を改善することができます。例えば、アカウントを登録していない Web サイト訪問者をターゲットにしたい会社は、[!DNL WCA] を使用して見込み客を開拓できますが、[!DNL People-Based Destinations] は、電子メールアドレスを提供しているけれど Web サイトは訪問していない既存の顧客をターゲットにするのに役立ちます。

**[!DNL People-Based Destinations] と [!DNL Facebook] の統合は、資格がなくなったユーザーの対象からの除外をサポートしますか？**

はい。統合では、ユーザーの資格がなくなった場合の [!DNL Facebook] オーディエンスからの削除をサポートします。