---
description: DIL とその動作の概要です。
seo-description: DIL とその動作の概要です。
seo-title: データ統合ライブラリ（DIL）について
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, '
solution: Audience Manager
title: データ統合ライブラリ（DIL）について
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL の実装
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 100%

---

# [!DNL Data Integration Library]（DIL）について {#understanding-the-data-integration-library-dil}

[!DNL Audience Manager DIL] コードライブラリの概要、導入方法、使用可能なコードメソッドについて説明します。

>[!IMPORTANT]
>
>バージョン 8.0（2018 年 8 月にリリース）より、[!UICONTROL DIL] は、[Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)のバージョン 3.3 以降に強く依存しています。[!DNL ID Service] を利用して、ID 同期や URL 宛先を有効にします。[!DNL ID Service] が見つからない、古い、または設定されていない場合は、エラーが発生します。
>
>[!DNL DIL]および [!DNL Adobe Experience Platform Identity Service] ライブラリの実装と管理には、[!DNL Adobe Experience Platform Launch] を使用することをお勧めします。

ただし、アドビの GitHub ページから Experience Cloud および [!DNL DIL] の最新リリースをダウンロードすることもできます。以下のダウンロードリンクを参照してください。

* [Adobe Experience Platform ID サービス](https://github.com/Adobe-Marketing-Cloud/id-service/releases)のダウンロード
* [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases) のダウンロード

## DIL の目的 {#purpose-dil}

[!UICONTROL DIL] は API ライブラリです。これは、[!DNL Adobe Audience Manager] のヘルパーコードの集まりと見なすことができます。[!DNL Audience Manager] を使用するのに必要なわけではありませんが、[!UICONTROL DIL] にメソッドや関数が用意されているので、[!DNL Audience Manager] にデータを送信するためのコードを独自に開発する必要はありません。さらに、[!UICONTROL DIL] は、[Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/en/id-service/using/home.html)で提供される API とは異なります。このサービスは、各種の [!DNL Experience Cloud] ソリューションにわたって訪問者 ID を管理することを目的としています。これに対して、[!UICONTROL DIL] は以下を目的としています。

* イベントを呼び出して[データ収集サーバー](../reference/system-components/components-data-collection.md)にデータを送信する。
* データを[宛先](../features/destinations/destinations.md)に送信する。

## DIL コードの取得と実装 {#get-implement-dil-code}

[!UICONTROL DIL] コードは&#x200B;**[こちら](https://github.com/Adobe-Marketing-Cloud/dil/releases)** でダウンロードできます。バージョン 8.0（2018 年 8 月にリリース）より、[!UICONTROL DIL] は、[Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/en/id-service/using/home.html)のバージョン 3.3 以降に強く依存していることに注意してください。[!DNL ID Service] を利用して、ID 同期や[!DNL URL destinations]を有効にします。[!DNL ID Service] が見つからない、古い、または設定されていない場合は、エラーが発生します。

[!UICONTROL DIL] を操作して [!DNL Audience Manager] を手動でセットアップするのではなく、[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html?lang=ja) を使用することをお勧めします。[!DNL Adobe Experience Platform Launch] を使用するとコードのデプロイメント、配置、バージョン管理が簡単になるので、実装ツールとして導入することをお勧めします。詳しくは、[!DNL Adobe Experience Platform Launch] の [Audience Manager 拡張機能](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html?lang=ja)を参照してください。

## サンプル呼び出し {#sample-code}

[!UICONTROL DIL] では、データをイベント呼び出しで [!DNL Audience Manager] に送信します。ページからの XML HTTP リクエストがイベント呼び出しになります。`POST` メソッドを使用して、データをリクエストの本文に入れて送信します。

| イベント呼び出しの構成要素 | 説明 |
|--- |--- |
| URL | DIL イベント呼び出しでは、`https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* という構文を使用します。 |
| 本文 | 以下のサンプルで示すように、DIL ではデータをキー値ペアとして渡します。特別な接頭辞文字で、これらのキー値ペアは Audience Manager 変数またはパートナー変数として識別されます。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

以下のページも参照してください。
* [キー変数のプレフィックスの要件](../features/traits/trait-variable-prefixes.md)
* [DCS API 呼び出しでサポートされている属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 関連リンク

* [DIL のユースケースとコードサンプル](/help/using/dil/dil-use-cases.md)
* [クラスレベルの DIL メソッド](/help/using/dil/dil-class-overview/dil-start.md)
* [インスタンスレベルの DIL メソッド](/help/using/dil/dil-instance-methods.md)
* [DIL モジュール](/help/using/dil/dil-modules.md)
* [DIL ツール](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
