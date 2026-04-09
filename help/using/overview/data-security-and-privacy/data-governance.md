---
description: このドキュメントでは、Audience Manager での顧客データの管理方法を説明します。
seo-description: TThis document explains how customer data is governed in Audience Manager.
seo-title: Data Governance
solution: Audience Manager
keywords: GDPR UI、GDPR API、CCPA、プライバシー、同意、難読化、ガバナンス
title: データガバナンス
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
TQID: https://experienceleague.adobe.com/HVF-SxKO4mcE7YkiiwXLBPn2K3N5NIjpZHFWgZb0CoI
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6cid: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: cc72dcf1-72e1-48cc-b434-e7c27d62d67cid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 96%

---

# データガバナンス

## 概要 {#overview}

Audience Manager のデータガバナンスは、Audience Manager での顧客データのライフサイクルを指し、[IP アドレスの収集と難読化](data-governance.md#collecting-ip-addresses)、[データ保持](data-governance.md#data-retention)、および[国境を越えたデータ転送](data-governance.md#data-transfers)を包含します。

## IP アドレスの収集とIP アドレスの難読化 {#collecting-ip-addresses}

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

## Audience Managerでのデータ保持 {#data-retention}

データに対して安全で適切なデータ保持ポリシーをタイムリーに適用することは、データプライバシー規制への準拠の重要な部分となります。Audience Manager をご利用のお客様は、所定の TTL （有効期間）を定義することで、特性およびセグメントの保持期間をカスタマイズ設定できます。保持期間の詳細については、[データ保持に関するよくある質問](../../faq/faq-privacy.md)を参照してください。

## 国境を越えたデータ転送 {#data-transfers}

Audience Manager が国境を越えてお客様の個人データを転送する場合、Audience Manager は適用法に準拠してデータを転送します。詳細については、[アドビプライバシーセンター](https://www.adobe.com/jp/privacy/eudatatransfers.html)にアクセスしてください。
