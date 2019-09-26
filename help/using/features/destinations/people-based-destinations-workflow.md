---
description: People-Based Destinations では、顧客データの構造に応じて、複数の実装戦略を提供します。この記事では、シナリオに応じて、People-Based Destinations について 従う必要のある実装手順の概要について説明します。
seo-description: 'People-Based Destinations では、顧客データの構造に応じて、複数の実装戦略を提供します。この記事では、シナリオに応じて、People-Based Destinations について 従う必要のある実装手順の概要について説明します。  '
seo-title: People-Based Destinations の実装ガイダンス
solution: Audience Manager
title: 実装ガイダンス
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# 実装ガイダンス {#implementation-guidance}

>[!IMPORTANT]
>This article contains product documentation meant to guide you through the setup and usage of this feature. Nothing contained herein is legal advice. Please consult your own legal counsel for legal guidance.

[!DNL People-Based Destinations] では、顧客データの構造に応じて、複数の実装戦略を提供します。この記事では、シナリオに応じて、[!DNL People-Based Destinations] で従う必要のある実装手順の概要について説明します。

## 概要 {#overview}

[!DNL People-Based Destinations] の設定では、Audience Manager に既に存在する顧客データの種類や、実行するオーディエンスターゲティングの種類に応じて、Audience Manager の複数のセクションを使用します。

>[!IMPORTANT]
> [!DNL People-Based Destinations] を設定する前に、必ずこの記事を注意深く読んでください。このガイドを読んだ後、[!DNL People-Based Destinations] で有効にするシナリオについて明確に理解する必要があります。

[!DNL People-Based Destinations] を使用する前に、実装に関する 6 つの側面を明確にしておく必要があります。この記事では、現在の設定を把握し、シナリオの実装手順を正確に進めるのに役立ちます。

![pbd-implementation](assets/pbd-implementation.png)

## 1. 使用例 {#defining-your-use-case}

Before you begin implementing [!DNL People-Based Destinations], you need to clearly define the use case that you will be using this feature for. [!DNL People-Based Destinations] を使用し、オーディエンスアクティビティに基づいて、2 つの方法でオーディエンスのターゲット設定をおこなうことができます。

**A)オンラインとオフラインの組み合わせによるユーザーアクティビティに基づくオーディエンスのターゲティング**。 このシナリオでは、Audience Manager の既存のオーディエンスデータを内部 [!DNL CRM] システムのデータと組み合わせ、結果として得られたオーディエンスセグメントを [!DNL People-Based Destinations] に送信します。以下に、このシナリオの例を示します。

あなたが勤める航空会社には、異なる顧客階層（ブロンズ、シルバー、ゴールド）があり、ソーシャルプラットフォームを通じてパーソナライズされたオファーを各層に提供したいと考えています。Audience Manager を使用して、Web サイトの顧客アクティビティを分析します。ただし、航空会社のモバイルアプリを使用していない顧客や、会社のWebサイトにログインしていない顧客もいます。 顧客データは、主にメンバーシップ ID と電子メールアドレスに限定されています。

To target them across social media and similar people-based channels, you can bring your [hashed email addresses](people-based-destinations-prerequisites.md) into Audience Manager and combine them with your existing online activity traits, to build new audience segments. 次に、これらのセグメントを使用、[!DNL People-Based Destinations] を通じてオーディエンスをターゲティングできます。

**B) Audience targeting based exclusively on your offline user activity.** In this scenario, your [!DNL CRM] system contains your customer email addresses and other customer attributes, but customers have not interacted with your website at all, so you don't have any customer activity in Audience Manager. 以下に、このシナリオの例を示します。

あなたが勤める通信サービスプロバイダーは、社内 [!DNL CRM] に、電子メールアドレスや購入した通信プランなどの顧客データを保持します。ソーシャルプラットフォーム内の既存の顧客をターゲットにして、既存のサブスクリプションに基づいてアップグレードパッケージを提供する場合があります。これを行うには、ハッシュ化された顧客の電子メールアドレスをAudience Managerに取り込み、既存の顧客の購読に基づいてセグメントを作成します。 その後、これらのセグメントを [!DNL People-Based Destinations] に送信して、パーソナライズされたオファーを用いて顧客のターゲット設定をおこなうことができます。

## 2. ターゲット設定された電子メールアドレスのタイプを定義する {#define-target-email}

実装戦略を定義する 2 つ目の手順では、対象とする顧客電子メールアドレスの種類を決定します。

**A)認証済みの電子メールアドレスに基づくオーディエンスのターゲティング**。 このシナリオでは、ユーザーは複数の電子メールアドレスに関連付けられた複数のアカウントを持ち、Web サイト上で認証される電子メールアドレスのみに基づいて、パーソナライズされたオファーを用いて、リアルタイムでターゲット設定をおこなうことができます。

**B) Audience targeting based on all of your associated email addresses**. このシナリオでは、ユーザーは複数の電子メールアドレスと関連付けられた複数のアカウントを持っており、お客様は、認証されたアクティビティに関係なく、関連するすべての電子メールアドレスをまたいでユーザーをターゲットに設定しようとしています。

## 3. 保有している顧客 ID（CRM ID）のタイプを特定する{#identify-customer-id}

[!DNL People-Based Destinations] でオーディエンスのターゲティングをおこなうには、顧客電子メールアドレスの [SHA256 ハッシュ](people-based-destinations-prerequisites.md) バージョンが必要です。既存の Audience Manager 設定に応じて、次の 2 つのシナリオのいずれかになります。

**A）Audience Manager の顧客 ID（[DPUUID](../../reference/ids-in-aam.md)） が、ハッシュ化された小文字の電子メールアドレスになっている場合**。このシナリオでは、これらの既存の ID を使用して、[!DNL People-Based Destinations] でオーディエンスのターゲット設定をおこないます。

**B）Audience Manager の顧客 ID（[DPUUID](../../reference/ids-in-aam.md)） が、ハッシュ化された小文字の電子メールアドレスでない場合**。このシナリオでは、既存の顧客 ID を [!DNL People-Based Destinations] に送信することはできません。[!DNL People-Based Destinations] を使用するには、既存の顧客 ID と、ハッシュ化された小文字バージョンの顧客電子メールアドレスで ID 同期を実行する必要があります。これは、[ファイルベースの ID 同期](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)を使用するか、[宣言済み ID](../declared-ids.md) を使用して実行します。

## 4. 特性認定{#trait-qualification}

[!DNL People-Based Destinations] で正確にオーディエンスのターゲットを絞るには、実行するオーディエンスのターゲット設定のタイプに応じて、ルールベースの特性またはオンボード特性のいずれかに適合している必要があります。

**A)顧客IDとデバイスIDを、ルールに基づく特性にリアルタイムで修飾します**。 このオプションは、「[1.ユースケースの定義](people-based-destinations-workflow.md#defining-your-use-case)」のユースケース Bに適用されます。オンラインとオフラインのアクティビティに基づいてオーディエンスをターゲット設定する予定がある場合は、[ルールベースの特性](../traits/trait-qualification-reference.md)について、既にオーディエンスを絞り込んでいる可能性が高くなります。

**B) Onboard traits against your customer IDs via inbound data files**. このオプションは、[1.ユースケースの定義](people-based-destinations-workflow.md#defining-your-use-case)」のユースケース Bに適用されます。純粋なオフラインアクティビティに基づいてオーディエンスをターゲット設定する場合、[受信データファイル](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)を通じてオンボードされた特性の顧客 ID を認定する必要があります。

## 5. データソースを作成およびラベル付けし、ハッシュ化された電子メールアドレスのオンボーディングをおこなう {#create-label-data-sources}

Audience Manager にある顧客 ID のタイプに応じて（「[3.保有している顧客 ID（CRM ID）のタイプを特定する](people-based-destinations-workflow.md#identify-customer-id)」を参照）、次のいずれかのシナリオから、適したものを選択します。

**A）既存のデータソースにラベルを付ける**。このオプションは、Audience Manager の顧客 ID（[DPUUID](../../reference/ids-in-aam.md)）がハッシュ化された小文字の電子メールアドレスの場合に適用されます。In this situation, what you need to do is label your data source that you store the IDs in as a [!DNL PII] data source. データソースの設定について詳しくは、「[データソースの設定](../datasources-list-and-settings.md)」を参照してください。「Cannot be tied to personally identifiable information」オプションのチェックがオフになっていることを確認する必要があります。

**B）新しいデータソースを作成する**。このオプションは、Audience Manager の顧客 ID（[DPUUID](../../reference/ids-in-aam.md)）がハッシュ化された小文字の電子メールアドレスでない場合に適用されます。この場合、新しいクロスデバイスデータソースを作成し、それに対してハッシュ化された電子メールアドレスをオンボードする必要があります。 これには次の 2 つの方法を使用できます。

* ファイルベースの ID 同期を使用する。ID 同期ファイルの表示形式について詳しくは、「[ID 同期ファイル の名前とコンテンツ要件](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)」を参照してください。When using this method, you can target all of your hashed email addresses from your [!DNL CRM] database.
* Use [declared IDs](../declared-ids.md) to declare your hashed email addresses when passing in authenticated customer IDs. この方法を使用する場合、Audience Managerは、オンラインで認証されたユーザーからのハッシュ化された電子メールアドレスのみをターゲットにします。 人ベースのチャネルでターゲット設定された電子メールアドレスは、宣言されたIDイベント呼び出しの電子メールアドレスのみです。 顧客 ID に関連付けられているその他の電子メールアドレスは、リアルタイムではアクティブ化されません。

## 6 - セグメント化のプロファイル結合ルールを作成する {#use-profile-merge-rules}

ユースケースに応じて（[1.ユースケースの定義](people-based-destinations-workflow.md#defining-your-use-case)を参照）、2 つの方法でセグメント化に [!DNL Profile Merge Rules] を使用できます。

**A）既存の[!DNL Profile Merge Rules]を使用する**。このオプションは、最初のユースケース（オンラインとオフラインのユーザーアクティビティの組み合わせに基づいてオーディエンスのターゲティングをおこなう）に適用されます。このシナリオでは、Audience Managerに既に顧客アクティビティが存在し、セグメント化で使用した少なくとも1つのプロファイル結合ルールが既に定義されています。 この場合、新しく [!DNL Profile Merge Rules] を作成する必要はありません。

**B）新しい[!DNL All Cross-Device Profiles]結合ルールを作成する**。このオプションは、2 番目のユースケース（オフラインのユーザーアクティビティのみに基づいてオーディエンスのターゲティングをおこなう）に適用されます。In this scenario you are bringing your offline customer data from your [!DNL CRM] into Audience Manager, and want to create segments from that data. これをおこなうため、[!DNL People-Based Destinations] では、4 つめのプロファイル結合ルールとなる **[!DNL All Cross-Device Profiles]** を導入します。このルールは、純粋なオフラインデータをセグメント化するときに使用する必要があります。
