---
description: Audience Management モジュールを Adobe Analytics AppMeasurement に追加すると、Audience Manager データ統合ライブラリ（DIL）コードでページからピクセルを送信するのではなく、Analytics データを Audience Manager に転送することができます。
keywords: audience analytics; analytics; ssf; サーバー側転送
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Audience Management モジュールの実装
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 93%

---

# [!DNL Adobe Analytics] から [!DNL Audience Manager] にデータを転送する方法  {#implement-the-audience-management-module}

このチュートリアルの手順に従い、[!DNL Audience Manager] [!UICONTROL Data Integration Library]（[!DNL DIL]）コードでページからピクセルを送信する代わりに、[!DNL Analytics] データを [!DNL Audience Manager] に転送することができます。

>[!TIP]
>
>[!DNL Adobe Experience Platform Tags] を使用して [!UICONTROL Analytics] データを [!DNL Audience Manager] に転送することをお勧めします。[!UICONTROL Tags] を使用すると、このページで示すように、[!DNL AppMeasurement] に手動でコードをコピーする必要がなくなります。

## 前提条件 {#prereqs}

このドキュメントで説明した拡張機能の有効化やコードの実装に加えて、以下をおこなう必要があります。

* [Adobe Experience Platform ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を実装する。
* [ でレポートスイートの](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=ja)サーバーサイド転送[!UICONTROL Adobe Analytics Admin Console]を有効にする。

## 実装 {#implementation}

[!DNL Adobe Analytics] から [!DNL Audience Manager] へのデータ転送は、使用するタグ管理ソリューションに応じて、2 つの方法で実装できます。

### [!DNL Adobe Experience Platform Tags] を使用した実装 

[!DNL Adobe] では、 [タグ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) 器具の拡張 [!DNL Adobe Analytics] および [!DNL Audience Manager] 」と入力します。 この場合、コードを手動でコピーする必要はありません。代わりに、以下の画像に示すように、[!DNL Analytics] 拡張機能でデータ共有を有効にする必要があります。[Adobe Analytics 拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager)のドキュメントも参照してください。

>[!TIP]
>
>[!DNL Adobe Analytics] 拡張機能をインストールする場合、[!DNL Audience Manager] 拡張機能はインストール&#x200B;*しないでください*。[!DNL Analytics] 拡張機能からのデータの転送は、[!DNL Audience Manager] 拡張機能に代わるものです。

![Adobe Analytics 拡張機能から Audience Manager へのデータ転送を有効にする方法 ](/help/using/integration/assets/analytics-to-aam.png)

## コード要素の定義 {#code-elements-defined}

コードサンプルの重要な変数の定義を次の表に示します。

| パラメーター | 説明 |
|--- |--- |
| `partner` | 必須。これは、[!DNL Adobe]によって割り当てられたパートナー名です。「[!UICONTROL partner ID]」や「パートナーサブドメイン」と呼ばれることもあります。パートナー名が不明な場合は、[!DNL Adobe]のコンサルタントまたは[カスタマーケア](https://helpx.adobe.com/jp/marketing-cloud/contact-support.html)にお問い合わせください。 |
| `containerNSID` | 必須。ほとんどの場合は、`"containerNSID":0` に設定できます。ただし、会社が異なるコンテナを使用して ID 同期をカスタマイズする必要がある場合、ここでそのコンテナ ID を指定できます。 |
| `uuidCookie` | オプションです。この設定を使用すると、ファーストパーティドメインに [!DNL Adobe] Cookie を設定できます。この [!DNL cookie] には、[UUID](../../reference/ids-in-aam.md) が含まれます。 |
| `visitorService` - `namespace` | 必須。`namespace` パラメーターは、[!UICONTROL AppMeasurement] バージョン 2.10 以降にバンドルされている [!DNL AudienceManagement] モジュールを使用する場合に必要です。この [!UICONTROL AudienceManagement] モジュールでは、[!UICONTROL Adobe Experience Platform Identity Service] 3.3 以降を使用する必要があります。<br><br>[!UICONTROL Experience Cloud Organization ID] は、会社が [!UICONTROL Experience Cloud] に新規登録したときに生成される ID です。「[組織とアカウントのリンク](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=ja)」で、会社の組織 ID を確認します。 |

## 結果：[!DNL Audience Manager] へのデータ転送  {#results-data-forwarding}

以下の手順をおこなった後、[!DNL Analytics] 実装は [!DNL Audience Manager] にデータを送信します。

* [!UICONTROL Server-Side Forwarding]を有効にする（この機能については、コンサルタントにお問い合わせください）。
* [!DNL Adobe Experience Platform Identity Service] を実装する。
* このチュートリアルの実装手順に従う。

このプロセスは、以下の場合に [!DNL Audience Manager] にデータを送信します。

* ページ表示の呼び出し時。
* 追跡されたリンクから。
* ビデオマイルストーンおよびハートビートビデオ表示から。

>[!NOTE]
>
>[!DNL Analytics] から [!DNL Audience Manager] に送信された変数は、特別なプレフィックスを使用します。[!DNL Audience Manager] 特性を作成する場合は、これらのプレフィックスについて理解し、考慮に入れる必要があります。これらのプレフィックスについて詳しくは、[キー変数のプレフィックス要件](../../features/traits/trait-variable-prefixes.md)を参照してください。
