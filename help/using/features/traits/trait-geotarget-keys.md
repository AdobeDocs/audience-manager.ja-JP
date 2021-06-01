---
description: Audience Manager アカウントのすべてのプロパティにわたって地理変数を使用してユーザーをターゲティングするのに使用できるプラットフォームレベルの共通のキーと値のペアについて説明します。
seo-description: Audience Manager アカウントのすべてのプロパティにわたって地理変数を使用してユーザーをターゲティングするのに使用できるプラットフォームレベルの共通のキーと値のペアについて説明します。
seo-title: プラットフォームレベルのキーによる GeoTargeting（地域に基づくターゲティング）
solution: Audience Manager
title: プラットフォームレベルのキーによる GeoTargeting（地域に基づくターゲティング）
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: 特性
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 100%

---

# プラットフォームレベルのキーによる GeoTargeting（地域に基づくターゲティング）{#geotargeting-with-platform-level-keys}

Audience Manager アカウントのすべてのプロパティにわたって地理変数を使用してユーザーをターゲティングするのに使用できるプラットフォームレベルの共通のキーと値のペアについて説明します。

<!-- c_tb_platform_vars.xml -->

## プラットフォームレベル変数の目的 {#platform-variables}

プラットフォームレベルの変数を使用すると、特定のサイトからデータを渡して、[!DNL Audience Manager] アカウントのすべてのプロパティにわたるターゲティングに使用できます。これらの変数は[キー値ペア](../../reference/key-value-pairs-explained.md)で構成され、以下に示すように、キーには `d_` というプレフィックスが付加されます。

## プラットフォームレベルキーへの値の追加 {#adding-values}

一部のプラットフォームレベルキーについては、ユーザー自身で値を指定できます。その他については、キーは、イベント呼び出しで渡された、対応する [!DNL IP] アドレスに関連付けられます。どちらの場合でも、[!UICONTROL Trait Builder]で特性を作成する際には、値を指定する必要があります。

## ユーザー定義のプラットフォームレベルキー {#user-defined-keys}

これらのキーと値のペアを使用して特性を作成する際には、値を指定します。

| キー | ターゲティングの場合 |
|---|---|
| `d_zx` | 郵便番号（例：`d_zx=10022`）。 |

## IP アドレスで定義されたプラットフォームレベルキー {#keys-ip-address}

アドビでは、[Digital Envoy](https://www.digitalenvoy.com/) と連携し、以下に示す人口統計データと地理的データを取得して更新します。これらのキーの値は、[!DNL IP] アドレスを対応する地理データおよび人口統計データと照合することで、決定されます。それでも、[!UICONTROL Trait Builder]でキーと値のペアを作成する際には、値パラメーターを入力する必要があります。

| キー | ターゲティングの場合 |
|--- |--- |
| d_area_code | [北米地域コード](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)。例： <ul><li>**特性**：d_area_code=801</li><li>**特性名**：Utah</li></ul> |
| d_city | 都市。[都市リスト](assets/d_city.txt)をダウンロードします。例： <ul><li>特性：d_city=bonn</li><li>特性名：Bonn</li></ul> **ヒント**：`d_city` と `d_country` を組み合わせて使用すれば、異なる国にある同じ名前の都市をターゲットにすることができます。`d_postal_code` を使用すると、さらに具体的にターゲットを絞り込むことができます。 |
| d_country | ISO 国コードに対応する値。各種コードの検索可能なリストについては、[ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home) を参照してください。<br>英国のターゲティングは、ISO 3166 に従わない特例です。英国では、ターゲティングに「GB」ではなく「UK」を使用する必要があります。オランダ領アンティルをターゲティングするためのコード「AN」は、2010 年から廃止されました。この地域は、5 つの個別の領土単位に分割されました。オランダ領アンティルをターゲティングする場合、「AN」は使用せず、「CW」、「SX」および「BQ」の国コードの組み合わせを使用するのがよいようです。例：<br>特性：d_country=CZ <br>特性名：Czech Republic<br>特性：d_country=UK<br>特性名：United Kingdom<br>特性：d_country=CW OR d_country=SX OR d_country=BQ<br>特性名：Netherlands Antilles |
| d_dma_code | 大都市圏 DMA コード。[DMA 地域リスト](assets/DMAregions.csv)（.csv 形式）をダウンロードします。例： <ul><li>特性：d_dma_code=807</li><li>特性名：San Francisco</li></ul> |
| d_lat | 緯度（例：d_lat=40.75）。[緯度リスト](assets/d_lat.txt)をダウンロードします。 |
| d_long | 経度（例：d_long=73.98）。[経度リスト](assets/d_long.txt)をダウンロードします。 |
| d_postal_code | 郵便番号（拡張 +4 コードを除く）。[郵便番号リスト](assets/d_postal_code.txt)をダウンロードします。例： <ul><li>特性：d_postal_code=84004 </li><li>特性名：Alpine</li></ul> |
| d_state | 米国の州の 2 文字の略称。[州コードリスト](assets/d_state.txt)をダウンロードします。例： <ul><li>特性：d_state=NY </li><li>特性名： New York</li></ul>d_state には、様々な国の異なる州の重複する値が含まれています。例えば、d_state == &quot;on&quot; は、Ontario（カナダ）、Ondo（ナイジェリア）、Oshana（ナミビア）といった複数の州に一致します。地域ターゲティングをより詳細におこなうために、このシグナルを d_country などの他のシグナルと組み合わせて使用することをお勧めします。 |
| d_region | 地域の英数字 ID。[地域リスト](assets/Country_RegionCodes_City.csv)をダウンロードします。次に、このリストを使用して、地域 ID を地域名と照合します。 |
| d_isp | ISP／組織。[ISP リスト](assets/d_isp.txt)をダウンロードします。 |

[すべての位置ベースのシグナル](assets/all.txt)のリストには、前述したすべてのシグナルが含まれ、次の順序で並べられています。`d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [キー変数のプレフィックスに関する要件](../../features/traits/trait-variable-prefixes.md)

