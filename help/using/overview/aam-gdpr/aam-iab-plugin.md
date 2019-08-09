---
description: アドビでは、オプトイン機能と IAB Transparency and Consent Framework（TCF）のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。この記事では、IAB TCT をサポートする Audience Manager の使用事例と、Audience Manager での IAB TCF サポートの実装方法について説明します。
seo-description: アドビでは、オプトイン機能と IAB Transparency and Consent Framework（TCF）のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。この記事では、IAB TCT をサポートする Audience Manager の使用事例と、Audience Manager での IAB TCF サポートの実装方法について説明します。
seo-title: IAB TCF 用 Audience Manager プラグイン
solution: Audience Manager
title: IAB TCF 用 Audience Manager プラグイン
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# IAB TCF 用 Audience Manager プラグイン {#aam-iab-plugin}

## 概要

ユーザーのプライバシー保護対策として重要なのは、個人データの活用方法（例：「目的」）および使用者（例：「会社」）に対するユーザーからの同意の取得です。

アドビでは、[オプトイン機能](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)と [IAB Transparency and Consent Framework（TCF）](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。

この記事では、IAB TCT をサポートする Audience Manager の使用事例と、Audience Manager での IAB TCF サポートの実装方法について説明します。Audience Managerは、ベンダーID565を持つIAB TCFに登録されています。

IAB TCF用Audience Managerプラグインは [](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)、Adobe [Experience Cloud IDサービス（ECID）](https://marketing.adobe.com/resources/help/en_US/mcvid/) ライブラリの一部であるオプトイン機能を利用しています。

## スコープと制限 {#scope-and-limitations}

Audience Managerを使用している発行者または広告主として、IAB TCFに従ってAudience Managerにユーザー選択肢を伝えることができます。これにより、作業しているすべてのパートナーに簡単かつ一貫性のある方法でユーザーの選択肢を伝え、Audience Managerでユーザーのプライバシーの選択を支援できます。

この記事で説明されているIAB TCFのサポートは、Audience ManagerがIABフレームワークに対して計画している最初のフェーズを表しています。現在、Audience Managerは以下のサポートをサポートしていません。

* モバイルデバイスのワークフロー
* デバイス間の同意管理
* URLへの送信先URLへ [の同意を付加](/help/using/features/destinations/create-url-destination.md)。
* セグメントへの同意を付加。

## 前提条件 {#prerequisites}

Audience ManagerでIAB TCFを使用するには、次の前提条件を満たす必要があります。

1. Experience Cloud IDサービス（ECID）バージョン4.1以降を使用している必要があります。[最新のEIDリリースをダウンロード](https://github.com/Adobe-Marketing-Cloud/id-service/releases) します。
2. 
   1. ここから [ダウンロード可能なAudience Manager Data Integration Library（DIL）バージョン9.0以降を使用](https://github.com/Adobe-Marketing-Cloud/dil/releases)している必要があります。Audience Managerドキュメントの [DILについて説明](/help/using/dil/dil-overview.md)します。
   2. または、サーバー側転送（SSF）を使用してAudience Managerにデータをインポートする場合は、AppMeasurementの最新バージョンにアップグレードする必要があります。[Analyticsコードマネージャーを使用してAppMeasurementをダウンロード](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)します。
3. IABをサポートし、IAB TCFに登録されているReaccence Management Platform（CMP）を使用する必要があります。IABフレームワークに登録されている [CMPsのリストを参照](https://advertisingconsent.eu/cmp-list/)してください。

## Recommendationsと導入方法 {#recommendations}

Audience ManagerでIAB TCFのサポートを有効にするには、オプトインでIABの設定方法に [関するドキュメントをお読み](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)ください。

これは、Adobe [Launch](https://docs.adobelaunch.com/) を使用してプロパティにEIDオプトインを実装することで実行されます。Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## IABフレームワークを使用する場合のユーザー選択ワークフロー {#user-choice-workflow}

Webプロパティを訪問する場合、発行者および発行者が使用するサードパーティベンダーによるデータの使用方法に関する選択肢をユーザーに提供できます。ユーザーは、グローバルベンダーリストに *登録されている**サードパーティベンダー* に対して、標準的な目的と権限の形式で選択できます。以下の画像は、Webサイトの初回訪問者に表示されるCMPダイアログの例を表しています。このダイアログは、顧客の実装に基づいて、大幅に異なることがあります。

![CMPダイアログ](/help/using/overview/aam-gdpr/assets/cmp.png)

IABフレームワークの標準的な目的は次のとおりです。

* 情報保存とアクセス
* パーソナライゼーション
* 広告選択、配信およびレポート
* コンテンツの選択、配信、レポート
* の測定

5つの標準的な目的の説明については [、IABフレームワーク仕様ページ](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) を参照してください。

ユーザーは、標準的な目的とベンダーの組み合わせに同意することがあります。例えば、ユーザーがストレージ、パーソナライゼーションおよび測定に同意し、CMPによって表示されるすべてのサードパーティベンダーに同意することができます。また、5つの標準的な目的に対する同意を付与することも、CMPによって表示されるベンダーの数に対してのみ同意することもあります。

ユーザーがプライバシー選択を選択すると、ユーザーの選択肢がIAB TCFの同意文字列に記録されます。IAB TCFの同意文字列には、承認された目的とベンダーの組み合わせと共に、その他のメタデータ情報（詳しくは [、IABページ](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) を参照）が格納されます。IAB TCFに登録されているすべてのベンダーは、IAB TCFの同意文字列を評価し、ユーザーのプライバシー選択に基づいて判断を行います。ユーザーのプライバシー選択は、承認されたすべてのベンダーに対して有効であることに注意してください。

## Audience Managerが必要とする標準的な目的 {#aam-standard-purposes}

Audience Managerは、IAB PRODUCT同意文字列に格納されているユーザーの選択肢を評価します。

* 情報保存とアクセス（ [グローバルベンダーリストの目的ID1](https://vendorlist.consensu.org/vendorlist.json)）
* パーソナライゼーション（目的ID2）
* 測定（目的ID5）
* Audience Managerベンダーは、発行者のデータを保存、処理またはアクティブ化することに同意します。

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Managerの動作は、ユーザーが同意するかどうかによって異なります {#aam-behavior-consent}

Audience Managerは、ユーザーが3つの目的（ストレージ、パーソナライゼーション、測定）の3つの目的（ストレージ、パーソナライゼーション、測定）に対して同意したIAB TCFの同意文字列で検出されるかどうかによって異なります。

| ユーザーが同意 **&#x200B;したら、Audience Managerを使用します。 | ユーザー *が* 同意すると、Audience Managerは次のようになります。 |
|---|---|
| <ul><li>リクエストしたAudience Manager使用事例をすべて実行します。</li><li>ID同期の第三者に同意します（dgpr=1を渡し、ID同期呼び出しではdgpr_ acceptとして同意文字列を渡します）。</li><li>広告サーバーピクセルから渡される同意と同意を評価します。</li><li>パートナー開始ID同期に優先します。</li></ul> | <ul><li>新しいユーザーデータはインスタンスに保存しません。パートナーID、シグナル、特性またはピクセルデータが含まれます。</li><li>サードパーティID同期を開始しません。</li><li>パートナー開始ID同期を順守しません。</li></ul> |



## 投稿者の使用例 {#publisher-use-case}

IAB TCFを実装することで、アドビまたは他のサードパーティベンダーとの別のメカニズムを使用して、Webプロパティ上の同意管理のカスタムコードを維持する必要はありません。使用例については、画像および次の手順で説明します。画像の左から開始します。

1. ユーザーがWebプロパティの1つを訪問します。最新バージョンのECIDおよびDILライブラリ（ [前提条件](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)を参照）を使用している限り、オプトインフローがトリガされます。
2. Audience ManagerはIABフローが適用されるかどう`isIabContext=true`かをチェックします。[Recommendationsおよび実装方法](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations)を参照してください。
3. Audience Managerは、GGPRが適用されるか（`gdpr = 1`）、WebプロパティにCMPが登録されているかどうかを確認します。例えば、これは欧州連合地域からの訪問者に適用されます。GGPRフラグを設定するには、発行者の責任があります。
4. DGPRが適用される場合、Audience Managerは、必要な権限のために、パラメーター `gdpr_consent`に渡されたIAB TCF同意文字列をチェックします。Audience Managerでは、ストレージ、パーソナライゼーション、測定およびAudience Managerベンダーの同意に関する権限を必要とし、データを保存、処理、アクティブ化することができます。
5. IAB TCFの同意文字列が存在し、必要な権限が含まれている場合、Audience ManagerはIAB TCF同意文字列をアドビのデータ [収集サーバー](/help/using/reference/system-components/components-data-collection.md) （DCS）に渡します。
6. Audience Managerは、ブラウザーに [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) を設定して応答します。また、Audience Managerは、サードパーティID同期を開始し、優先します。
7. または、手順5で渡されたIAB TCFの同意文字列に必要なすべての権限が含まれていない場合、Audience Managerはデータを収集、処理またはアクティブ化しません。また、ID同期を実行または開始しません。

![投稿者の使用例](assets/publisher-use-case.png)

## 広告主事例 {#advertiser-use-case}

Audience Managerは、IAB TCFに従って [、ピクセル呼び出し](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)で渡される同意を評価し、順守します。

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

## IAB TCFをサポートするアクティベートパートナー {#aam-activation-partners}

IAB TCF用Audience Managerプラグインを使用すると、ユーザーのプライバシー選択に従い、IAB TCFの同意文字列をアクティブ化パートナーに転送できます。アクティブ化パートナーがIAB TCFをサポートしていること（2019年7月7日以降）については **[、弊社のパートナーExcelシートを参照](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**&#x200B;してください。

## IAB実装のテスト {#test-iab-implementation}

IAB TCF用Audience Managerプラグインを正しく実装していることをテストするには、オプトインおよびIAB実装の検証方法で [「使用事例4"を読み取り](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html)ます。

## Audience ManagerのIABおよびオプトアウト。優先順位。 {#iab-and-optout}

ユーザーの浪費によって保護された別のプライバシーオプションは、すべてのデータ収集をオプトアウトする機能です。アドビでは、ユーザーにプライバシー選択 [](https://www.adobe.com/privacy/opt-out.html#customeruse) ページ内の方法を提供しています。

Audience Managerは、アドビドキュメントの [別の記事でオプトアウト管理に対処](/help/using/overview/data-security-and-privacy/opt-out-management.md)します。

>[!NOTE]
>
>**優先順位** -ユーザーがグローバルオプトアウトツールを使用してデータ収集をオプトアウトする場合、上記のリンクに記載されているように、オプトインおよびIABの検証よりも優先されます。

## その他のリソース {#additional-resources}

* [Experience Cloud IDサービスオプトイン](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GGPR透明化および同意フレームワーク](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GGPR透明および同意フレームワーク技術仕様](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF plugin-ビデオデモンストレーション](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)