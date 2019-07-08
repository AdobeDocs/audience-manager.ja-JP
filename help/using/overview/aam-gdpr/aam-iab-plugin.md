---
description: アドビでは、オプトイン機能と IAB Transparency and Consent Framework（TCF）のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。この記事では、IAB TCT をサポートする Audience Manager の使用事例と、Audience Manager での IAB TCF サポートの実装方法について説明します。
seo-description: アドビでは、オプトイン機能と IAB Transparency and Consent Framework（TCF）のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。この記事では、IAB TCT をサポートする Audience Manager の使用事例と、Audience Manager での IAB TCF サポートの実装方法について説明します。
seo-title: IAB TCF 用 Audience Manager プラグイン
solution: Audience Manager
title: IAB TCF 用 Audience Manager プラグイン
translation-type: tm+mt
source-git-commit: 0e32fcaee617e7f18ce4223ffacc39708fb32786

---


# IAB TCF 用 Audience Manager プラグイン {#aam-iab-plugin}

## 概要

ユーザーのプライバシー保護対策として重要なのは、個人データの活用方法（例：「目的」）および使用者（例：「会社」）に対するユーザーからの同意の取得です。

アドビでは、[オプトイン機能](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)と [IAB Transparency and Consent Framework（TCF）](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。

この記事では、IAB TCT をサポートする Audience Manager の使用事例と、Audience Manager での IAB TCF サポートの実装方法について説明します。Audience Managerは、ベンダーID565を持つIAB TCFに登録されています。

The Audience Manager Plug-in for IAB TCF utilizes the [Opt-in functionality](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html), which is, in turn, part of the Adobe [Experience Cloud ID Service (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) library.

## Scope and Limitations {#scope-and-limitations}

Audience Managerを使用している発行者または広告主として、IAB TCFに従ってAudience Managerにユーザー選択肢を伝えることができます。これにより、作業しているすべてのパートナーに簡単かつ一貫性のある方法でユーザーの選択肢を伝え、Audience Managerでユーザーのプライバシーの選択を支援できます。

この記事で説明されているIAB TCFのサポートは、Audience ManagerがIABフレームワークに対して計画している最初のフェーズを表しています。現在、Audience Managerは以下のサポートをサポートしていません。

* モバイルデバイスのワークフロー
* デバイス間の同意管理
* Appending consent to URLs sent to [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination);
* セグメントへの同意を付加。

## 前提条件 {#prerequisites}

Audience ManagerでIAB TCFを使用するには、次の前提条件を満たす必要があります。

1. Experience Cloud IDサービス（ECID）バージョン4.1以降を使用している必要があります。[最新のEIDリリースをダウンロード](https://github.com/Adobe-Marketing-Cloud/id-service/releases) します。
2. 
   1. You must be using Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from [here](https://github.com/Adobe-Marketing-Cloud/dil/releases). Read about [DIL in the Audience Manager documentation](/help/using/dil/dil-overview.md).
   2. または、サーバー側転送（SSF）を使用してAudience Managerにデータをインポートする場合は、AppMeasurementの最新バージョンにアップグレードする必要があります。[Analyticsコードマネージャーを使用してAppMeasurementをダウンロード](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)します。
3. IABをサポートし、IAB TCFに登録されているReaccence Management Platform（CMP）を使用する必要があります。See the list of [CMPs registered within the IAB framework](https://advertisingconsent.eu/cmp-list/).

## Recommendations and how to implement {#recommendations}

To enable the IAB TCF support in Audience Manager, read our documentation on [how to set up IAB with Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

This is easiest done by using [Adobe Launch](https://docs.adobelaunch.com/) to instrument ECID Opt-in on your properties. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## User choice workflow when using the IAB framework {#user-choice-workflow}

Webプロパティを訪問する場合、発行者および発行者が使用するサードパーティベンダーによるデータの使用方法に関する選択肢をユーザーに提供できます。Users provide their choices in the form of *standard purposes* and permissions to *third-party vendors* registered in the global vendor list. 以下の画像は、Webサイトの初回訪問者に表示されるCMPダイアログの例を表しています。このダイアログは、顧客の実装に基づいて、大幅に異なることがあります。

![CMPダイアログ](/help/using/overview/aam-gdpr/assets/cmp.png)

IABフレームワークの標準的な目的は次のとおりです。

* 情報保存とアクセス
* パーソナライゼーション
* 広告選択、配信およびレポート
* コンテンツの選択、配信、レポート
* の測定

Refer to the [IAB framework specification page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) for a description of the five standard purposes.

ユーザーは、標準的な目的とベンダーの組み合わせに同意することがあります。例えば、ユーザーがストレージ、パーソナライゼーションおよび測定に同意し、CMPによって表示されるすべてのサードパーティベンダーに同意することができます。また、5つの標準的な目的に対する同意を付与することも、CMPによって表示されるベンダーの数に対してのみ同意することもあります。

ユーザーがプライバシー選択を選択すると、ユーザーの選択肢がIAB TCFの同意文字列に記録されます。The IAB TCF consent string stores the combination of approved purposes and vendors, along with other metadata information (see the [IAB page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) for more information). IAB TCFに登録されているすべてのベンダーは、IAB TCFの同意文字列を評価し、ユーザーのプライバシー選択に基づいて判断を行います。ユーザーのプライバシー選択は、承認されたすべてのベンダーに対して有効であることに注意してください。

## Standard purposes needed by Audience Manager {#aam-standard-purposes}

Audience Managerは、IAB PRODUCT同意文字列に格納されているユーザーの選択肢を評価します。

* Information storage and access (purpose ID 1 in the [global vendor list](https://vendorlist.consensu.org/vendorlist.json))
* パーソナライゼーション（目的ID2）
* 測定（目的ID5）
* Audience Managerベンダーは、発行者のデータを保存、処理またはアクティブ化することに同意します。

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager behavior depends on whether the user grants consent {#aam-behavior-consent}

Audience Managerは、ユーザーが3つの目的（ストレージ、パーソナライゼーション、測定）の3つの目的（ストレージ、パーソナライゼーション、測定）に対して同意したIAB TCFの同意文字列で検出されるかどうかによって異なります。

| When your user *provides consent*, Audience Manager: | When your user *declines* consent, Audience Manager: |
|---|---|
| <ul><li>リクエストしたAudience Manager使用事例をすべて実行します。</li><li>ID同期の第三者に同意します（dgpr=1を渡し、ID同期呼び出しではdgpr_ acceptとして同意文字列を渡します）。</li><li>広告サーバーピクセルから渡される同意と同意を評価します。</li><li>パートナー開始ID同期に優先します。</li></ul> | <ul><li>新しいユーザーデータはインスタンスに保存しません。パートナーID、シグナル、特性またはピクセルデータが含まれます。</li><li>サードパーティID同期を開始しません。</li><li>パートナー開始ID同期を順守しません。</li></ul> |



## Publisher Use Case {#publisher-use-case}

IAB TCFを実装することで、アドビまたは他のサードパーティベンダーとの別のメカニズムを使用して、Webプロパティ上の同意管理のカスタムコードを維持する必要はありません。使用例については、画像および次の手順で説明します。画像の左から開始します。

1. ユーザーがWebプロパティの1つを訪問します。As long as you are using the latest versions of the ECID and DIL libraries (see [Prerequisites](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), the opt-in flow is triggered.
2. Audience Manager checks whether the IAB flow applies (`isIabContext=true`). [Recommendationsおよび実装方法](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations)を参照してください。
3. Audience Manager checks whether GDPR applies (`gdpr = 1`) and whether there is a CMP, registered with IAB, on your web property. 例えば、これは欧州連合地域からの訪問者に適用されます。GGPRフラグを設定するには、発行者の責任があります。
4. If GDPR applies, Audience Manager checks the IAB TCF consent string, passed in the parameter `gdpr_consent`, for the needed permissions. Audience Managerでは、ストレージ、パーソナライゼーション、測定およびAudience Managerベンダーの同意に関する権限を必要とし、データを保存、処理、アクティブ化することができます。
5. If the IAB TCF consent string is present and it contains the required permissions, Audience Manager passes the IAB TCF consent string on to our [data collection servers](/help/using/reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager responds by setting a [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) on the browser. また、Audience Managerは、サードパーティID同期を開始し、優先します。
7. または、手順5で渡されたIAB TCFの同意文字列に必要なすべての権限が含まれていない場合、Audience Managerはデータを収集、処理またはアクティブ化しません。また、ID同期を実行または開始しません。

![投稿者の使用例](assets/publisher-use-case.png)

## Advertiser Use Case {#advertiser-use-case}

Audience Manager evaluates and honors consent passed in [pixel calls](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), in accordance with the IAB TCF.

ピクセルは通常、Audience Managerのユーザーによってパートナーページに配置されるか、広告応答に含める広告サーバーに配置されます。最初のケースでは、パートナーはプログラムによって同意パラメーターを取得し、実行する前にピクセルに追加する必要があります。2番目のケースでは、より一般的で、後述のように、広告サーバーは、サプライ側プラットフォーム（SSP）またはパブリッシャー広告サーバーからすべてのピクセルに受信する同意パラメーターを追加します。

Audience Managerでは、ピクセル呼び出しでユーザーの同意を渡すために2つのパラメーターを使用します。

* `gdpr` は、0（GGPRが適用されません）または1（GGPR適用）です。
* `gdpr_consent` は、URLセーフベースの64エンコードされたGGPRの同意文字列です（ [指定](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)を参照）。インプレッションピクセルのサンプル呼び出しは、次の2つのパラメーターのようになります。

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

使用例については、画像および次の手順で説明します。画像の左から開始します。

1. ユーザーは、広告サーバー経由でインプレッションを提供します。これは、アドビのデータ収集サーバー（DCS）へのピクセル呼び出しに変換されます。
1. Audience Managerは、DGPRフラグが適用されるかどうかをチェックします。これがない場合、Audience Managerはマクロ変数に渡されたデータをピクセル呼び出しで格納します。
1. 同意文字列が存在し、必要な権限が含まれている場合、Audience Managerはマクロ変数に渡されたデータをピクセル呼び出しで保存します。
1. 同意する文字列がないか、必要な権限がない場合、Audience Managerはマクロ変数に渡されたデータをピクセル呼び出しで削除します。

![広告主事例](assets/advertiser-use-case.png)

## Activation partners that support IAB TCF {#aam-activation-partners}

IAB TCF用Audience Managerプラグインを使用すると、ユーザーのプライバシー選択に従い、IAB TCFの同意文字列をアクティブ化パートナーに転送できます。For information on which activation partners support IAB TCF (accurate as of July 7th, 2019), refer to our **[Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**.

## Test your IAB implementation {#test-iab-implementation}

To test that you have correctly implemented the Audience Manager Plug-in for IAB TCF, read [Use Case 4 in Validation Methods for Opt-in and IAB implementation](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html).

## Audience ManagerのIABおよびオプトアウト。Order of precedence. {#iab-and-optout}

ユーザーの浪費によって保護された別のプライバシーオプションは、すべてのデータ収集をオプトアウトする機能です。Adobe provides users with the means to do so within the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page.

Audience Manager addresses opt-out management in a [separate article in our documentation](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**優先順位** -ユーザーがグローバルオプトアウトツールを使用してデータ収集をオプトアウトする場合、上記のリンクに記載されているように、オプトインおよびIABの検証よりも優先されます。

## その他のリソース {#additional-resources}

* [Experience Cloud IDサービスオプトイン](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GGPR透明化および同意フレームワーク](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GGPR透明および同意フレームワーク技術仕様](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF plugin-ビデオデモンストレーション](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)