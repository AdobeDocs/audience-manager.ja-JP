---
description: 'People-Based Destinations に新規登録する前に満たす必要のある顧客要件の概要については、以下をお読みください。  '
seo-description: 'People-Based Destinations に新規登録する前に満たす必要のある顧客要件の概要については、以下をお読みください。  '
seo-title: People-Based Destinations の前提条件と考慮事項
solution: Audience Manager
title: 前提条件と考慮事項
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 2e32f9ebff487ae8dfb2088ec1bbfcea1daa00a1
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 86%

---


# 前提条件と考慮事項 {#prerequisites-considerations}

>[!IMPORTANT]
>この記事には、この機能の設定と使用方法を説明する製品ドキュメントが含まれています。法的なアドバイスは何も含まれません。法律に関するガイダンスについては、御社の顧問弁護士にアドバイスを求めてください。

[!UICONTROL People-Based Destinations] に新規登録する前に満たす必要のある顧客要件の概要については、以下をお読みください。

>[!IMPORTANT]
> 実装段階に進む前に、この記事をよくお読みください。

## Signing up for [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] は、ソーシャルネットワーク上または電子メールマーケティングで、カスタマイズされたオファーを用いてオーディエンスのターゲティングをおこない、ユーザーベースの環境でファーストパーティのオーディエンスセグメントをアクティブ化することで、Audience Manager のエクスペリエンスを強化するプレミアム機能です。

このプレミアム機能を活用するには、アドビの担当者にお問い合わせください。

## パートナー固有の前提条件 {#partner-prerequisites}

### [!DNL Facebook]

Before you can use [!UICONTROL People-Based Destinations] to send your first-party audience [!UICONTROL segments] to [!DNL Facebook], make sure you meet the following requirements:

1. お使いの [!DNL Facebook] ユーザーアカウントで、使用するプランの広告アカウントに対する&#x200B;**キャンペーンの管理**&#x200B;権限が有効になっている必要があります。
2. **Adobe Experience Cloud** ビジネスアカウントを [!DNL Facebook Ad Account] の広告パートナーとして追加します。`business ID=206617933627973` を使用します。詳しくは、[ビジネスマネージャにパートナーを追加する](https://www.facebook.com/business/help/1717412048538897)を参照してください。
   >[!IMPORTANT]
   > Adobe Experience Cloud の権限を設定する場合は、**キャンペーンの管理**&#x200B;権限を有効にする必要があります。これは、[!UICONTROL People-Based Destinations] 統合に必要です。
3. [!DNL Facebook Custom Audiences] 利用規約を読み、署名します。これをおこなうには、`https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]` に進みます（`accountID` は [!DNL Facebook Ad Account ID] です）。

### [!DNL LinkedIn]

[!UICONTROL People-Based Destinations] を使用してファーストパーティオーディエンスセグメントを [!DNL LinkedIn] に送信する前に、お客様の [!DNL LinkedIn Campaign Manager] アカウントが [!DNL Creative Manager] 以上の権限レベルであることを確認してください。

[!DNL LinkedIn Campaign Manager] ユーザー権限の編集方法については、「[広告アカウントのユーザー権限の追加、編集、削除](https://www.linkedin.com/help/lms/answer/5753)」を参照してください。 」を参照してください。

ビデオの [手順については、「LinkedInの人ベースの宛先についてと設定](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) 」を参照してください。

### [!DNL Google Customer Match]

を使用してファーストパーティオーディエンスセグメント [!UICONTROL People-Based Destinations] を [!DNL Google Customer Match] 送信先に送信する前に、をファーストパーティ許可リストに追加す [!DNL Google] る必要があります。

データ [!DNL Google] ドキュメントのアップロードは、担当者に問い合わせて、「 [Use Customer Match partners」に記載されている許可リストの手順に従って行います](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507)[!DNL Google] 。

このプロセスが完了したら、を作成でき [!UICONTROL People-Based Destination]ます。

## データオンボーディング {#data-onboarding}

[!UICONTROL People-Based Destinations] のデータ取り込みでは現在、バッチ転送 1 回あたり、1 つの顧客 ID（[!DNL CRM ID]）とリンクされている最大 10 個のハッシュ化された電子メールアドレスをサポートしています。1 つの顧客 ID にリンクされている 10 を超えるハッシュ化された電子メールアドレスをアップロードすると、Audience Manager が、それらのうち 10 個の電子メールアドレスを取り込みます（特定の順序はありません）。

1 つの顧客 ID にリンクされている 10 を超えるハッシュ化された電子メールアドレスを、複数の一括転送でアップロードすると、Audience Manager は最近追加された 10 個の電子メールアドレスを保持します。

## データプライバシー {#data-privacy}

[!UICONTROL People-Based Destinations] では、お客様自身がアップロードした、ハッシュ化された電子メールアドレスに基づいてオーディエンスをターゲット設定することができますが、識別可能な訪問者情報を直接 Audience Manager にアップロードすることは引き続き禁止されています。オンボーディング段階で、使用する予定の電子メールアドレスが [!DNL SHA256] アルゴリズムでハッシュ化されていることを確認する必要があります。そうでない場合、[!UICONTROL People-Based Destinations] で使用することはできません 。

## データのハッシュと暗号化 {#data-hashing-encryption}

暗号化は双方向関数です。暗号化された情報は、復号化キーを使用して復号化することもできます。暗号化された形式の個人を識別できる情報は、復号化される可能性があります。そのため、Audience Manager のコンテキストでデータを暗号化すると、深刻なリスクが生じます。暗号化とは異なり、[!UICONTROL People-Based Destinations] はハッシュ化されたデータを使用するように設計されています。

ハッシュは、入力をスクランブル処理して一意の結果を生成する一方向関数です。[!DNL SHA256] などの適切なハッシュアルゴリズムを使用した場合、ハッシュ関数を反転させてスクランブルされていない情報を表示する方法はありません。Audience Manager にオンボーディングする電子メールアドレスは、[!DNL SHA256] アルゴリズムでハッシュ化する必要があります。これにより、ハッシュ化されていない電子メールアドレスが Audience Manager に届かないようにすることができます。

## ハッシュ要件 {#hashing-requirements}

電子メールアドレスをハッシュ化する場合は、以下の要件に従ってください。

* 電子メール文字列から先頭および末尾の空白文字をすべてトリミングします。例：`johndoe@example.com`（`<space>johndoe@example.com<space>` ではない）
* 電子メール文字列をハッシュする場合は、必ず小文字の文字列をハッシュ化するようにしてください。
   * 例：`example@email.com`（`EXAMPLE@EMAIL.COM` ではない）
* ハッシュ化された文字列がすべて小文字であることを確認します。
   * 例：`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`（`55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149` ではない）
* 文字列にソルトを使用しないでください。

[!UICONTROL People-Based Destinations] のハッシュ要件については、以下のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud gives you the option to hash customer IDs through the [!DNL Adobe Experience Platform Identity Service (ECID)]. ECID を使用して顧客 ID をハッシュ化する方法について詳しくは、[SHA256 setCustomerID のハッシュ化のサポート](https://docs.adobe.com/content/help/ja-JP/id-service/using/reference/hashing-support.html)を参照してください。

## ユーザー権限の取得 {#obtaining-user-permission}

[!UICONTROL People-Based Destinations] は、ユーザーベースのチャネルでファーストパーティのオーディエンスデータをアクティブ化するよう支援しますが、広告目的やその他の目的でデータをどのように使用するかを顧客に通知し、顧客から必要なコンテンツを取得する作業は、お客様がおこなう必要があります。

[!UICONTROL People-Based Destinations] に新規登録する前に必ず、顧客の同意を得てから広告目的で顧客の情報を使用するようにしてください。

広告キャンペーンのオプトアウトをおこなう場合は、Audience Manager を停止してそれ以降のデータを収集する停止方法について詳しくは、[オプトアウト管理](../../overview/data-security-and-privacy/data-privacy-requests.md)を参照してください。

## ファーストパーティデータのアクティブ化を強制する {#enforcing-first-party-activation}

[!UICONTROL People-Based Destinations] を使用する際は、ファーストパーティデータを使用して、ユーザーベースのチャネルでオーディエンスセグメントをアクティブ化できます。ユーザーベースのチャネルでオーディエンスのアクティブ化にセカンドパーティデータやサードパーティデータを使用することはできません。

When using [!UICONTROL People-Based Destinations], use [Data Export Controls](../data-export-controls.md) to label your [!UICONTROL data sources] and [!UICONTROL destinations] according to the guidelines and requirements from destination platforms and data providers.

## 宣言された ID のターゲティングを介して認証済みの ID のオンボーディングをおこなう {#onboard-authenticated-declared-id}

オフラインデータを [!UICONTROL People-Based Destinations] 用に Audience Manager に取り込む方法は次の 2 つです。

* Audience Manager に[バッチデータを送信](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)して、ハッシュ化された電子メールアドレスを取り込みます。この方法では、[!UICONTROL People-Based Destinations] の [!DNL CRM] データベースからすべてのハッシュ化された電子メールアドレスを使用できます。さらに、この方法を使用する場合、[オンボード特性](../traits/trait-and-segment-qualification-reference.md)のハッシュ化された電子メールアドレスも絞り込みます。
* [宣言された ID を使用](../declared-ids.md)して、認証済みの顧客 ID を渡す際にハッシュ化された電子メールアドレスを宣言します。この方法を使用すると、Audience Manager はお客様に代わって、オンラインで認証されたユーザーの、ハッシュされた電子メールアドレスのみを [!UICONTROL People-Based Destinations] に送信できます。ユーザーベースのチャネルでアクティブ化される電子メールアドレスは、宣言されている ID イベント呼び出しの電子メールアドレスのみです。顧客 ID に関連付けられているその他の電子メールアドレスは、リアルタイムでは送信されません。
