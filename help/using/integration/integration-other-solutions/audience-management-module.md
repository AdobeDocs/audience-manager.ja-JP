---
description: Audience Management モジュールを Adobe Analytics AppMeasurement に追加すると、Audience Manager データ統合ライブラリ（DIL）コードでページからピクセルを送信するのではなく、Analytics データを Audience Manager に転送することができます。
keywords: audience analytics; analytics; ssf; サーバー側転送
seo-description: Audience Management モジュールを Adobe Analytics AppMeasurement に追加すると、Audience Manager データ統合ライブラリ（DIL）コードでページからピクセルを送信するのではなく、Analytics データを Audience Manager に転送することができます。
seo-title: Audience Management モジュールの実装
solution: Audience Manager
title: Audience Management モジュールの実装
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Audience Management モジュールの実装 {#implement-the-audience-management-module}

[!UICONTROL Audience Management Module] を [!DNL Adobe Analytics] [!UICONTROL AppMeasurement] に追加すると、 Audience Manager [!UICONTROL Data Integration Library] （[!UICONTROL DIL]）コードでページからピクセルを送信する代わりに、[!DNL Analytics] データを Audience Manager に転送することができます。

## 前提条件 {#prereqs}

このドキュメントで説明したコードの実装に加えて、以下をおこなう必要があります。

* [Experience Cloud ID サービス](https://marketing.adobe.com/resources/help/en_US/mcvid/)を実装する。
* [!UICONTROL Adobe Analytics Admin Console] でレポートスイートの[!UICONTROL Server-Side Forwarding]を有効にします。

## 実装 {#implementation}

[!UICONTROL Audience Management Module] を実装するには：

1. [!UICONTROL AppMeasurement] Analyticsコードマネージャー [を使用してダウンロードします](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) （バージョン1.5以降が必要です）。
1. ダウンロードした zip ファイルに含まれていたバージョンに [!UICONTROL AppMeasurement] コードを更新します。
1. zip ファイルの `AppMeasurement_Module_AudienceManagement.js` からすべてのコードをコピーします。`appMeasurement.js` ファイルの「`"DO NOT ALTER ANYTHING BELOW THIS LINE."`」というテキストのすぐ上に貼り付けます。
1. 前の手順で追加した `AppMeasurement_Module_AudienceManagement.js` コードのすぐ上に、コード `s.loadModule("AudienceManagement");` を追加します。
1. 以下のコードを更新およびコピーして、`AppMeasurement.js` ファイルの `doPlugins` 関数に追加します。

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
| `visitorService` - `namespace` | 必須。`namespace` パラメーターは、[!UICONTROL AppMeasurement] バージョン 2.10 以降にバンドルされている AudienceManagement モジュールを使用する場合に必要です。この [!UICONTROL AudienceManagement] モジュールでは、[!UICONTROL Experience Cloud ID Service] 3.3 以降を使用する必要があります。<br>[!UICONTROL Experience Cloud Organization ID]は会社が [!UICONTROL Experience Cloud] に新規登録したときに生成される ID です。「組織」と「アカウントのリンク」で、会社 [の組織IDを確認します](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)。 |

## 結果：Audience Manager へのデータ転送 {#results-data-forwarding}

以下の手順をおこなった後、[!DNL Analytics] 実装は Audience Manager にデータを送信します。

* [!UICONTROL Server-Side Forwarding]を有効にする（この機能については、コンサルタントにお問い合わせください）。
* ID サービスを実装する。
* [!UICONTROL Audience Management Module] をインストールする。

このプロセスは、以下の場合に [!DNL Audience Manager] にデータを送信します。

* ページ表示の呼び出し時。
* 追跡されたリンクから。
* ビデオマイルストーンおよびハートビートビデオ表示から。

>[!NOTE]
>
>[!DNL Analytics] から Audience Manager に送信された変数は、特別なプレフィックスを使用します。Audience Manager 特性を作成する場合は、これらのプレフィックスについて理解し、考慮に入れる必要があります。これらのプレフィックスについて詳しくは、[キー変数のプレフィックスに関する要件](../../features/traits/trait-variable-prefixes.md)を参照してください。