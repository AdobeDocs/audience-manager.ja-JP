---
description: このドキュメントでは、Audience Managerでの顧客データの管理方法を説明します。
seo-description: このドキュメントでは、Audience Managerでの顧客データの管理方法を説明します。
seo-title: データガバナンス
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: データガバナンス
translation-type: tm+mt
source-git-commit: b47819d5e6394e78d744ada1bb7090d337938983

---


# データガバナンス

## 概要 {#overview}

Audience Managerのデータガバナンスは、Audience Managerでの顧客データのライフサイクルを指し、IPアドレス [、データ保持率](data-governance.md#collecting-ip-addresses)、および国境を越えたデー [タ転送を収](data-governance.md#data-retention)集して不明化します [](data-governance.md#data-transfers)。

## IP アドレスの収集と IP アドレスの難読化 {#collecting-ip-addresses}

顧客の Web サイトにアクセスする訪問者の [!DNL IP] アドレスは Adobe [!DNL Data Processing Center]（[!DNL DPC]）に転送され、同センターに [!DNL IP] アドレスが保存される場合があります。訪問者のネットワーク設定によっては、この [!DNL IP] アドレスが訪問者のコンピューターの [!DNL IP] アドレスと一致しないことがあります。例えば、この [!DNL IP] アドレスは、Network Address Translation（NAT）ファイアウォール、[!DNL HTTP] プロキシ、またはインターネットゲートウェイの外部 [!DNL IP] アドレスである可能性があります。

**難読化方法：**[!DNL IP]「プライバシーバイデザイン」の原則に従い、Adobe Audience Manager では、すべての地域に対してグローバルに、または特定の国に対して、UI からの IP 難読化を有効にすることができます。この設定を有効にすると、[!DNL IP] アドレスが Audience Manager に取り込まれると、[!DNL IP] アドレスの最後のオクテット（最後の部分）は即座に破棄されます。Audience Manager は、処理（オプションの [!DNL IP] アドレスの地域の参照またはログ作成を含む）に先立って、[!DNL IP] アドレスのこの部分を破棄します。次に例を示します。

* マスク前： `255.255.255.255`
* マスク後： `255.255.255.0`

>[!NOTE]
>
>Audience Manager UI で アドレスを難読化する方法については、[IP アドレスの難読化](../../features/administration/ip-obfuscation.md)をお読みください。[!DNL IP]

Audience Managerでのどのよ [!DNL IP] アドレスの難読かについては、以下のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=jpn)

**地理的分類：**[!DNL IP] アドレスの難読化を有効にした場合、その アドレスの残りのオクテットは引き続き、Audience Manager の地域特性およびレポートに使用できます。[!DNL IP][!DNL IP]アドレスの難読化を有効にしない場合、Audience Manager は完全な [!DNL IP] アドレスを使用します。どちらの場合でも、[!DNL IP] の場所を地理的地域によって特定できる地理的セグメンテーション機能を使用できますが、[!DNL IP] の難読化を使用している場合は、精度が少し落ちます。[!DNL IP] アドレスの不明化をおこなうと、市レベルの情報の取得が著しく困難になる場合があります。地域レベルおよび国レベルの情報の取得に関しては、それほど大きな影響はありません。地理的セグメンテーションデータの精度は市区町村レベルまたは郵便番号レベルにとどまり、個人レベルにまでは及びません。[地域に基づくターゲティング](../../features/traits/trait-geotarget-keys.md)と、地理的変数を使用した特性の設定方法についてお読みください。

## Audience Manager におけるデータ保持 {#data-retention}

適切で安全なタイムリーなデータ保存ポリシーをデータに適用することは、データのプライバシー規制に準拠する上で重要な要素です。 Audience Manager をご利用のお客様は、所定の TTL （有効期間）を定義することで、特性およびセグメントの保持期間をカスタマイズ設定できます。リテンション期 [間の詳細については、](../../faq/faq-privacy.md) 「データリテンションFAQ」を参照してください。

## 欧州圏域を超えたデータ転送 {#data-transfers}

GDPR では、欧州圏外へのデータ転送を禁じていませんが、データ転送の際は、欧州におけるデータのプライバシー保護がそのまま適用されることが求められます。詳細については、[アドビプライバシーセンター](https://www.adobe.com/privacy/eudatatransfers.html)にアクセスしてください。CCPAには、国境を越えたデータ転送の制限はありません。
