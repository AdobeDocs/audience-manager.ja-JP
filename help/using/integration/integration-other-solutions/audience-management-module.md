---
description: Audience Management モジュールを Adobe Analytics AppMeasurement に追加すると、Audience Manager データ統合ライブラリ（DIL）コードでページからピクセルを送信するのではなく、Analytics データを Audience Manager に転送することができます。
keywords: オーディエンス分析;analytics;ssf;サーバー側転送
seo-description: Audience Management モジュールを Adobe Analytics AppMeasurement に追加すると、Audience Manager データ統合ライブラリ（DIL）コードでページからピクセルを送信するのではなく、Analytics データを Audience Manager に転送することができます。
seo-title: Audience Management モジュールの実装
solution: Audience Manager
title: Audience Management モジュールの実装
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Audience Management モジュールの実装 {#implement-the-audience-management-module}

Add the [!UICONTROL Audience Management Module] to [!DNL Adobe Analytics] [!UICONTROL AppMeasurement] to forward [!DNL Analytics] data to Audience Manager instead of having the Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) code send a pixel from the page.

## 前提条件 {#prereqs}

このドキュメントで説明したコードの実装に加えて、以下をおこなう必要があります。

* [Experience Cloud ID サービス](https://marketing.adobe.com/resources/help/en_US/mcvid/)を実装する。
* Enable [!UICONTROL Server-Side Forwarding] for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## 実装 {#implementation}

To implement the [!UICONTROL Audience Management Module]:

1. Download [!UICONTROL AppMeasurement] using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (requires version 1.5 or later).
1. ダウンロードした zip ファイルに含まれていたバージョンに [!UICONTROL AppMeasurement] コードを更新します。
1. zip ファイルの `AppMeasurement_Module_AudienceManagement.js` からすべてのコードをコピーします。`appMeasurement.js` ファイルの「`"DO NOT ALTER ANYTHING BELOW THIS LINE."`」というテキストのすぐ上に貼り付けます。
1. 前の手順で追加した `AppMeasurement_Module_AudienceManagement.js` コードのすぐ上に、コード `s.loadModule("AudienceManagement");` を追加します。
1. 以下のコードを更新およびコピーして、`doPlugins` ファイルの `AppMeasurement.js` 関数に追加します。

```js
s.AudienceManagement.setup({ 
     "partner":"partner name", 
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
>`audienceManagement.setup` 関数は、パラメーターを Audience Manager の `DIL.create` 関数と共有し、このコードで設定できます。これらのパラメーターについて詳しくは、 [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create)を参照してください。

## コード要素の定義 {#code-elements-defined}

コードサンプルの重要な変数の定義を次の表に示します。

| パラメーター | 説明 |
|--- |--- |
| `partner` | 必須。これは、アドビによって割り当てられたパートナー名です。「パートナー ID」や「パートナーサブドメイン」と呼ばれることもあります。パートナー名が不明な場合は、アドビのコンサルタントまたは[カスタマーケア](https://helpx.adobe.com/marketing-cloud/contact-support.html)にお問い合わせください。 |
| `containerNSID` | 必須。ほとんどの場合は、`"containerNSID":0` に設定できます。ただし、会社が異なるコンテナを使用して ID 同期をカスタマイズする必要がある場合、ここでそのコンテナ ID を指定できます。 |
| `uuidCookie` | オプションです。この設定を使用すると、ファーストパーティドメインに Adobe Cookie を設定できます。この Cookie には、[UUID](../../reference/ids-in-aam.md) が含まれます。 |
| `visitorService` - `namespace` | 必須。`namespace` パラメーターは、 バージョン 2.10 以降にバンドルされている AudienceManagement モジュールを使用する場合に必要です。[!UICONTROL AppMeasurement][!UICONTROL AudienceManagement] このモジュールでは3.3以降を使用 [!UICONTROL Experience Cloud ID Service] する必要があります。<br>は [!UICONTROL Experience Cloud Organization ID] 、サインアップ時に会社が提供するID [!UICONTROL Experience Cloud]です。Find out your company's Organization ID in [Organizations and Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## 結果：Audience Manager へのデータ転送 {#results-data-forwarding}

Your [!DNL Analytics] implementation sends data to Audience Manager after you have:

* Enabled [!UICONTROL Server-Side Forwarding] (talk to your consultant about this feature);
* ID サービスを実装する。
* Installed the [!UICONTROL Audience Management Module].

このプロセスは、以下の場合に [!DNL Audience Manager] にデータを送信します。

* ページ表示の呼び出し時。
* 追跡されたリンクから。
* ビデオマイルストーンおよびハートビートビデオ表示から。

>[!NOTE]
>
>[!DNL Analytics] から Audience Manager に送信された変数は、特別なプレフィックスを使用します。Audience Manager 特性を作成する場合は、これらのプレフィックスについて理解し、考慮に入れる必要があります。これらのプレフィックスについて詳しくは、[キー変数のプレフィックスに関する要件](../../features/traits/trait-variable-prefixes.md)を参照してください。