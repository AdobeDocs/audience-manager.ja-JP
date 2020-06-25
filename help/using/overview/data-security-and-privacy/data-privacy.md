---
description: 消費者のプライバシーおよびオプトアウト手順に関連する一般に認められたベストプラクティスに対する Audience Manager の統合と準拠について説明します。
seo-description: 消費者のプライバシーおよびオプトアウト手順に関連する一般に認められたベストプラクティスに対する Audience Manager の統合と準拠について説明します。
seo-title: データのプライバシー概要
solution: Audience Manager
title: データプライバシーの概要
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 78%

---


# データプライバシーの概要 {#data-privacy}

## 概要

The Data Privacy documentation describes [!DNL Audience Manager] integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.

[!DNL Audience Manager] は、顧客と顧客がやり取りするオンラインブランドとの関係の重要性を認識します。両者とも、匿名データ要素の透過的な交換のメリットを得ることができます。

* 消費者は、パーソナライズされたコンテンツ、割引製品オファー、効率化されたユーザーエクスペリエンスを得ることができます。
* ブランドは、複数のオンラインビジネスモデルをサポートする非常に重要な収入源を得ることができます。

In our continuing support of this model, [!DNL Audience Manager] remains committed to providing you with the tools to help support your ability to provide  transparency and control to your consumers, while delivering personalized ads subject to the [Online Behavioral Advertising (OBA) Self-Regulatory Principles](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

[一般データ保護規則（GDPR）](https://eugdpr.org/)は、EU 加盟国に対して、**アクセス権**&#x200B;や&#x200B;**忘れられる権利**&#x200B;など、新たなデータプライバシー権を導入しました。This means that any [!DNL EU] citizen whose personal data has been collected by your business can request to access or delete their data at any time. これらの要求に従わないと、組織に対して数百万ドルの罰金が科せられる可能性があります。

To comply with [!DNL GDPR], [!DNL Audience Manager] supports data access and delete [requests](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

2020 年 1 月 1 日に施行される[カリフォルニア州消費者プライバシー法（CCPA）](https://www.caprivacy.org/about)は、カリフォルニア州在住者に対して個人情報に関する新たな権利を提供し、カリフォルニア州で事業をおこなう特定の事業者に対してデータ保護責任を課します。

[!DNL CCPA] は、カリフォルニア在住者に対して、自分の個人データにアクセスし削除する権利や、自分の個人データが販売または開示されたか（そして誰に対して）を知る権利など、新しいデータプライバシー権を提供します。に準拠するため [!DNL CCPA]、では [!DNL Audience Manager] アクセスおよび削除 [!DNL CCPA] 要求をサポートしてい [ます](data-privacy-requests.md)。

詳しくは、アドビ[プライバシーセンター](https://www.adobe.com/jp/privacy/opt-out.html)を参照してください。

## 規制コンプライアンス {#compliance}

[!DNL Audience Manager] は、[Adobe Experience Platform プライバシーサービス](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)などのプライバシーツールを使用して、特定のプライバシー規制に基づくデータアクセスおよび削除の要求に対する義務を守るのに役立ちます。

このサービスは、消費者[!DNL RESTful API]データ要求の管理に役立つユーザーインターフェイスを提供します。[プライバシーサービスを使用すると](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)、個人の顧客の要求に基づいて、個人のデータに対するアクセスおよび削除の要求を送信し、コンプライアンス上の義務のこの部分を自動化できます。

データアクセスおよび削除の要求は[プライバシーサービス](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)で処理されますが、現在、[オプトアウト要求](data-privacy-requests.md#opt-out-requests)は [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) を通じてサポートされています。詳しくは、[データのプライバシーリクエスト](data-privacy-requests.md)を参照してください。

## 関連する概念 {#related-concepts}

* [データのプライバシーリクエスト](data-privacy-requests.md)
* [同意管理](data-privacy-consent.md)
* [IAB TCF 用 Audience Manager プラグイン](aam-iab-plugin.md)
* [Audience Manager 識別子](data-privacy-ids.md)
* [CCPA の用語集](aam-ccpa-glossary.md)
* [GDPR の用語集](aam-gdpr-glossary.md)
* [宛先の GDPR に関する考慮事項](aam-gdpr-partners.md)
* [Audience Manager をご利用のお客様向けの GDPR 対応ガイダンス](aam-gdpr-readiness.md)
* [データガバナンス](data-governance.md)
* [プライバシーとデータ保持に関するよくある質問](../../faq/faq-privacy.md)