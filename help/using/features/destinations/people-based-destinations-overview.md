---
description: 'ユーザーベースの宛先を使用して、ファーストパーティのオーディエンスセグメントをユーザーベースの環境に送信します。これらの環境は、そこで表示されるコンテンツを制御する 1 つのエンティティに属する、クローズドなシステムです。これには、顧客アカウントに依存して表示するコンテンツをパーソナライズする、Facebook などのソーシャルプラットフォームが含まれます。 '
seo-description: 'ユーザーベースの宛先を使用して、ファーストパーティのオーディエンスセグメントをユーザーベースの環境に送信します。これらの環境は、そこで表示されるコンテンツを制御する 1 つのエンティティに属する、クローズドなシステムです。これには、顧客アカウントに依存して表示するコンテンツをパーソナライズする、Facebook などのソーシャルプラットフォームが含まれます。  '
seo-title: People-Based Destinations の概要とユースケース
solution: Audience Manager
title: 概要とユースケース
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# 概要とユースケース {#overview-use-cases}

[!DNL People-Based Destinations] を使用して、ファーストパーティのオーディエンスセグメントをユーザーベースの環境に送信します。これらの環境は、そこで表示されるコンテンツを制御する 1 つのエンティティに属する、クローズドなシステムです。これには、顧客アカウントに依存して表示するコンテンツをパーソナライズする、[!DNL Facebook] などのソーシャルプラットフォームが含まれます。

## 概要 {#overview}

[!DNL People-Based Destinations] enable you to apply segmentation on online and offline data to create audience segments based on [hashed identifiers](people-based-destinations-prerequisites.md#hashing-requirements), such as email addresses or phone numbers. Then, you can send these segments to "walled gardens" such as [!DNL Facebook], where you can target your audience on the social platforms. [!DNL People-Based Destinations] は、次の場合に役立ちます。

* ハッシュ化された電子メールアドレスに基づいて、プラットフォーム（[!DNL Facebook] など）でオフラインとオンラインのオーディエンスのターゲット設定をおこなう
* Audience Manager の既存のデバイスおよび Cookie のターゲティング機能を補完する
* サードパーティ製データオンボードソリューションに関連するコストを排除する
* カスタムデータオンボーディングワークフローの開発に関連するコストを排除します
* Cookie がない環境でオーディエンスのターゲット設定をおこなう
* 顧客 ID と一致する電子メールアドレスの重複を排除してオーディエンスのターゲット設定をおこなう

You can use [!DNL People-Based Destinations] to segment and target high value customers who may not visited your website, or stop targeting those who have already converted offline. Additionally, you can leverage [!DNL Profile Merge Rules] to combine your offline first-party data with your online first-party data, including customer data from other Adobe Experience Cloud solutions, to optimize your social media advertising efforts.

![pbd-overview](assets/pbd-overview.png)

## 使用可否{#availability}

[!DNL People-Based Destinations] は、Audience Manager のプレミアム統合です。このプレミアム機能を活用するには、アドビの担当者にお問い合わせください。

## People-Based Destinations を使用する理由 {#why-use}

**Audience Manager 内からオーディエンスセグメント全体を管理することで、一貫性のあるクロスチャネルエクスペリエンスを顧客に提供します。**

Audience Manager から、ユーザーベースのチャネルでオーディエンスセグメントをアクティブ化しなかった場合、Web サイトの訪問時に顧客に表示される内容と、[!DNL Facebook] フィードなどに表示される内容が切り離されます。チャネルをまたいで一貫したターゲティングをおこなうと、広告への投資を最適化すると同時に、広告収入を増やすことができます。

**専用データオンボーディングソリューションやカスタムワークフローを使用してオーディエンスを送信しなくても、ユーザーベースのチャネルでオーディエンスにリーチできます。**

他のユーザーベースのチャネルをまたいでオーディエンスをターゲティングする「従来の」方法では、宣伝したいプラットフォームで許可されている形式で顧客データを書き出し、プラットフォームの専用データオンボード方式を使用して、顧客データを広告主アカウントに取り込みます。この作業は、宣伝したい各プラットフォームで、手動で実行する必要があります。さらに、プラットフォームが異なれば、データ形式の要件も異なることがあり、プロセスの煩雑さも増します。

![pbd-overview](assets/pbd-diagram.png)

Through [!DNL People-Based Destinations], Audience Manager helps you centralize your customer data, build audience segments, and activate them across multiple people-based channels. これらをすべては、Audience Manager UI 内から実行できるので、各プラットフォームに手動でデータをアップロードする手間がなくなり、プロセスの貴重な時間を節約できます。

**純粋なオフラインプロファイルからオーディエンスセグメントを作成およびアクティブ化します。**

[!DNL People-Based Destinations] により、デバイスアクティビティに基づいてしかオーディエンスセグメントをアクティブ化できなかった問題が解決されました。[!DNL People-Based Destinations] を使用すれば、独自の [!DNL CRM] の純粋なオフラインデータからセグメントを作成し、ユーザーベースのプラットフォームでアクティブ化することができます。さらに、オフラインデータをAudience Managerで既に持っているデバイスデータと相互に関連付けることができます。

**Audience Manager のデータガバナンスおよびプライバシーコントロールを活用して、顧客データを安全に処理できます。**

[!DNL People-Based Destinations] requires that you only use irreversibly hashed identifiers. This reduces the risk associated with manually uploading customer data into each destination platform.

## ユースケース {#use-cases}

[!DNL People-Based Destinations] をいつどのようにして使用するかを理解しやすくするために、Audience Manager のお客様がこの機能を使用して解決できる、2 つのユースケースの例を以下に示します。

### ユースケース 1 {#use-case-1}

オンライン小売業者は、ソーシャルプラットフォームを通じて既存の顧客にリーチし、以前の注文に基づいてパーソナライズされたオファーを表示したいと願っています。With [!DNL People-Based Destinations], the online retailer can ingest hashed email addresses from their own [!DNL CRM] to Audience Manager, build segments from their own offline data, and send these segments to the social platforms they want to advertise on, optimizing their advertising spending.

### ユースケース 2 {#use-case-2}

航空会社には異なる顧客階層（ブロンズ、シルバー、ゴールド）があり、ソーシャルプラットフォームを通じてパーソナライズされたオファーを各層に提供したいと考えています。この会社は、Audience Managerを使用してWeb サイトの顧客アクティビティを分析します。ただし、航空会社のモバイルアプリを使用していない顧客や、会社のWebサイトにログインしていない顧客もいます。 会社がこれらの顧客に関して持っている識別子は、メンバーシップ ID と電子メールアドレスのみです。

To target them across social media and similar people-based channels, they can onboard the customer data from their [!DNL CRM] into Audience Manager, using the hashed email addresses as identifiers.

Next, they can combine their offline data with their existing online activity traits, to build new audience segments that they can target through [!DNL People-Based Destinations].
