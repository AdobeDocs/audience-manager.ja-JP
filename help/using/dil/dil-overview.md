---
description: DIL とその仕組みの概要です。
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: データ統合ライブラリ（DIL）について
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
TQID: https://experienceleague.adobe.com/SyaOtcmDa6IwaoPVjv-G6zvdnFa7ZVDaGP7MaX4RaBk
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: b82b475d-1e7d-46c6-9172-1f9c73004b11id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2: id: d7e573ad-4eda-46ec-90c4-239e75362af9id: f8c1669e-86ba-49c4-b622-9dfa07854df8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 473
ht-degree: 86%

---

# [!DNL Data Integration Library]（DIL）について {#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>2023年7月以降、Adobeは[!DNL Data Integration Library (DIL)]と[!DNL DIL]拡張機能の開発を中止しました。
>
>既存のお客様は、引き続き[!DNL DIL]実装を使用できます。 ただし、Adobeはこの時点を超えて[!DNL DIL]を開発しません。 お客様は、長期的なデータ収集戦略について[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を評価することをお勧めします。
>
>2023年7月以降に新しいデータ収集インテグレーションを導入するお客様は、代わりに[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を使用してください。

[!DNL Audience Manager DIL] コードライブラリの概要、導入方法、使用可能なコードメソッドについて説明します。

>[!IMPORTANT]
>
>バージョン 8.0（2018 年 8 月にリリース）より、[!UICONTROL DIL] は、[Adobe Experience Platform ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)のバージョン 3.3 以降に強く依存しています。[!DNL ID Service] を利用して、ID 同期や URL 宛先を有効にします。[!DNL ID Service] が見つからない、古い、または設定されていない場合は、エラーが発生します。
>
>[!DNL DIL]および [!DNL Adobe Experience Platform Identity Service] ライブラリの実装と管理には、[!DNL Adobe Experience Platform Tags] を使用することをお勧めします。

ただし、アドビの GitHub ページから Experience Cloud および [!DNL DIL] の最新リリースをダウンロードすることもできます。以下のダウンロードリンクを参照してください。

* [Adobe Experience Platform ID サービス](https://github.com/Adobe-Marketing-Cloud/id-service/releases)のダウンロード
* [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases) のダウンロード

## DIL の目的 {#purpose-dil}

[!UICONTROL DIL] は API ライブラリです。これは、[!DNL Adobe Audience Manager] のヘルパーコードの集まりと見なすことができます。[!DNL Audience Manager] を使用するのに必要なわけではありませんが、[!UICONTROL DIL] にメソッドや関数が用意されているので、[!DNL Audience Manager] にデータを送信するためのコードを独自に開発する必要はありません。さらに、[!UICONTROL DIL] は、[Adobe Experience Platform ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)で提供される API とは異なります。このサービスは、各種の [!DNL Experience Cloud] ソリューションにわたって訪問者 ID を管理することを目的としています。これに対して、[!UICONTROL DIL] は以下を目的としています。

* イベントを呼び出して[データ収集サーバー](../reference/system-components/components-data-collection.md)にデータを送信する。
* データを[宛先](../features/destinations/destinations.md)に送信する。

## DIL コードの取得と実装 {#get-implement-dil-code}

[!UICONTROL DIL] コードは&#x200B;**[こちら](https://github.com/Adobe-Marketing-Cloud/dil/releases)** でダウンロードできます。バージョン 8.0（2018 年 8 月にリリース）より、[!UICONTROL DIL] は、[Adobe Experience Platform ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)のバージョン 3.3 以降に強く依存していることに注意してください。[!DNL ID Service] を利用して、ID 同期や[!DNL URL destinations]を有効にします。[!DNL ID Service] が見つからない、古い、または設定されていない場合は、エラーが発生します。

[!UICONTROL DIL] を操作して [!DNL Audience Manager] を手動でセットアップするのではなく、[Adobe Experience Platform タグ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja) を使用することをお勧めします。[!DNL Adobe Experience Platform Tags] を使用するとコードのデプロイメント、配置、バージョン管理が簡単になるので、実装ツールとして導入することをお勧めします。詳しくは、[!DNL Adobe Experience Platform Tags] の [Audience Manager 拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=ja)を参照してください。

## サンプル呼び出し {#sample-code}

[!UICONTROL DIL] では、データをイベント呼び出しで [!DNL Audience Manager] に送信します。ページからの XML HTTP リクエストがイベント呼び出しになります。`POST` メソッドを使用して、データをリクエストの本文に入れて送信します。

| イベント呼び出しの構成要素 | 説明 |
|--- |--- |
| URL | DIL イベント呼び出しでは、`https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* という構文を使用します。 |
| 本文 | 以下のサンプルで示すように、DIL ではデータをキー値ペアとして渡します。特別な接頭辞文字で、これらのキー値ペアは Audience Manager 変数またはパートナー変数として識別されます。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

以下のページも参照してください。

* [キー変数の接頭辞に関する要件](../features/traits/trait-variable-prefixes.md)
* [DCS API 呼び出しでサポートされている属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 関連リンク

* [DIL のユースケースとコードサンプル](/help/using/dil/dil-use-cases.md)
* [クラスレベルの DIL メソッド](/help/using/dil/dil-class-overview/dil-start.md)
* [インスタンスレベルの DIL メソッド](/help/using/dil/dil-instance-methods.md)
* [DIL モジュール](/help/using/dil/dil-modules.md)
* [DIL ツール](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
