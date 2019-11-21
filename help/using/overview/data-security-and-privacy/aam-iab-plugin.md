---
description: アドビでは、オプトイン機能と IAB Transparency and Consent Framework（TCF）のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。この記事では、IAB TCF をサポートする Audience Manager の使用事例と、Audience Manager での IAB TCF サポートの実装方法について説明します。
seo-description: アドビでは、オプトイン機能と IAB Transparency and Consent Framework（TCF）のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。この記事では、IAB TCF をサポートする Audience Manager の使用事例と、Audience Manager での IAB TCF サポートの実装方法について説明します。
seo-title: IAB TCF 用 Audience Manager プラグイン
solution: Audience Manager
title: IAB TCF 用 Audience Manager プラグイン
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# IAB TCF 用 Audience Manager プラグイン {#aam-iab-plugin}

## 概要

ユーザーのプライバシー保護対策として重要なのは、個人データの活用方法（例：「目的」）および使用者（例：「会社」）に対するユーザーからの同意の取得です。

アドビでは、[オプトイン機能](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)と [IAB Transparency and Consent Framework（TCF）](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。

この記事では、IAB TCF をサポートする Audience Manager の使用事例と、Audience Manager での IAB TCF サポートの実装方法について説明します。Audience Manager は、IAB TCF に登録されています（ベンダー ID 565）。

IAB TCF用Audience Managerプラグインは、 [Opt-in機能を利用します](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)。これは、Adobe [Experience Cloud IDサービス(ECID)ライブラリの一部です](https://marketing.adobe.com/resources/help/en_US/mcvid/) 。

## 範囲と制限 {#scope-and-limitations}

Audience Manager を使用しているパブリッシャーまたは広告主は、IAB TCFに従い、ユーザーが選択した内容を Audience Manager に伝えることができます。これにより、連携するすべてのパートナーに、簡単かつ一貫性のある方法でユーザーの選択肢を伝え、Audience Manager でユーザーのプライバシーの選択を支援することができます。

この記事で説明されている IAB TCF のサポートは、Audience Manager が IAB フレームワークのサポートを予定している最初のフェーズを表しています。現在、Audience Manager は以下をサポートしていません。

* モバイルデバイスのワークフロー
* デバイス間のコンセント管理
* [URL の宛先](../../features/destinations/create-url-destination.md)へ送信する URL への同意の追加
* セグメントへの同意の追加

## 前提条件 {#prerequisites}

Audience Manager で IAB TCF を使用するには、次の前提条件を満たす必要があります。

1. Experience Cloud ID サービス（ECID）バージョン 4.1 以降を使用している。[最新のECIDリリース](https://github.com/Adobe-Marketing-Cloud/id-service/releases) をダウンロードします。
1. You must be using Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from [here](https://github.com/Adobe-Marketing-Cloud/dil/releases). [Audience Manager ドキュメントの DIL](../..//dil/dil-overview.md) をお読みください。
1. また、サーバー側転送（SSF）を使用して Audience Manager にデータを読み込む場合は、最新バージョンの AppMeasurement を使用する必要があります。Analyticsコードマネージャーを使用してAppMeasurement [をダウンロードします](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)。
1. IAB をサポートする市販または独自の同意管理プラットフォーム（CMP）を使用し、IAB TCF に登録していること。See the list of [CMPs registered within the IAB framework](https://advertisingconsent.eu/cmp-list/).

## レコメンデーションと実装方法 {#recommendations}

Audience ManagerでIAB TCFサポートを有効にするには、IABをオプトインで設定する方法に関す [るドキュメントをお読みください](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)。

This is easiest done by using [Adobe Launch](https://docs.adobelaunch.com/) to instrument ECID Opt-in on your properties. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## IAB フレームワークを使用する場合のユーザー選択ワークフロー {#user-choice-workflow}

Web プロパティを訪問する際、ユーザーは、パブリッシャーや、パブリッシャーが連携しているサードパーティベンダーによるデータの使用方法について、自分たちが選択した内容を提供することができます。ユーザーは、グローバルベンダーリストに登録されている&#x200B;*サードパーティベンダー*&#x200B;に対して、*標準的な目的*&#x200B;と権限の形式で選択を提供できます。以下の画像は、Web サイトの初回訪問者に表示される CMP ダイアログの例を表しています。このダイアログは、顧客の実装に基づいて、大幅に異なることがあります。

![CMP ダイアログ](assets/cmp.png)

IAB フレームワークの標準的な目的は次のとおりです。

* 情報の保存とアクセス
* パーソナライゼーション
* 広告の選択、配信およびレポート
* コンテンツの選択、配信、およびレポート
* 測定

5つの標準的な目的の説明は、 [IABフレームワーク仕様のページ](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) （英語）を参照してください。

ユーザーは、標準的な目的とベンダーの組み合わせに同意することができます。例えば、ユーザーはストレージ、パーソナライゼーションおよび測定に同意し、CMP によって表示されるすべてのサードパーティベンダーに対して同意できます。また、5 つの標準的な目的に対する同意することも、CMPによって表示される少数のベンダーの数に対してのみ同意することもできます。

ユーザーがプライバシーを選択すると、ユーザーが選択した内容が IAB TCF のコンセントストリングに記録されます。The IAB TCF consent string stores the combination of approved purposes and vendors, along with other metadata information (see the [IAB page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) for more information). IAB TCF に登録されているすべてのベンダーは、IAB TCF のコンセントストリングを評価し、ユーザーのプライバシー選択に基づいて判断を下します。ユーザーのプライバシー選択は、承認されたすべてのベンダーをまたいで有効であることに注意してください。

## Audience Manager で求められる標準的な目的 {#aam-standard-purposes}

Audience Manager は、IAB TFC コンセントストリングに格納されているユーザーの選択内容を評価します。



* Information storage and access (purpose ID 1 in the [global vendor list](https://vendorlist.consensu.org/vendorlist.json))
* パーソナライゼーション（目的 ID2）
* 測定（目的 ID5）
* Audience Manager ベンダーは、パブリッシャーのデータを保存、処理またはアクティブ化することに同意します。

>[!IMPORTANT]
>
>Audience Manager では、Cookie をデプロイして ID 同期を開始または有効化するために、*3 つの目的すべてに対する同意に加え、ベンダーの同意*&#x200B;が必要です。

## Audience Manager の動作は、ユーザーが同意するかどうかによって異なります {#aam-behavior-consent}

Audience Manager の動作は、ユーザーが 3 つの目的（ストレージ、パーソナライゼーション、測定）に対して同意した IAB TCF のコンセントストリングを検出するかどうかによって異なります。

| ユーザーが&#x200B;*同意*&#x200B;した場合、Audience Manager は以下をおこないます。 | ユーザーが&#x200B;*拒否*&#x200B;した場合、Audience Manager は以下をおこないます。 |
|---|---|
| <ul><li>リクエストした Audience Manager のユースケースをすべて実行する。</li><li>ID 同期でサードパーティに同意する（dgpr=1 を渡し、ID 同期呼び出しでは dgpr_ accept としてコンセントストリングを渡す）。</li><li>広告サーバーピクセルから渡される同意を評価して順守する。</li><li>パートナーが開始した ID 同期に従う。</li></ul> | <ul><li>インスタンスに新しいユーザーデータを保存しない。（パートナー ID、シグナル、特性またはピクセルデータを含む）</li><li>サードパーティ ID 同期を開始しない。</li><li>パートナーが開始した ID 同期に従わない。</li></ul> |

## パブリッシャーのユースケース {#publisher-use-case}

IAB TCF を実装すれば、アドビまたは他のサードパーティベンダーの異なるメカニズムを使用して、Web プロパティ上に同意管理のカスタムコードを保持する必要がなくなります。使用例については、画像と次の手順で説明します。画像の左から開始します。

1. ユーザーが Web プロパティの 1 つを訪問します。最新バージョンの ECID および DIL ライブラリ（[前提条件](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)を参照）を使用している限り、オプトインフローがトリガーされます。
2. Audience Manager は、IAB フローが適用されるかどうかを確認します（`isIabContext=true`）。[レコメンデーションおよび実装方法](aam-iab-plugin.md#recommendations)を参照してください。
3. Audience Manager は、GDPR が適用されるか（`gdpr = 1`）、Web プロパティで IAB に CMP が登録されているかどうかを確認します。例えば、これを欧州連合地域からの訪問者に適用されるとします。パブリッシャーは、GDPR フラグを設定する責任を負います。
4. GDPR が適用される場合、Audience Manager は、必要な権限に対し、パラメーター `gdpr_consent`に渡された IAB TCF コンセントストリングを確認します。Audience Manager でデータを保存、プロセス、またはアクティブ化するには、ストレージ、パーソナライゼーション、測定および Audience Manager ベンダーの同意に関する権限を必要とし、データを保存、処理、アクティブ化することができます。
5. IAB TCF のコンセントストリングが存在し、必要な権限が含まれている場合、Audience Managerは IAB TCF コンセントストリングをアドビの[データ収集サーバー](../../reference/system-components/components-data-collection.md)（DCS）に渡します。
6. Audience Managerは、ブラウザーでdemdex cookieを設 [定するこ](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) とで応答します。 また、Audience Manager は、サードパーティ ID 同期を開始して保持します。
7. または、手順 5 で渡された IAB TCF のコンセントストリングに必要なすべての権限が含まれていない場合、Audience Manager はデータを収集、処理またはアクティブ化せず、ID 同期を実行または開始しません。

![パブリッシャーのユースケース](assets/publisher-use-case.png)

## 広告主のユースケース {#advertiser-use-case}

Audience Manager は、IAB TCF に従って [ピクセル呼び出し](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)で渡される同意を評価し、順守します。

ピクセルは通常、Audience Manager のユーザーによってパートナーページに配置されるか、広告サーバーに配置されて広告応答に含められます。最初のケースでは、パートナーはプログラムによって同意パラメーターを取得し、実行する前にピクセルに追加する必要があります。より一般的な 2 番目のケース（以下で説明します）では、広告サーバーは、サプライ側プラットフォーム（SSP）またはパブリッシャー広告サーバーから受信した同意パラメーターを、すべてのピクセルに受信する同意パラメーターを追加します。

Audience Manager では、ピクセル呼び出しでユーザーの同意を渡すために 2 つのパラメーターを使用します。

* `gdpr` には、0（GDPR 適用対象外）または 1（GDPR 適用対象）を使用できます。
* `gdpr_consent` は、URL で使用できる base64 でエンコードされた GDPR コンセントストリングです（[ の仕様](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)を参照）。インプレッションピクセルのサンプル呼び出しは、次の 2 つのパラメーターのようになります。

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

使用例については、画像と次の手順で説明します。画像の左から開始します。

1. ユーザーは、広告サーバー経由でインプレッションを提供します。これは、アドビのデータ収集サーバー（DCS）へのピクセル呼び出しに変換されます。
2. Audience Manager は、GDPR フラグが適用されるかどうかを確認します。適用されない場合、Audience Manager はマクロ変数に渡されたデータをピクセル呼び出しに保存します。
3. コンセントストリングが存在し、必要な権限が含まれている場合、Audience Manager はマクロ変数に渡されたデータをピクセル呼び出しに保存します。
4. コンセントストリングがない、または必要な権限が不足している場合、Audience Manager はマクロ変数に渡されたデータをピクセル呼び出しから破棄します。

![広告主のユースケース](assets/advertiser-use-case.png)

## IAB TCF をサポートするアクティベーションパートナー {#aam-activation-partners}

IAB TCF 用 Audience Manager プラグインを使用すると、ユーザーのプライバシー選択に従い、IAB TCF のコンセントストリングをアクティベーションパートナーに転送できます。For information on which activation partners support IAB TCF, refer to our **[Partner Excel sheet](/help/using/overview/data-security-and-privacy/assets/AAM-Partners-October2019.xlsx)**.

## IAB 実装のテスト {#test-iab-implementation}

To test that you have correctly implemented the Audience Manager Plug-in for IAB TCF, read [Use Case 4 in Validation Methods for Opt-in and IAB implementation](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html).

## Audience Manager の IAB およびオプトアウト。優先順位。 {#iab-and-optout}

ユーザーが選択できるもう一つのプライバシーオプションは、すべてのデータ収集をオプトアウトする機能です。Adobe provides users with the means to do so within the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page.

Audience Manager addresses opt-out requests in a [separate article in our documentation](data-privacy-requests.md).

>[!NOTE]
>
>**優先順位**：ユーザーがグローバルオプトアウトツールを使用してデータ収集をオプトアウトする場合、上記のリンクに記載されているように、オプトインおよび IAB の検証よりも優先されます。

## その他のリソース {#additional-resources}

* [Experience Cloud IDサービスのオプトイン](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB欧州GDPR透明化・同意枠組み](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR透明性と同意フレームワークの技術仕様](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCFプラグイン — ビデオデモ](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)