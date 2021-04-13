---
description: 定義および関連情報へのリンク。
seo-description: 定義および関連情報へのリンク。
seo-title: 用語集
solution: Audience Manager
title: 用語集
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
feature: リファレンス
exl-id: 9e2ee3d3-01b2-4038-abda-fedf0f16f163
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 100%

---

# 用語集 {#glossary}

定義および関連情報へのリンク。

## A-B {#a-b}

**アルゴリズムモデリング**

[!UICONTROL Algorithmic Modeling]は、既に特定されているコアユーザーを超える範囲のユーザーにリーチするために使用します。自動化されたデータ分析を通して、固有のオーディエンスを新しく発見できます。[!UICONTROL Algorithmic Models] は **[!UICONTROL Audience Data > Models]** で管理します。

詳細については、[アルゴリズムモデルについて](../features/algorithmic-models/algo-models-overview.md)を参照してください。

**BAAAM**

[!UICONTROL Bulk Management Tools]をインストールします。[!DNL Audience Manager] の[!UICONTROL Bulk Management Tools]は Microsoft Excel ベースのツールセットで、1 回の操作で一度に複数のオブジェクトの作成、修正および削除ができます。データソース、派生シグナル、宛先、フォルダー、セグメントおよび特性を処理できます。この機能は Microsoft Excel スプレッドシートのマクロを使用し、[!DNL Audience Manager] API の認証済みの安全な呼び出しをおこないます。

詳しくは、[一括管理ツール](../reference/bulk-management-tools/bulk-management-intro.md)を参照してください。

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]をインストールします。[!UICONTROL CDF] ファイルとは、[!DNL Audience Manager] で収集されたデータを一括ダウンロードしたものです。これにより、ユーザーインターフェイスに課せられた制限を超えて [!DNL Audience Manager] データを処理できます。[!UICONTROL CDF] ファイルには、[!DNL Audience Manager] イベント呼び出し（`/event`）でサーバーに送信されるデータと同じものが含まれています。ユーザー ID、特性 ID、セグメント ID など、イベント呼び出しで表されるあらゆるパラメーターが含まれます。

[顧客データフィード](../features/cdf-files.md)を参照してください。

**CRM ID**

CRM ID は、お客様が自身の CRM システム内でユーザーを識別するための ID です。Audience Manager では、CRM ID ではなく DPUUID という用語を使用します。

[Audience Manager の ID のインデックス](../reference/ids-in-aam.md)の DPUUID を参照してください。



**Customer Addressable Audience**

[アドレス可能オーディエンス](/help/using/features/addressable-audiences.md)では、この指標は次のデバイスを表します。
* ルックバック期間にルールベースの特性またはオンボードの特性に適合し、
   **かつ**
* 同期の時間に関係なく、選択した宛先と ID が同期している。



**Customer Attributes**

[!DNL Experience Cloud Core Services] 製品ドキュメントの[顧客属性](https://docs.adobe.com/content/help/ja-JP/core-services/interface/customer-attributes/attributes.html)を参照してください。



**Customer Match Rate**

Customer Addressable Audience ÷ Customer Total Audience を％で表現したもの。[アドレス可能なオーディエンス](/help/using/features/addressable-audiences.md)を参照してください。



**Customer Total Audience**

[アドレス可能なオーディエンス](/help/using/features/addressable-audiences.md)で、ルックバック期間に、御社のシステムにおけるルールベースの特性、またはオフラインファイルからのオンボードの特性に適合したデバイスの数。



**demdex.net**

Demdex.net は [!DNL Adobe] が管理しているレガシーのドメインです。[!DNL Audience Manager] の買収前の名前（[!DNL Demdex]）を表しています。[!DNL Adobe] は 2011 年に [!DNL Demdex] を買収し、[!DNL Audience Manager] というブランド名に変更しました。`demdex.net` への HTTP 呼び出しはすべて、[!DNL Adobe]に送信される呼び出しとなります。

[Demdex ドメインの呼び出しについて](../reference/demdex-calls.md)を参照してください。



**DAID**

[!UICONTROL Device Advertising IDs] は一意のデバイス ID で、モバイルデバイスの識別に使用されます。これらの ID はアドビではなく、デバイス製造元によって割り当てられます。[!DNL Audience Manager] は、iOS および Android デバイス ID をサポートしています。

[Audience Manager の ID のインデックス](../reference/ids-in-aam.md)を参照してください。



**宛先**

[!DNL Audience Manager] において、宛先とは、データを共有したいサードパーティシステム（広告サーバー、DSP、広告ネットワークなど）になります。UI 内の [!UICONTROL Destination Builder] はこれらのデータ配信プロセスを作成および管理するためのツールです。[!DNL Audience Manager] の宛先に関する機能には、**[!UICONTROL Audience Data > Destinations]** からアクセスできます。



**DIL**

[!UICONTROL Data Integration Library]は、ユーザーインタラクションデータを収集するために [!DNL Audience Manager] で使用される API ライブラリです。詳しくは、[データ統合ライブラリ（DIL）API](../dil/dil-overview.md) を参照してください。



**dpm**

[!UICONTROL Data Provider Match]をインストールします。これにより、[!DNL Audience Manager] または ID サービスからの呼び出しで同期または ID リクエストのために顧客データが渡されていることが、[!DNL Adobe] の社内システムにわかります。[Demdex ドメインの呼び出しについて](../reference/demdex-calls.md)を参照してください。

## E-F {#e-f}

**Experience Cloud ID (ECID)**

以前は [!DNL Marketing Cloud] ID（MID または MCID）と呼ばれていたものです。この ID は [!DNL Experience Cloud] ID サービスの中心となるものです。サイト訪問者の永続的な一意の識別子です。[Cookie と Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/intro/cookies.html)を参照してください。



**フォルダー特性**

フォルダー分類における、特性の自動的なグループ化。階層内の各フォルダーで、セグメントを定義できる特性が自動的に作成されます。

 [フォルダー特性について](../features/traits/about-folder-traits.md)を参照してください。



**頻度キャップ**

広告主がエンドユーザーに対して所定のクリエイティブを表示できる回数の制限。[!UICONTROL Segment Builder]では、様々な方法で頻度キャップを設定できます。

詳しくは、[最新性と頻度](../features/segments/recency-and-frequency.md)を参照してください。

## G-H {#g-h}

**GAID**

Google 広告 ID。Android オペレーティングシステムを実行しているハードウェアデバイスに対して Google によって割り当てられる一意のデバイス ID です。[Audience Manager の ID のインデックス](../reference/ids-in-aam.md)を参照してください。



**GUID**

Globally Unique Identifier（グローバルに一意の ID）の頭字語。[!DNL Audience Manager] では、GUID という用語は使用しません。GUID は [!DNL Audience Manager]Audience Manager UUID と呼ばれます。[Audience Manager の ID のインデックス](../reference/ids-in-aam.md)を参照してください。

## I-J {#i-j}

**IDFA**

広告主の識別子。Apple によって製品に割り当てられる一意のデバイス ID。[Audience Manager の ID のインデックス](../reference/ids-in-aam.md)を参照してください。



**インバウンド**

[!DNL Audience Manager] に対して他のソースからオーディエンスデータを送信できるプロセス。詳しくは、[オーディエンスデータの送信](/help/using/integration/sending-audience-data/send-audience-data.md)を参照してください。



**統合コード**

[!DNL Audience Manager] UI または API を使用して特性、セグメントまたはデータソースを作成する際に、オプションで統合コードを追加できます。統合コードは以下のように様々な目的に使用されます。

* [!UICONTROL Traits]：統合コードは、内部のビジネスプロセスで使用される ID や SKU などの値のフィールドとなります。オプションです。
* [!UICONTROL Segments]：統合コードは、ユーザー定義 ID などの会社固有の情報のフィールドとなります。オプションです。
* [!UICONTROL Data Sources]：統合コードは、クロスデバイスのデータソースを作成したり、Adobe Experience Platform ID サービスを使用したり、[!UICONTROL Profile Merge Rules] を使用して作業する場合に必要となります。詳しくは、[データソースの作成](../features/manage-datasources.md#create-data-source)を参照してください。

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

[アルゴリズムモデリング](../reference/aam-glossary.md#a-b)を参照してください。

## M-N {#m-n}

**MCID**、**MID**

[Experience Cloud ID](../reference/aam-glossary.md#e-f) を参照してください。

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]をインストールします。[!UICONTROL PCS] は、Apache Cassandra 上で動作する大規模なデータベースです。サーバーからサーバーへのデータ転送および [!DNL DCS] から受信したアクティブユーザーのデータを格納します。[!UICONTROL PCS] データは、デバイス ID、認証済みプロファイル ID、およびそれらに関連付けられた特性で構成されます。

[データ収集コンポーネント](../reference/system-components/components-data-collection.md)を参照してください。



**プロファイルリンク**

詳しくは、[定義済みのプロファイルの結合ルールオプション](../features/profile-merge-rules/merge-rule-definitions.md)を参照してください。



**プロファイル結合ルール**

[!UICONTROL Profile Merge Rules]を使用すると、[!DNL Audience Manager] がセグメント化に使用するデータのタイプを制御できます。

詳しくは、[定義済みのプロファイルの結合ルールオプション](../features/profile-merge-rules/merge-rule-definitions.md)を参照してください。

## Q-R {#q-r}

**適合**

ある特性に適合するサイト訪問者のアクション。 [訪問者プロファイルビューア](../features/visitor-profile-viewer.md)ツールを使用して特定のユーザーの特性への適合情報を取得できます。

## S-T {#s-t}

**セグメント**

セグメント（またはオーディエンス）は、共通の属性を共有する一連のユーザーです。

詳しくは、[セグメント：目的、構成およびルール](../features/segments/segments-purpose.md)を参照してください。



**Segment Addressable Audience**

[アドレス可能なオーディエンス](/help/using/features/addressable-audiences.md)において、レポートのルックバック期間中にセグメントに属しており、サイト上で ID 同期がアクティブとなっているユーザーの数。セグメントには、[Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md) で取得した経由で、自社のファーストパーティデータと、セカンドパーティおよびサードパーティデータを含むことができます。



**Segment Total Population**

[アドレス可能なオーディエンス](/help/using/features/addressable-audiences.md)では、この指標はレポートのルックバック期間内にセグメントに属していたすべてのデバイスの数を表します。



**Segment Match Rate**

Segment Addressable Audience ÷ Total Segment Population の総数を％で表現したもの。[アドレス可能なオーディエンス](/help/using/features/addressable-audiences.md)を参照してください。



**シグナル**

シグナルは [!DNL Audience Manager] で最小のデータ単位で、キー値ペアとして表現されます。

詳しくは、[シグナル、特性およびセグメント](../reference/signal-trait-segment.md)を参照してください。



**特性**

特性は、1 つ以上のシグナルの組み合わせです。詳しくは、[シグナル、特性およびセグメント](../reference/signal-trait-segment.md)を参照してください。



**Trait Population**

[セグメントビルダーにおける特性およびセグメント母集団データ](../features/segments/segment-builder-data.md)を参照してください。

**TTL (Time-to-Live)**

TTL は、対象として認定された訪問者が特性にとどまる日数を定義します。TTL は、セグメントではなく、特性に対して設定されます。訪問者は、TTL 期間が終了するまでに対象となる特性が確認されない場合、セグメントから除外されます。詳しくは、[セグメントと特性の有効期間についての説明](/help/using/features/traits/segment-ttl-explained.md)を参照してください。



## U-V {#u-v}

**UUID**

[!DNL Audience Manager] の一意のユーザー ID。[Audience Manager の ID のインデックス](../reference/ids-in-aam.md)を参照してください。



**訪問者 ID**

[!DNL Experience Cloud] ID サービス（旧称、訪問者 ID）は、[!DNL Experience Cloud] のすべてのソリューションにわたって訪問者を識別する、普遍的、永続的な ID を提供します。

[Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)のドキュメントを参照してください。

## W-X-Y-Z {#w-z}
