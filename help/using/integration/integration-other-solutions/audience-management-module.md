---
description: Audience Management モジュールを Adobe Analytics AppMeasurement に追加すると、Audience Manager データ統合ライブラリ（DIL）コードでページからピクセルを送信するのではなく、Analytics データを Audience Manager に転送することができます。
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Audience Management モジュールを Adobe Analytics AppMeasurement に追加すると、Audience Manager データ統合ライブラリ（DIL）コードでページからピクセルを送信するのではなく、Analytics データを Audience Manager に転送することができます。
seo-title: Audience Management モジュールの実装
solution: Audience Manager
title: Audience Management モジュールの実装
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 75%

---


# Adobe Analytics から Audience Manager にデータを転送する方法 {#implement-the-audience-management-module}

Follow the steps in this tutorial to forward [!DNL Analytics] data to [!DNL Audience Manager] instead of having the [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) code send a pixel from the page.

>[!TIP]
>
>We recommend you use [!DNL Adobe Experience Platform Launch] to forward [!UICONTROL Analytics] data into [!DNL Audience Manager]. [!UICONTROL Launch] を使用すると、このページで示すように、[!DNL AppMeasurement] に手動でコードをコピーする必要がなくなります。

## 前提条件 {#prereqs}

このドキュメントで説明した拡張機能の有効化やコードの実装に加えて、以下をおこなう必要があります。

* [Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を実装する。
* [ でレポートスイートの](https://docs.adobe.com/help/ja-JP/analytics/admin/admin-tools/server-side-forwarding/ssf.html)サーバー側転送[!UICONTROL Adobe Analytics Admin Console]を有効にする。

## 実装 {#implementation}

There are two methods to implement data forwarding from [!DNL Adobe Analytics] to [!DNL Audience Manager], depending on the tag management solution that you use.

### Adobe Experience Platform Launch を使用した実装

[!DNL Adobe] Launch [拡張機能を使用して、実装](https://docs.adobe.com/content/help/ja-JP/launch/using/overview.html) とプロパティ [!DNL Adobe Analytics] に対して使用することをお勧めし [!DNL Audience Manager] ます。 この場合、コードを手動でコピーする必要はありません。Instead, you must enable data sharing in the [!DNL Analytics Launch] extension, as shown in the image below. [Adobe Analytics 拡張機能](https://docs.adobe.com/content/help/ja-JP/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager)のドキュメントも参照してください。

>[!TIP]
>
>If you install the [!DNL Adobe Analytics] extension, *do not* also install the [!DNL Audience Manager] extension. Forwarding data from the [!DNL Analytics] extension replaces the [!DNL Audience Manager] extension functionality.

![Adobe Analytics 拡張機能から Audience Manager へのデータ転送を有効にする方法 ](/help/using/integration/assets/analytics-to-aam.png)

### Adobe Digital Tag Management（DTM）またはその他のタグ管理ソリューションを使用した実装

>[!WARNING]
>
>[!DNL Adobe] 2020年末までに日没 [!DNL DTM] する計画を発表しました。 For more information and scheduling, see [!DNL DTM] Plans for a Sunset in the [Adobe community forums](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

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
| `partner` | 必須。This is a partner name assigned to you by [!DNL Adobe]. 「パートナー ID」や「パートナーサブドメイン」と呼ばれることもあります。Contact your [!DNL Adobe] consultant or [Customer Care](https://helpx.adobe.com/jp/marketing-cloud/contact-support.html) if you don&#39;t know your partner name. |
| `containerNSID` | 必須。ほとんどの場合は、`"containerNSID":0` に設定できます。ただし、会社が異なるコンテナを使用して ID 同期をカスタマイズする必要がある場合、ここでそのコンテナ ID を指定できます。 |
| `uuidCookie` | オプションです。この設定を使用すると、ファーストパーティドメインに [!DNL Adobe] Cookie を設定できます。この Cookie には、[UUID](../../reference/ids-in-aam.md) が含まれます。 |
| `visitorService` - `namespace` | 必須。`namespace`[!DNL AudienceManagement] パラメーターは、[!UICONTROL AppMeasurement] バージョン 2.10 以降にバンドルされている モジュールを使用する場合に必要です。この [!UICONTROL AudienceManagement] モジュールでは、[!UICONTROL Adobe Experience Platform Identity Service] 3.3 以降を使用する必要があります。<br>[!UICONTROL Experience Cloud Organization ID]は会社が [!UICONTROL Experience Cloud] に新規登録したときに生成される ID です。「[組織とアカウントのリンク](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/organizations.html)」で、会社の組織 ID を確認します。 |

## 結果：Audience Manager へのデータ転送 {#results-data-forwarding}

以下の手順をおこなった後、[!DNL Analytics] 実装は にデータを送信します。[!DNL Audience Manager]

* [!UICONTROL Server-Side Forwarding]を有効にする（この機能については、コンサルタントにお問い合わせください）。
* を実装 [!DNL Adobe Experience Platform Identity Service]。
* このチュートリアルの実装手順に従う。

このプロセスは、以下の場合に [!DNL Audience Manager] にデータを送信します。

* ページ表示の呼び出し時。
* 追跡されたリンクから。
* ビデオマイルストーンおよびハートビートビデオ表示から。

>[!NOTE]
>
>The variables sent to [!DNL Audience Manager] from [!DNL Analytics] use special prefixes. You need understand and take these prefixes into account when creating [!DNL Audience Manager] traits. これらのプレフィックスの詳細については、「キー変数の [プレフィックス要件](../../features/traits/trait-variable-prefixes.md)」を参照してください。