---
description: Audience Management モジュールを Adobe Analytics AppMeasurement に追加すると、Audience Manager データ統合ライブラリ（DIL）コードでページからピクセルを送信するのではなく、Analytics データを Audience Manager に転送することができます。
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Audience Management モジュールを Adobe Analytics AppMeasurement に追加すると、Audience Manager データ統合ライブラリ（DIL）コードでページからピクセルを送信するのではなく、Analytics データを Audience Manager に転送することができます。
seo-title: Audience Management モジュールの実装
solution: Audience Manager
title: Audience Management モジュールの実装
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 7e8ba292f2f901b1323d30d682066b49df885a0c

---


# Adobe AnalyticsからAudience Managerにデータを転送する方法 {#implement-the-audience-management-module}

Follow the steps in this tutorial to forward [!DNL Analytics] data to Audience Manager instead of having the Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) code send a pixel from the page.

>[!TIP]
>
>データをAudience Managerに転送す [!UICONTROL Adobe Launch] るためにを使 [!UICONTROL Analytics] 用することをお勧めします。 [!UICONTROL Launch] を使用すると、このページで示すように、[!UICONTROL AppMeasurement] に手動でコードをコピーする必要がなくなります。

## 前提条件 {#prereqs}

このドキュメントで説明する拡張機能の有効化やコードの実装に加えて、次の作業も行う必要があります。

* [Experience Cloud ID サービス](https://marketing.adobe.com/resources/help/en_US/mcvid/)を実装する。
* Enable [Server-Side Forwarding](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## 実装 {#implementation}

Adobe AnalyticsからAudience Managerへのデータ転送は、使用するタグ管理ソリューションに応じて、2つの方法で実装できます。

### Adobe Launchを使用した実装

Adobe AnalyticsおよびAudience Managerをプロパ [ティに実装するには](https://docs.adobe.com/content/help/en/launch/using/overview.html) 、Launch拡張機能を使用することをお勧めします。 この場合、コードを手動でコピーする必要はありません。 代わりに、以下の画像に示すように、Analytics Launch拡張でデータ共有を有効にする必要があります。 Adobe Analytics Extensionのドキュメ [ントも参照してください](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) 。

>[!TIP]
>
>Adobe Analytics拡張機能をインストールする場合は、Audience Manager *拡張機能* もインストールしないでください。 Analytics拡張機能からのデータの転送は、Audience Manager拡張機能に代わるものです。

![Adobe Analytics拡張機能からAudience Managerへのデータ共有を有効にする方法](/help/using/integration/assets/analytics-to-aam.png)

### Adobe Digital Tag Management(DTM)またはその他のタグ管理ソリューションを使用した実装


>[!WARNING]
>
>アドビは、2020年末までにDTMの日没を予定しています。 詳しくは、 [AdobeコミュニティフォーラムのDTM Plans for a Sunsetを参照してください](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)。

Adobe DTMまたは他のタグ管 [!UICONTROL Audience Management Module] 理ソリ [ューションを使用して](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) 、以下を実装します。

1. [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)（バージョン 1.5 以降が必要）を使用して、[!UICONTROL AppMeasurement] をダウンロードします。
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
>`audienceManagement.setup` 関数は、パラメーターを Audience Manager の `DIL.create` 関数と共有し、このコードで設定できます。これらのパラメーターについて詳しくは、 [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create)を参照してください。

## コード要素の定義 {#code-elements-defined}

コードサンプルの重要な変数の定義を次の表に示します。

| パラメーター | 説明 |
|--- |--- |
| `partner` | 必須。これは、アドビによって割り当てられたパートナー名です。「パートナー ID」や「パートナーサブドメイン」と呼ばれることもあります。パートナー名が不明な場合は、アドビのコンサルタントまたは[カスタマーケア](https://helpx.adobe.com/marketing-cloud/contact-support.html)にお問い合わせください。 |
| `containerNSID` | 必須。ほとんどの場合は、`"containerNSID":0` に設定できます。ただし、会社が異なるコンテナを使用して ID 同期をカスタマイズする必要がある場合、ここでそのコンテナ ID を指定できます。 |
| `uuidCookie` | オプションです。この設定を使用すると、ファーストパーティドメインに Adobe Cookie を設定できます。この Cookie には、[UUID](../../reference/ids-in-aam.md) が含まれます。 |
| `visitorService` - `namespace` | 必須。`namespace` パラメーターは、[!UICONTROL AppMeasurement] バージョン 2.10 以降にバンドルされている AudienceManagement モジュールを使用する場合に必要です。この [!UICONTROL AudienceManagement] モジュールでは、[!UICONTROL Experience Cloud ID Service] 3.3 以降を使用する必要があります。<br>[!UICONTROL Experience Cloud Organization ID]は会社が [!UICONTROL Experience Cloud] に新規登録したときに生成される ID です。「[組織とアカウントのリンク](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)」で、会社 の組織 ID を確認します。 |

## 結果：Audience Manager へのデータ転送 {#results-data-forwarding}

以下の手順をおこなった後、[!DNL Analytics] 実装は Audience Manager にデータを送信します。

* [!UICONTROL Server-Side Forwarding]を有効にする（この機能については、コンサルタントにお問い合わせください）。
* Experience Cloud IDサービスを実装しました。
* このチュートリアルの導入手順に従いました。

このプロセスは、以下の場合に [!DNL Audience Manager] にデータを送信します。

* ページ表示の呼び出し時。
* 追跡されたリンクから。
* ビデオマイルストーンおよびハートビートビデオ表示から。

>[!NOTE]
>
>[!DNL Analytics] から Audience Manager に送信された変数は、特別なプレフィックスを使用します。Audience Manager 特性を作成する場合は、これらのプレフィックスについて理解し、考慮に入れる必要があります。これらのプレフィックスについて詳しくは、[キー変数のプレフィックスに関する要件](../../features/traits/trait-variable-prefixes.md)を参照してください。