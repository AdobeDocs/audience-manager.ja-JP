---
description: 「人ベースの場所」は、顧客データの構造に応じて複数の導入戦略を提供します。この記事では、シナリオに応じて、「人ベースの宛先」に従う必要のある実装手順の概要を説明します。
seo-description: '「人ベースの場所」は、顧客データの構造に応じて複数の導入戦略を提供します。この記事では、シナリオに応じて、「人ベースの宛先」に従う必要のある実装手順の概要を説明します。  '
seo-title: 人ベースの宛先導入ガイダンス
solution: Audience Manager
title: 導入ガイダンス
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# 導入ガイダンス {#implementation-guidance}

[!DNL People-Based Destinations] には、顧客データの構造に応じて複数の実装方法があります。この記事では、シナリオに応じて実行する必要のある実装手順の [!DNL People-Based Destinations]概要を説明します。

## 概要 {#overview}

Audience [!DNL People-Based Destinations] Managerの複数のセクションについての設定は、Audience Managerに既に存在する顧客データの種類と、実行するオーディエンスのターゲット設定の種類に応じて、異なる設定およびデータオンボードメソッドが必要です。

>[!IMPORTANT]
> 設定 [!DNL People-Based Destinations]する前に、必ずこの記事を注意深く読んでください。このガイドを読んだ後、有効にするシナリオを明確に理解 [!DNL People-Based Destinations]する必要があります。

使用する前に明確にする必要のある6つの実装面 [!DNL People-Based Destinations]があります。この記事では、現在の設定が何であるかを把握し、シナリオの実装手順を正確に進めることができます。

![pbd- implementation](assets/pbd-implementation.png)

## 1. 使用例の定義 {#defining-your-use-case}

導入 [!DNL People-Based Destinations]を始める前に、この機能を使用する使用事例を明確に定義する必要があります。オーディエンス [!DNL People-Based Destinations] アクティビティに基づいて、オーディエンスを2つの方法でターゲット化できます。

**A) オンラインおよびオフラインのユーザーアクティビティに基づくオーディエンスのターゲット設定**。このシナリオでは、Audience Managerから既存のオーディエンスデータを内部 [!DNL CRM] システムのデータと結合し、結果のオーディエンスセグメントを送信 [!DNL People-Based Destinations]します。以下に、このシナリオを示します。

会社の航空会社である航空会社は、異なる顧客層（ブロンズ、シルバー、ゴールド）を持ち、ソーシャルプラットフォームを通じてパーソナライズされたオファーを提供する必要があります。Audience Managerを使用して、Webサイトの顧客アクティビティを分析します。ただし、すべての顧客が航空会社のモバイルアプリを使用するわけではなく、一部の顧客が会社のWebサイトにログインしていることもありません。顧客データは、主にメンバーシップIDと電子メールアドレスに制限されています。

ソーシャルメディアや類似のユーザーベースのチャネルにわたってターゲットを絞るには、 [ハッシュ化された電子メールアドレスをAudience Manager](people-based-destinations-prerequisites.md) に取り込んで、それらを既存のオンラインアクティビティの特性と組み合わせて、新しいオーディエンスセグメントを構築できます。次に、これらのセグメントを使用してオーディエンスをターゲット [!DNL People-Based Destinations]化できます。

**B) オフラインユーザーアクティビティのみに基づくオーディエンスターゲット**&#x200B;設定。このシナリオでは、お客 [!DNL CRM] 様のシステムには顧客の電子メールアドレスやその他の顧客属性が含まれていますが、お客様のWebサイトについてはまったくアクションがないので、Audience Managerで顧客アクティビティをお持ちではありません。以下に、このシナリオを示します。

通信サービスプロバイダである会社は、顧客データを電子メールアドレスや購入した通信プランなどの内部で保持 [!DNL CRM]します。ソーシャルプラットフォーム内の既存の顧客をターゲットにして、既存の購読に基づいてアップグレードパッケージを提供する必要があります。これを行うには、ハッシュ化された顧客電子メールアドレスをAudience Managerに取り込み、既存の顧客購読に基づいてセグメントを作成します。その後、これらのセグメントを送信して、パーソナライズ [!DNL People-Based Destinations] されたオファーを顧客にターゲット設定することができます。

## 2. ターゲット設定された電子メールアドレスのタイプの定義 {#define-target-email}

導入戦略を定義する2つ目の手順では、対象とする顧客電子メールアドレスの種類を決定します。

**A) 認証済みの電子メールアドレスに基づくオーディエンスのターゲット**&#x200B;設定。このシナリオでは、ユーザーは複数の電子メールアドレスに関連付けられた複数のアカウントを持ち、Webサイト上で認証される電子メールアドレスのみに基づいて、パーソナライズされたオファーをターゲットにすることができます。

**B) 関連するすべての電子メールアドレスに基づくオーディエンスのターゲット**&#x200B;設定。このシナリオでは、ユーザーに複数の電子メールアドレスに関連付けられた複数のアカウントがあり、認証されたアクティビティに関係なく、関連するすべての電子メールアドレスにわたってターゲットを設定する必要があります。

## 3. お客様ID（CRM ID）の種類を特定する {#identify-customer-id}

イン [!DNL People-Based Destinations] ターゲティング対象のオーディエンスを使用するには、 [お客様の電子メールアドレスのSHA256ハッシュ](people-based-destinations-prerequisites.md) バージョンを送信する必要があります。既存のAudience Manager設定によっては、次の2つのシナリオのいずれかになります。

**A) Audience Managerの顧客ID（[DPUUID](../../reference/ids-in-aam.md)）は、既に小文字の電子メールアドレスです**。このシナリオでは、これらの既存のIDを使用して、オーディエンスのターゲットを設定 [!DNL People-Based Destinations]できます。

**B) Audience Managerの顧客ID（[DPUUID](../../reference/ids-in-aam.md)）は、小文字の電子メールアドレス**&#x200B;ではありません。このシナリオでは、既存の顧客IDは送信できません [!DNL People-Based Destinations]。使用 [!DNL People-Based Destinations]するには、既存の顧客IDと、お客様の電子メールアドレスのハッシュ化された様々なバージョンのID同期を実行する必要があります。これは、ファイルベースのID同期を使用 [する](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) か、宣言済みIDを使用 [して実行](../declared-ids.md)します。

## 4. 特性選定 {#trait-qualification}

オーディエンスを正確にターゲット設定する [!DNL People-Based Destinations]には、実行するオーディエンスのターゲット設定のタイプに応じて、ユーザーがルールベースまたはオンボーブの特性に適合する必要があります。

**A) ルールベースの特性について、顧客IDとデバイスIDをリアルタイムで修飾**&#x200B;します。このオプションは、1から [のAケースの使用に適用されます。使用事例](people-based-destinations-workflow.md#defining-your-use-case)の定義を参照してください。オンラインおよびオフラインのアクティビティに基づいてオーディエンスをターゲット設定する場合は、ルールベースの特性について [、オーディエンスの資格を得ることができます](../traits/trait-qualification-reference.md)。

**B) インバウンドデータファイルを介して、顧客IDに対するインサイトが提供**&#x200B;されます。このオプションは、1から [のBの使用に適用されます。使用事例](people-based-destinations-workflow.md#defining-your-use-case)の定義を参照してください。純粋なオフラインアクティビティに基づいてオーディエンスをターゲット設定する場合、受信データファイルを通じ [てオンボーブされた特性の顧客IDを有効にする必要](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)があります。

## 5. データソースの作成またはラベル付けと、ハッシュ化された電子メールアドレス {#create-label-data-sources}

Audience Managerにある顧客IDのタイプによって異なります（3を参照 [）。顧客ID（CRM ID）の種類を特定](people-based-destinations-workflow.md#identify-customer-id)するには、次のいずれかのシナリオを実行します。

**A) 既存のデータソースにラベル**&#x200B;を付けます。このオプションは、Audience Managerの顧客ID（[DPUUID](../../reference/ids-in-aam.md)）が既に小文字の電子メールアドレスであるシナリオに適用されます。この状況では、データソースとしてIDを保存するデータソースにラベルを付ける [!DNL PII] 必要があります。データソースの設定について詳しくは、 [データソースの設定](../datasources-list-and-settings.md) を参照してください。実行する必要があるのは、個人を特定できる情報オプションに関連付けられていないことを確認することです。

**B) 新しいデータソースを作成**&#x200B;します。このオプションは、Audience Managerの顧客ID（[DPUUID](../../reference/ids-in-aam.md)）がハッシュ化された電子メールアドレスではないシナリオに適用されます。この場合、新しいクロスデバイスデータソースを作成し、ハッシュ化された電子メールアドレスをそのデータに対して埋め込んでおく必要があります。これは、次の2つの方法で実行できます。

* ファイルベースのID同期を使用します。ID [同期ファイルの表示形式について詳しくは、ID同期ファイル](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) の名前とコンテンツ要件を参照してください。この方法を使用する場合、 [!DNL CRM] データベースからすべてのハッシュ化された電子メールアドレスをターゲットにすることができます。
* [宣言済みID](../declared-ids.md) を使用して、認証済みの顧客IDを渡すときにハッシュ化された電子メールアドレスを宣言します。この方法を使用すると、Audience Managerはオンラインで認証されたユーザーからのハッシュされた電子メールアドレスのみをターゲットにします。Facebookを通じてターゲット設定される電子メールアドレスは、宣言されているIDイベント呼び出しのもののみです。顧客IDに関連付けられているその他の電子メールアドレスは、リアルタイムではアクティブ化されません。

## 6. セグメントの結合ルールの使用 {#use-profile-merge-rules}

使用例に応じて（1を参照 [）。使用事例の定義](people-based-destinations-workflow.md#defining-your-use-case)には、セグメントに使用 [!DNL Profile Merge Rules] する2つの方法があります。

**A) 既存のものを使用[!DNL Profile Merge Rules]**&#x200B;します。このオプションは、最初の使用事例に適用されます（オンラインおよびオフラインのユーザーアクティビティに基づくオーディエンスのターゲット設定）。このシナリオでは、Audience Managerで既存の顧客アクティビティを持ち、セグメントで使用したプロファイル結合ルールを少なくとも1つ定義しています。この場合、新規 [!DNL Profile Merge Rules]作成する必要はありません。

**B)[!DNL All Cross-Device Profiles]新しい結合ルール**&#x200B;の作成を参照してください。このオプションは、2番目の使用例（オフラインユーザーアクティビティのみに基づくオーディエンスターゲット）に適用されます。このシナリオでは、オフラインの顧客データをAudience Manager [!DNL CRM] から取得し、そのデータからセグメントを作成します。これを行うには、4番目に新しいプロファイル結合ルールを [!DNL People-Based Destinations] 導入 **[!DNL All Cross-Device Profiles]**&#x200B;します。これは、純粋なオフラインデータをセグメント化するときに使用する必要があるルールです。
