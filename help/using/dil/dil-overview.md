---
description: DIL とその動作の概要です。
seo-description: DIL とその動作の概要です。
seo-title: データ統合ライブラリ（DIL）について
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: データ統合ライブラリ（DIL）について
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# データ統合ライブラリ（DIL）について{#understanding-the-data-integration-library-dil}

Audience Manager DIL コードライブラリの概要、導入方法、使用可能なコードメソッドについて説明します。

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. ID サービスを利用して、ID 同期や URL 宛先を有効にします。ID サービスが見つからない、古い、または設定されていない場合は、エラーが発生しまます。
>
>DILおよびAdobe Experience Platform Identity Serviceライブラリの実装と管理には、Adobe Experience Platform Launchを使用することをお勧めします。

ただし、アドビの GitHub ページから Experience Cloud および DIL の最新リリースをダウンロードすることもできます。以下のダウンロードリンクを参照してください。

* [Adobe Experience Platform Identity Serviceのダウンロード](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* ダウンロ [ード](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL{#purpose-dil} の目的 

[!UICONTROL DIL] は API ライブラリです。これは、[!DNL Adobe Audience Manager] のヘルパーコードの集まりとみなすことができます。[!DNL Audience Manager] を使用するのに必要なわけではありませんが、[!UICONTROL DIL] にメソッドや関数が用意されているので、[!DNL Audience Manager] にデータを送信するためのコードを独自に開発する必要はありません。Also, [!UICONTROL DIL] is different than the API provided by the [Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/). このサービスは、各種の [!DNL Experience Cloud] ソリューションにわたって訪問者 ID を管理することを目的としています。これに対して、[!UICONTROL DIL] は以下を目的としています。

* イベントを呼び出して[データ収集サーバー](../reference/system-components/components-data-collection.md)にデータを送信する。
* データを[宛先](../features/destinations/destinations.md)に送信する。

## DIL コードの取得と実装 {#get-implement-dil-code}

[!UICONTROL DIL] コードはこちらからダウンロードで **[きます](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。 Please note that starting with version 8.0 (released August 2018),[!UICONTROL DIL]has a hard dependency on the[Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. ID サービスを利用して、ID 同期や URL 宛先を有効にします。ID サービスが見つからない、古い、または設定されていない場合は、エラーが発生しまます。

Rather than work with [!UICONTROL DIL] and set up [!DNL Audience Manager] manually, we recommend that you use [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) instead. [!DNL Adobe Experience Platform Launch] でコードのデプロイメント、配置、バージョン管理が簡単になるので、実装ツールとしてお勧めします。Read more about the [Audience Manager extension](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Experience Platform Launch.

Adobe Experience Platform Launch is the successor to [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## サンプル呼び出し {#sample-code}

[!UICONTROL DIL] では、データをイベント呼び出しで [!DNL Audience Manager] に送信します。ページからの XML HTTP 要求がイベント呼び出しになります。`POST` メソッドを使用して、データを要求の本文に入れて送信します。

| イベント呼び出しの構成要素 | 説明 |
|--- |--- |
| URL | DIL イベント呼び出しでは、`https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* という構文を使用します。 |
| 本文 | 以下のサンプルで示すように、DIL ではデータをキー値ペアとして渡します。特別な接頭辞文字で、これらのキー値ペアは Audience Manager 変数またはパートナー変数として識別されます。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

以下のページも参照してください。
* [キー変数のプレフィックスに関する要件](../features/traits/trait-variable-prefixes.md)
* [DCS API 呼び出しでサポートされている属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 関連リンク

* [DIL のユースケースとコードサンプル](/help/using/dil/dil-use-cases.md)
* [クラスレベルの DIL メソッド](/help/using/dil/dil-class-overview/dil-start.md)
* [インスタンスレベルの DIL メソッド](/help/using/dil/dil-instance-methods.md)
* [DIL モジュール](/help/using/dil/dil-modules.md)
* [DIL ツール](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)