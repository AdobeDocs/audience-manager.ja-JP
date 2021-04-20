---
description: 消費者のプライバシーおよびオプトアウト手順に関連する一般に認められたベストプラクティスに対する Audience Manager の統合と準拠について説明します。
seo-description: 消費者のプライバシーおよびオプトアウト手順に関連する一般に認められたベストプラクティスに対する Audience Manager の統合と準拠について説明します。
seo-title: データプライバシー概要
solution: Audience Manager
title: データプライバシーの概要
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: Data Governance & Privacy
exl-id: 051de369-e762-49fb-b65f-6faf94db48a4
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 99%

---

# データプライバシーの概要 {#data-privacy}

## 概要

データプライバシードキュメントでは、消費者のプライバシーおよびオプトアウト手順に関連する一般に認められたベストプラクティスに対する [!DNL Audience Manager] の統合と準拠について説明します。

[!DNL Audience Manager] は、顧客と顧客がやり取りするオンラインブランドとの関係の重要性を認識します。両者とも、匿名データ要素の透過的な交換のメリットを得ることができます。

* 消費者は、パーソナライズされたコンテンツ、割引製品オファー、効率化されたユーザーエクスペリエンスを得ることができます。
* ブランドは、複数のオンラインビジネスモデルをサポートする非常に重要な収入源を得ることができます。

[!DNL Audience Manager] は、このモデルの継続的なサポートにおいて、[Online Behavioral Advertising（OBA）の自主規制原則](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/)に従ってパーソナライズされた広告を提供しながら、消費者に透明性と制御を提供するためのツールの提供に取り組んでいます。

## [!DNL GDPR] {#gdpr}

[一般データ保護規則（GDPR）](https://gdpr.eu/data-privacy/)は、EU 加盟国に対して、**アクセス権**&#x200B;や&#x200B;**忘れられる権利**&#x200B;など、新たなデータプライバシー権を導入しました。つまり、御社が個人データを収集した [!DNL EU] 市民は、いつでもデータのアクセスや削除を要求できます。これらの要求に従わないと、組織に対して数百万ドルの罰金が科せられる可能性があります。

[!DNL GDPR] に準拠するため、[!DNL Audience Manager] はデータアクセスおよび削除の[要求](data-privacy-requests.md)をサポートします。

## [!DNL CCPA] {#ccpa}

2020 年 1 月 1 日（PT）に施行される[カリフォルニア州消費者プライバシー法（CCPA）](https://www.caprivacy.org/about)は、カリフォルニア州在住者に対して個人情報に関する新たな権利を提供し、カリフォルニア州で事業をおこなう特定の事業者に対してデータ保護責任を課します。

[!DNL CCPA] は、カリフォルニア在住者に対して、自分の個人データにアクセスし削除する権利や、自分の個人データが販売または開示されたか（そして誰に対して）を知る権利など、新しいデータプライバシー権を提供します。[!DNL CCPA] に準拠するため、[!DNL Audience Manager] は[!DNL CCPA] のアクセスおよび削除の[要求](data-privacy-requests.md)をサポートします。

詳しくは、アドビ[プライバシーセンター](https://www.adobe.com/jp/privacy/opt-out.html)を参照してください。

## 規制コンプライアンス {#compliance}

[!DNL Audience Manager] は、[Adobe Experience Platform プライバシーサービス](https://docs.adobe.com/content/help/ja-JP/experience-platform/privacy/home.html)などのプライバシーツールを使用して、特定のプライバシー規制に基づくデータアクセスおよび削除の要求に対する義務を守るのに役立ちます。

このサービスは、消費者[!DNL RESTful API]データ要求の管理に役立つユーザーインターフェイスを提供します。[プライバシーサービスを使用すると](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)、個人の顧客の要求に基づいて、個人のデータに対するアクセスおよび削除の要求を送信し、コンプライアンス上の義務のこの部分を自動化できます。

データアクセスおよび削除の要求は[プライバシーサービス](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)で処理されますが、現在、[オプトアウト要求](data-privacy-requests.md#opt-out-requests)は [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) を通じてサポートされています。詳しくは、[データプライバシーリクエスト](data-privacy-requests.md)を参照してください。

## 関連する概念 {#related-concepts}

* [データプライバシーリクエスト](data-privacy-requests.md)
* [同意管理](data-privacy-consent.md)
* [IAB TCF 用 Audience Manager プラグイン](aam-iab-plugin.md)
* [Audience Manager 識別子](data-privacy-ids.md)
* [CCPA の用語集](aam-ccpa-glossary.md)
* [GDPR の用語集](aam-gdpr-glossary.md)
* [宛先の GDPR に関する考慮事項](aam-gdpr-partners.md)
* [Audience Manager をご利用のお客様向けの GDPR 対応ガイダンス](aam-gdpr-readiness.md)
* [データガバナンス](data-governance.md)
* [プライバシーとデータ保持に関するよくある質問](../../faq/faq-privacy.md)
