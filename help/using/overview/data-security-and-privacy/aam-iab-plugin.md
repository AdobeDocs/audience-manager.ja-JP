---
description: アドビでは、オプトイン機能と IAB Transparency and Consent Framework（TCF）のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。この記事では、IAB TCF をサポートする Audience Manager のユースケースと、Audience Manager での IAB TCF サポートの実装方法について説明します。
seo-description: アドビでは、オプトイン機能と IAB Transparency and Consent Framework（TCF）のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。この記事では、IAB TCF をサポートする Audience Manager のユースケースと、Audience Manager での IAB TCF サポートの実装方法について説明します。
seo-title: IAB TCF 用 Audience Manager プラグイン
solution: Audience Manager
title: IAB TCF 用 Audience Manager プラグイン
translation-type: tm+mt
source-git-commit: b5c56453a7278573dec2b80be7baa9833a847a4a
workflow-type: tm+mt
source-wordcount: '2432'
ht-degree: 42%

---


# IAB TCF 用 Audience Manager プラグイン {#aam-iab-plugin}

## 概要

ユーザに対するプライバシー義務の重要な側面は、個人データの使用方法（「目的」など）や使用者(「会社」など)に関するユーザの選択肢の獲得と伝達です。

アドビでは、[オプトイン機能](https://docs.adobe.com/content/help/ja-JP/id-service/using/implementation/opt-in-service/optin-overview.html)と [IAB Transparency and Consent Framework（TCF）](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)のサポートを通じて、ユーザーのプライバシー選択を管理および伝達する手段を提供しています。

この記事では、IAB TCF をサポートする Audience Manager のユースケースと、Audience Manager での IAB TCF サポートの実装方法について説明します。

>[!IMPORTANT]
>
>Audience Manager is registered in the [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) with the vendor ID 565.

IAB TCF 用 Audience Manager プラグインは、[オプトイン機能](https://docs.adobe.com/content/help/ja-JP/id-service/using/implementation/opt-in-service/iab.html)を利用します。これは、アドビの [ Experience Platform ID サービス（ECID）](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)ライブラリの一部です。

## 範囲と制限 {#scope-and-limitations}

Audience Manager を使用しているパブリッシャーまたは広告主は、IAB TCF に従い、ユーザーが選択した内容を Audience Manager に伝えることができます。

>[!IMPORTANT]
>
>IAB TCFの規制は、欧州経済圏に位置する訪問者にのみ適用されます。

オーディエンスマネージャは、ユーザのプライバシー選択を尊重し、お客様が利用するすべてのパートナーに対して、プライバシー選択を簡単に伝える手段を提供します。

現在、Audience Manager は以下をサポートしていません。

* モバイルデバイスのワークフロー
* セグメントエクスポートに同意を追加。

## 前提条件 {#prerequisites}

>[!IMPORTANT]
>
>オーディエンスマネージャーはIAB TCF v2.0をサポートしています。
>
>IAB TCF v1.1のサポートは、2020年8月15日に終了します。
>
> 同意管理のためにIAB TCF用オーディエンスマネージャプラグインを引き続き使用する場合は、サポートを継続するために [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) の最新バージョンにアップグレードする必要があります。
>
> 最新の [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) バージョンにアップグレードした後は、IAB TCF v1.1の同意文字列はサポートされなくなるので、最新のECIDバージョンにアップグレードする前にCMPを必ず更新してください。

IAB TCF用オーディエンスマネージャプラグインをオーディエンスマネージャと共に使用するには、次の前提条件を満たす必要があります。

1. Adobe Experience Platform ID サービス（ECID）バージョン 5 以降を使用している。アドビの最新 ECID リリースを[ダウンロード](https://github.com/Adobe-Marketing-Cloud/id-service/releases)してください。
2. Audience Manager Data Integration Library（DIL）バージョン 9.0 以降を使用している（[こちら](https://github.com/Adobe-Marketing-Cloud/dil/releases)からダウンロード可能）。[Audience Manager ドキュメントの DIL](../..//dil/dil-overview.md) をお読みください。オーディエンスマネージャーの最も簡単なDIL実装には、 [Adobe Launch](https://docs.adobe.com/content/help/ja-JP/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) （アドビの起動）を使用することをお勧めします。
3. または、最新バージョンの AppMeasurement を使用している（サーバー側転送（SSF）を使用して Audience Manager にデータを読み込む場合）。[Analytics コードマネージャー](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/code-manager-admin.html)を使用して AppMeasurement をダウンロードしてください。
4. IAB TCF v2.0に統合され、IAB TCFに登録されている、商用または自社のいずれかの同意管理プラットフォーム(CMP)を使用している必要があります。 [IAB フレームワーク内の登録 CMP](https://iabeurope.eu/cmp-list/) のリストを参照してください。

>[!WARNING]
>
>IAB TCF v.2.0をサポートしないConsent Management Platform(CMP)を使用している場合、訪問者がヨーロッパ和集合にいる場合でも、オーディエンスマネージャーはID同期で `gdpr=0` パラメーターを自動的に送信します。 GDPR検証が有効かどうかを判断するには、IAB TCF v2.0をサポートしていることをCMP（同意管理プラットフォーム）で確認することをお勧めします。

## レコメンデーションと実装方法 {#recommendations}

Audience Manager で IAB TCF サポートを有効にするには、[IAB をオプトインで設定する方法](https://docs.adobe.com/content/help/ja-JP/id-service/using/implementation/opt-in-service/iab.html)に関するドキュメントをお読みください。

これを行う最も簡単な方法は、 [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/ja-JP/launch/using/overview.html) （Adobe Experience Platformの起動）を使用して、プロパティにECIDオプトインを追加することです。 Launch 拡張機能のセットアップ方法については、[ECID オプトイン拡張機能](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html)をお読みください。

## IAB フレームワークを使用する場合のユーザー選択ワークフロー {#user-choice-workflow}

Web プロパティを訪問する際、ユーザーは、パブリッシャーや、パブリッシャーが連携しているサードパーティベンダーによるデータの使用方法について、自分たちが選択した内容を提供することができます。

ユーザーは、グローバルベンダーリストに *登録した* サードパーティベンダーに対し、IAB目的の *同意と正当な利益の形で選択肢を提供します*** 。

以下の画像は、Web サイトの初回訪問者に表示される CMP ダイアログの例を表しています。このダイアログは、顧客の実装に基づいて、大幅に異なることがあります。

![CMP ダイアログ](assets/cmp-example.png)

IAB TCF v2.0に含まれる様々な目的と権限の詳細については、 [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)（IABヨーロッパ透明性および同意フレームワークポリシー）を参照してください。

ユーザーは、目的とベンダーの組み合わせに対して、同意または合法的な利益（利用可能な場合）を付与できます。 例えば、ユーザーは、デバイスに情報を保存し、製品を開発および改善することに対する同意を与え、CMPによって表示されるすべてのサードパーティベンダーに同意を与えることができます。

また、別の例では、CMPが表示する一部のベンダーに対しては、すべての目的に対して同意または正当な関心を与えるだけで、同意または正当な関心を与えることができます。

ユーザーがプライバシーの選択を行うと、IAB TC文字列にユーザーの選択内容が記録されます。 The IAB TC string stores the combination of approved purposes and vendors, along with other metadata information (see the [IAB page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) for more information).

IAB TCFに登録されたすべてのベンダーは、IAB TC文字列を評価し、ユーザーのプライバシー選択に基づいて判断を行います。 ユーザーのプライバシー選択は、IAB TCFに登録されているすべてのベンダーで有効であることに注意してください。

## オーディエンスマネージャーに必要な目的 {#aam-standard-purposes}

オーディエンスマネージャーは、IAB Europe Transparency &amp; Consent Framework Policiesに定義されている次の目的で、IAB TC文字列に保存されている [ユーザーの選択を評価します](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)。 また、この目的は、 [グローバルベンダーリストにもあります](https://vendorlist.consensu.org/vendorlist.json)。

* **目的1**: デバイス上に情報を保存/アクセスする。
* **目的10**: 製品の開発と改善
* **特別な目的1**: セキュリティの確保、不正の防止、デバッグ。

>[!IMPORTANT]
>
>Cookieを展開し、ID同期を開始または順守するには、オーディエンスマネージャーが目的1と目的10に対する同意とベンダーの同意を必要とします。
>
>IAB規制に従い [、特別な目的](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)1（セキュリティの確保、不正の防止、デバッグ）は常に同意され、ユーザーはそれに反対できません。

## Audience Manager の動作は、ユーザーが同意するかどうかによって異なります {#aam-behavior-consent}

IAB TC文字列が2つの目的（デバイス上のストアおよび/またはアクセス情報、製品の開発と改善）に対するユーザーの同意を含むかどうかによって、オーディエンスマネージャの動作が異なります。

また、オーディエンスマネージャーで作業するすべての宛先がIAB TCFに登録されている限り、その宛先に対するユーザーの同意を確認します。

| ユーザーが&#x200B;*同意*&#x200B;した場合、Audience Manager は以下をおこないます。 | ユーザーが&#x200B;*拒否*&#x200B;した場合、Audience Manager は以下をおこないます。 |
|---|---|
| <ul><li>リクエストした Audience Manager のユースケースをすべて実行する。</li><li>Conveys consent to third parties in ID syncs (by passing `gdpr = 1` and the consent string as `gdpr_consent` on ID sync calls).</li><li>広告サーバーピクセルから渡される同意を評価して順守する。</li><li>パートナーが開始した ID 同期に従う。</li></ul> | <ul><li>インスタンスに新しいユーザーデータを保存しない。（パートナー ID、シグナル、特性またはピクセルデータを含む）。</li><li>サードパーティ ID 同期を開始しない。</li><li>パートナーが開始した ID 同期に従わない。</li><li>ユーザーをその他のデータ収集からオプトアウトします。</li></ul> |

## パブリッシャーのユースケース {#publisher-use-case}

IAB TCF用オーディエンスマネージャープラグインを実装することで、アドビや他のサードパーティベンダーとは異なるメカニズムを使用して、Webプロパティの同意管理のためのカスタムコードを維持する必要はありません。 ユースケースについては、画像と次の手順で説明します。画像の左から開始します。

1. ユーザーが Web プロパティの 1 つを訪問します。最新バージョンの ECID および DIL ライブラリ（[前提条件](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)を参照）を使用している限り、オプトインフローがトリガーされます。
2. Audience Manager は、IAB フローが適用されるかどうかを確認します（`isIabContext=true`）。[レコメンデーションおよび実装方法](aam-iab-plugin.md#recommendations)を参照してください。
3. Audience Manager checks whether GDPR applies (`gdpr = 1`) and whether there is a CMP, registered with IAB TCF, on your web property. 例えば、これはヨーロッパ和集合から訪問するユーザーに適用されます。 GDPRフラグを設定するのは、パブリッシャーとしての責任です。
4. If GDPR applies, Audience Manager checks the IAB TC string, passed in the `gdpr_consent` parameter, for the required consent. オーディエンスマネージャは、デバイス([IAB TCF purpose 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes))上の情報の保存/アクセス、製品の開発と向上([IAB TCF purpose 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes))、およびオーディエンスマネージャベンダーによるデータの保存、処理、アクティベートに関する同意を得る必要があります。
5. If the IAB TC string is present and it contains the required consent, Audience Manager passes the IAB TC string on to our [data collection servers](../../reference/system-components/components-data-collection.md) (DCS).
6. オーディエンスマネージャーは、ブラウザーで [demdex cookie](https://docs.adobe.com/content/help/ja-JP/core-services/interface/ec-cookies/cookies-am.html) を設定することで応答し、サードパーティID同期を開始し、その同期に従います。
7. または、手順4で渡されたIAB TC文字列に必要なすべての権限が含まれていない場合、オーディエンスマネージャーはユーザーデータを収集、処理、アクティブ化せず、ID同期を順守または開始しません。 さらに、操作するリンク先からユーザーをオプトアウトします。

>[!IMPORTANT]
>
>IAB TCFパラメーターを必要とするオーディエンスマネージャーの宛先パートナーと連携しているが、WebサイトでIAB TCFをサポートするCMPがない場合、オーディエンスマネージャーはID同期 `gdpr=0` で送信します。 つまり、GDPRはユーザには適用されない。
>
> それが望ましくない場合は、オーディエンスマネージャーでIAB TCF機能を有効にして、適切なIAB TC文字列を送信先のパートナーに送信する必要があります。



![パブリッシャーのユースケース](assets/publisher-use-case.png)

## 広告主のユースケース {#advertiser-use-case}

Audience Manager は、IAB TCF に従って、[ピクセル呼び出し](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)で渡される同意を評価し、順守します。

ピクセルは、オーディエンスマネージャーのお客様がパートナーページに配置するか、広告サーバーに配置して広告の応答に含めることができます。 最初のケースでは、パートナーはプログラムによって同意パラメーターを取得し、実行する前にピクセルに追加する必要があります。より一般的な 2 番目のケース（以下で説明します）では、広告サーバーは、サプライ側プラットフォーム（SSP）またはパブリッシャー広告サーバーから受信した同意パラメーターを、すべてのピクセルに受信する同意パラメーターを追加します。

Audience Manager では、ピクセル呼び出しでユーザーの同意を渡すために 2 つのパラメーターを使用します。

* `gdpr` には、0（GDPR 適用対象外）または 1（GDPR 適用対象）を使用できます。
* `gdpr_consent` は、URL で使用できる base64 でエンコードされた GDPR コンセントストリングです（[ の仕様](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)を参照）。インプレッションピクセルのサンプル呼び出しは、次の 2 つのパラメーターのようになります。

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

ユースケースについては、画像と次の手順で説明します。画像の左から開始します。

1. ユーザーは、広告サーバー経由でインプレッションを提供します。This translates into a [pixel call](../../integration/media-data-integration/impression-data-pixels.md) to our Data Collection Servers (DCS).
2. Audience Manager は、GDPR フラグが適用されるかどうかを確認します。If it doesn&#39;t, Audience Manager stores the data passed in the `gdpr` and `gdpr_consent` variables in pixel calls.
3. If the IAB TC string is present and it contains the required permissions, Audience Manager stores the data passed in the `gdpr` and `gdpr_consent` variables in pixel calls.
4. If the IAB TC string is missing or lacks the required permissions, Audience Manager drops the data passed in the `gdpr` and `gdpr_consent` variables in pixel calls.

![広告主のユースケース](assets/advertiser-use-case.png)

## IAB TCF をサポートするアクティベーションパートナー {#aam-activation-partners}

IAB TCF用オーディエンスマネージャプラグインを使用すると、ユーザーのプライバシーの選択に従い、IAB TC文字列をアクティベーションパートナーに転送できます。 IAB TCF をサポートするアクティベーションパートナーに関する情報は、[デバイスベースの宛先のリストト](/help/using/features/destinations/device-based-destinations-list.md)を参照してください。

## URL宛先に送信するURLに同意を追加

IAB TCF v2.0とのオーディエンスマネージャー統合では、IAB TCF v2.0と統合される [](../../features/destinations/create-url-destination.md) URL宛先に送信される情報に同意を付加できます。ただし、特定のURL形式を無効にするために、オーディエンスーマネージャーはこの処理を自動的に行いません。

URLの宛先に送信するデータに同意を追加する場合は、URL形式にマクロ `${GDPR}` と `${GDPR_CONSENT_XXXX}` マクロを手動で追加し、それを宛先パートナーID `XXXX` に置き換える必要があります。

例：`http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`。

サポートされている [宛先マクロの詳細は、「定義された](../../features/destinations/destination-macros.md) 宛先マクロ」を参照してください。

## デバイス間の同意管理

IAB TCF用オーディエンスマネージャープラグインは、サイトの訪問者が適切な権限を与えていない場合、リクエストに存在するIDを自動的にオプトアウトします。 リクエストに [クロスデバイスID(CRM ID)が含まれる場合](../../reference/ids-in-aam.md)、オーディエンスマネージャーは、IDと、そのクロスデバイスID(CRM ID)にリンクされている最後の [デバイスをオプトアウトし](../../reference/ids-in-aam.md)ます。

## IAB 実装のテスト {#test-iab-implementation}

To test that you have correctly implemented the Audience Manager Plug-in for IAB TCF, read [Use Case 4 in Validating Opt-in Service](https://docs.adobe.com/content/help/ja-JP/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## Audience Manager の IAB およびオプトアウト。優先順位。 {#iab-and-optout}

ユーザーが選択できるもう一つのプライバシーオプションは、すべてのデータ収集をオプトアウトする機能です。アドビはユーザーに対し、[プライバシーの選択肢](https://www.adobe.com/jp/privacy/opt-out.html#customeruse)ページ内でオプトアウトを提供しています。

Audience Manager は、[ドキュメントの別の記事](data-privacy-requests.md#opt-out-requests)で、オプトインのリクエストに対処しています。

>[!IMPORTANT]
>
>同意を拒否した後にすべてのデータ収集をオプトアウトしたユーザーは、オプトインできません。

>[!NOTE]
>
>**優先順位**：ユーザーがグローバルオプトアウトツールを使用してデータ収集をオプトアウトする場合、上記のリンクに記載されているように、オプトインおよび IAB の検証よりも優先されます。

## その他のリソース {#additional-resources}

* [Adobe Experience Platform ID サービスのオプトイン](https://docs.adobe.com/content/help/ja-JP/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB Europe GDPR の透明性および同意フレームワーク](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR の透明性および同意フレームワークの技術仕様](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF プラグイン - ビデオデモ](https://helpx.adobe.com/jp/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)