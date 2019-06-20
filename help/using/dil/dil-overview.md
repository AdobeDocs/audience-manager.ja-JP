---
description: DIL とその動作の概要です。
seo-description: DIL とその動作の概要です。
seo-title: データ統合ライブラリ（DIL）について
solution: Audience Manager
title: データ統合ライブラリ（DIL）について
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 8f2cbf8a31335762f03cad278114d9ab7c520763

---


# データ統合ライブラリ（DIL）について{#understanding-the-data-integration-library-dil}

Audience Manager DIL コードライブラリの概要、導入方法、使用可能なコードメソッドについて説明します。

>[!IMPORTANT]
>
>バージョン 8.0（2018 年 8 月にリリース）より、[!UICONTROL DIL] は、[Experience Cloud ID サービス](https://marketing.adobe.com/resources/help/en_US/mcvid/)バージョン 3.3 以降に強く依存します。ID サービスを利用して、ID 同期や URL 宛先を有効にします。ID サービスが見つからない、古い、または設定されていない場合は、エラーが発生しまます。
>
>Adobe Launch を使用して DIL ライブラリと Experience Cloud ID サービスライブラリを実装および管理することをお勧めします。

ただし、GitHubページから最新のExperience CloudおよびDILリリースをダウンロードすることもできます。以下のダウンロードリンクを参照してください。

* [Experience Cloud IDサービスのダウンロード](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* [DILをダウンロード](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL{#purpose-dil} の目的 

[!UICONTROL DIL] はAPIライブラリです。これは、[!DNL Adobe Audience Manager] のヘルパーコードの集まりとみなすことができます。[!DNL Audience Manager] を使用するのに必要なわけではありませんが、[!UICONTROL DIL] にメソッドや関数が用意されているので、[!DNL Audience Manager] にデータを送信するためのコードを独自に開発する必要はありません。さらに、[!UICONTROL DIL] は、[Experience Cloud ID サービス](https://marketing.adobe.com/resources/help/en_US/mcvid/)で提供される API とは異なります。このサービスは、各種の [!DNL Experience Cloud] ソリューションにわたって訪問者 ID を管理することを目的としています。これに対して、[!UICONTROL DIL] は以下を目的としています。

* イベントを呼び出して[データ収集サーバー](../reference/system-components/components-data-collection.md)にデータを送信する。
* データを[宛先](../features/destinations/destinations.md)に送信する。

## DIL コードの取得と実装 {#get-implement-dil-code}

[!UICONTROL DIL] コードは **[こちら](https://github.com/Adobe-Marketing-Cloud/dil/releases)** からダウンロードできます。Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. ID サービスを利用して、ID 同期や URL 宛先を有効にします。ID サービスが見つからない、古い、または設定されていない場合は、エラーが発生しまます。

[!UICONTROL DIL] を操作して [!DNL Audience Manager] を手動でセットアップするのではなく、[Adobe Launch](https://docs.adobelaunch.com/) を使用することをお勧めします。[!DNL Adobe Launch] でコードのデプロイメント、配置、バージョン管理が簡単になるので、実装ツールとしてお勧めします。[Audience Manager 拡張機能](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension)について詳しくは、Adobe Launch を参照してください。

Adobe Launch is the successor to [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## サンプル呼び出し {#sample-code}

[!UICONTROL DIL] では、データをイベント呼び出しで [!DNL Audience Manager] に送信します。ページからの XML HTTP 要求がイベント呼び出しになります。`POST` メソッドを使用して、データを要求の本文に入れて送信します。

| イベント呼び出しの構成要素 | 説明 |
|--- |--- |
| URL | DIL event calls use the following syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
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