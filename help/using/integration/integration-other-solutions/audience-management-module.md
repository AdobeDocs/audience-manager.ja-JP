---
description: Audience Management モジュールを Adobe Analytics AppMeasurement に追加すると、Audience Manager データ統合ライブラリ（DIL）コードでページからピクセルを送信するのではなく、Analytics データを Audience Manager に転送することができます。
keywords: audience analytics; analytics; ssf; サーバー側転送
seo-description: Audience Management モジュールを Adobe Analytics AppMeasurement に追加すると、Audience Manager データ統合ライブラリ（DIL）コードでページからピクセルを送信するのではなく、Analytics データを Audience Manager に転送することができます。
seo-title: Audience Management モジュールの実装
solution: Audience Manager
title: Audience Management モジュールの実装
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 100%

---

# [!DNL Adobe Analytics] から [!DNL Audience Manager] にデータを転送する方法 {#implement-the-audience-management-module}

このチュートリアルの手順に従い、[!DNL Audience Manager] [!UICONTROL Data Integration Library]（[!DNL DIL]）コードでページからピクセルを送信する代わりに、[!DNL Analytics] データを [!DNL Audience Manager] に転送することができます。

>[!TIP]
>
>[!DNL Adobe Experience Platform Launch] を使用して [!UICONTROL Analytics] データを [!DNL Audience Manager] に転送することをお勧めします。[!UICONTROL Launch] を使用すると、このページで示すように、[!DNL AppMeasurement] に手動でコードをコピーする必要がなくなります。

## 前提条件 {#prereqs}

このドキュメントで説明した拡張機能の有効化やコードの実装に加えて、以下をおこなう必要があります。

* [Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を実装する。
* [ でレポートスイートの](https://docs.adobe.com/help/ja-JP/analytics/admin/admin-tools/server-side-forwarding/ssf.html)サーバーサイド転送[!UICONTROL Adobe Analytics Admin Console]を有効にする。

## 実装 {#implementation}

[!DNL Adobe Analytics] から [!DNL Audience Manager] へのデータ転送は、使用するタグ管理ソリューションに応じて、2 つの方法で実装できます。

### [!DNL Adobe Experience Platform Launch] を使用した実装 

[!DNL Adobe] では、[Launch](https://docs.adobe.com/content/help/ja-JP/launch/using/overview.html) 拡張機能を使用して、プロパティで [!DNL Adobe Analytics] および [!DNL Audience Manager] を実装することをお勧めします。この場合、コードを手動でコピーする必要はありません。代わりに、以下の画像に示すように、[!DNL Analytics Launch] 拡張機能でデータ共有を有効にする必要があります。[Adobe Analytics 拡張機能](https://docs.adobe.com/content/help/ja-JP/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager)のドキュメントも参照してください。

>[!TIP]
>
>[!DNL Adobe Analytics] 拡張機能をインストールする場合、[!DNL Audience Manager] 拡張機能はインストール&#x200B;*しないでください*。[!DNL Analytics] 拡張機能からのデータの転送は、[!DNL Audience Manager] 拡張機能に代わるものです。

![Adobe Analytics 拡張機能から Audience Manager へのデータ転送を有効にする方法 ](/help/using/integration/assets/analytics-to-aam.png)

### [!DNL Adobe Digital Tag Management (DTM)] またはタグ管理ソリューションを使用した実装

>[!WARNING]
>
>[!DNL Adobe]は、2020 年末までに [!DNL DTM] の終了を予定しています。詳しくは、[Adobe コミュニティフォーラム](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)の「[!DNL DTM] の終了予定」を参照してください。

[Adobe DTM](https://docs.adobe.com/content/help/ja-JP/dtm/using/dtm-home.html) または他のタグ管理ソリューションを使用して、[!UICONTROL Audience Management Module] を実装するには、次の手順を実行します。

1. [Analytics Code Manager](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/code-manager-admin.html)（バージョン 1.5 以降が必要）を使用して、[!UICONTROL AppMeasurement] をダウンロードします。
1. ダウンロードした zip ファイルに含まれていたバージョンに [!UICONTROL AppMeasurement] コードを更新します。
1. zip ファイルの `AppMeasurement_Module_AudienceManagement.js` からすべてのコードをコピーします。`appMeasurement.js` ファイルの「`"DO NOT ALTER ANYTHING BELOW THIS LINE."`」というテキストのすぐ上に貼り付けます。
1. 前の手順で追加した `AppMeasurement_Module_AudienceManagement.js` コードのすぐ上に、コード `s.loadModule("AudienceManagement");` を追加します。
1. 以下のコードを更新およびコピーして、`AppMeasurement.js` ファイルの `doPlugins` 関数に追加します。

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>`audienceManagement.setup` 関数は、パラメーターを の [!DNL Audience Manager] 関数と共有し、このコードで設定できます。`DIL.create`これらのパラメーターについて詳しくは、 [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create) を参照してください。

## コード要素の定義 {#code-elements-defined}

コードサンプルの重要な変数の定義を次の表に示します。

| パラメーター | 説明 |
|--- |--- |
| `partner` | 必須。これは、[!DNL Adobe]によって割り当てられたパートナー名です。「[!UICONTROL partner ID]」や「パートナーサブドメイン」と呼ばれることもあります。パートナー名が不明な場合は、[!DNL Adobe]のコンサルタントまたは[カスタマーケア](https://helpx.adobe.com/jp/marketing-cloud/contact-support.html)にお問い合わせください。 |
| `containerNSID` | 必須。ほとんどの場合は、`"containerNSID":0` に設定できます。ただし、会社が異なるコンテナを使用して ID 同期をカスタマイズする必要がある場合、ここでそのコンテナ ID を指定できます。 |
| `uuidCookie` | オプションです。この設定を使用すると、ファーストパーティドメインに [!DNL Adobe] Cookie を設定できます。この [!DNL cookie] には、[UUID](../../reference/ids-in-aam.md) が含まれます。 |
| `visitorService` - `namespace` | 必須。`namespace`[!DNL AudienceManagement] パラメーターは、[!UICONTROL AppMeasurement] バージョン 2.10 以降にバンドルされている モジュールを使用する場合に必要です。この [!UICONTROL AudienceManagement] モジュールでは、[!UICONTROL Adobe Experience Platform Identity Service] 3.3 以降を使用する必要があります。<br><br>[!UICONTROL Experience Cloud Organization ID]は、会社が [!UICONTROL Experience Cloud] に新規登録したときに生成される ID です。「[組織とアカウントのリンク](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/organizations.html)」で、会社の組織 ID を確認します。 |

## 結果：[!DNL Audience Manager] へのデータ転送 {#results-data-forwarding}

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
>[!DNL Analytics] から [!DNL Audience Manager] に送信された変数は、特別なプレフィックスを使用します。[!DNL Audience Manager] 特性を作成する場合は、これらのプレフィックスについて理解し、考慮に入れる必要があります。これらのプレフィックスの詳細については、[キー変数のプレフィックス要件](../../features/traits/trait-variable-prefixes.md)を参照してください。
