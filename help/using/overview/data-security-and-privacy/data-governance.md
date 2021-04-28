---
description: このドキュメントでは、Audience Manager での顧客データの管理方法を説明します。
seo-description: このドキュメントでは、Audience Manager での顧客データの管理方法を説明します。
seo-title: データガバナンス
solution: Audience Manager
keywords: GDPR UI、GDPR API、CCPA、プライバシー、同意、難読化、ガバナンス
title: データガバナンス
feature: データガバナンス & プライバシー
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
translation-type: ht
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: ht
source-wordcount: '470'
ht-degree: 100%

---

# データガバナンス

## 概要 {#overview}

Audience Manager のデータガバナンスは、Audience Manager での顧客データのライフサイクルを指し、[IP アドレスの収集と難読化](data-governance.md#collecting-ip-addresses)、[データ保持](data-governance.md#data-retention)、および[国境を越えたデータ転送](data-governance.md#data-transfers)を包含します。

## IP アドレスの収集と IP アドレスの難読化 {#collecting-ip-addresses}

顧客の Web サイトにアクセスする訪問者の [!DNL IP] アドレスは Adobe [!DNL Data Processing Center]（[!DNL DPC]）に転送され、同センターに [!DNL IP] アドレスが保存される場合があります。訪問者のネットワーク設定によっては、この [!DNL IP] アドレスが訪問者のコンピューターの [!DNL IP] アドレスと一致しないことがあります。例えば、この [!DNL IP] アドレスは、Network Address Translation（NAT）ファイアウォール、[!DNL HTTP] プロキシ、またはインターネットゲートウェイの外部 [!DNL IP] アドレスである可能性があります。

**難読化方法：**「プライバシーバイデザイン」の原則に従い、Adobe Audience Manager では、すべての地域に対してグローバルに、または特定の国に対して、UI からの [!DNL IP] 難読化を有効にすることができます。この設定を有効にすると、[!DNL IP] アドレスが Audience Manager に取り込まれると、[!DNL IP] アドレスの最後のオクテット（最後の部分）は即座に破棄されます。Audience Manager は、処理（オプションの [!DNL IP] アドレスの地域の参照またはログ作成を含む）に先立って、[!DNL IP] アドレスのこの部分を破棄します。例：

* マスク前： `255.255.255.255`
* マスク後： `255.255.255.0`

>[!NOTE]
>
>Audience Manager ユーザーインターフェイス で アドレスを難読化する方法については、[IP アドレスの難読化](../../features/administration/ip-obfuscation.md)をお読みください。[!DNL IP]

Audience Managerでのどのよ [!DNL IP] アドレスの難読かについては、以下のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**地理的分類：**[!DNL IP] アドレスの難読化を有効にした場合、その [!DNL IP] アドレスの残りのオクテットは引き続き、Audience Manager の地域特性およびレポートに使用できます。[!DNL IP]アドレスの難読化を有効にしない場合、Audience Manager は完全な [!DNL IP] アドレスを使用します。どちらの場合でも、[!DNL IP] の場所を地理的地域によって特定できる地理的セグメンテーション機能を使用できますが、[!DNL IP] の難読化を使用している場合は、精度が少し落ちます。[!DNL IP] アドレスの不明化をおこなうと、市レベルの情報の取得が著しく困難になる場合があります。地域レベルおよび国レベルの情報の取得に関しては、それほど大きな影響はありません。地理的セグメンテーションデータの精度は市区町村レベルまたは郵便番号レベルにとどまり、個人レベルにまでは及びません。[地域に基づくターゲティング](../../features/traits/trait-geotarget-keys.md)と、地理的変数を使用した特性の設定方法についてお読みください。

## Audience Manager におけるデータ保持 {#data-retention}

データに対して安全で適切なデータ保持ポリシーをタイムリーに適用することは、データプライバシー規制への準拠の重要な部分となります。Audience Manager をご利用のお客様は、所定の TTL （有効期間）を定義することで、特性およびセグメントの保持期間をカスタマイズ設定できます。保持期間の詳細については、[データ保持に関するよくある質問](../../faq/faq-privacy.md)を参照してください。

## 欧州圏域を超えたデータ転送 {#data-transfers}

Audience Manager が国境を越えてお客様の個人データを転送する場合、Audience Manager は適用法に準拠してデータを転送します。詳細については、[アドビプライバシーセンター](https://www.adobe.com/jp/privacy/eudatatransfers.html)にアクセスしてください。
