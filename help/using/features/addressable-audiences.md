---
description: アドレス可能なオーディエンスの機能およびユースケースの概要です。
keywords: DIL
seo-description: アドレス可能なオーディエンスの機能およびユースケースの概要です。
seo-title: アドレス可能なオーディエンス
solution: Audience Manager
title: アドレス可能なオーディエンス
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1824'
ht-degree: 44%

---


# [!UICONTROL Addressable Audiences] {#addressable-audiences}

An overview of the [!UICONTROL Addressable Audience] feature and use cases.

##  [!UICONTROL Addressable Audience]? {#addressable-audience-description}

[!UICONTROL Addressable Audiences]では、[!DNL Audience Manager] がデータを収集している御社のすべてのシステムと選択された宛先との間のオーディエンスの重複を表示します。この概念を理解するには、次の図を参照してください。各円の重複は、各種のアドレス可能なオーディエンスを示します。

![](assets/addressableAudienceVenn.png)


| 指標 | 説明 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] の [!UICONTROL Destination] | A count of all devices that have interacted with all [!DNL Audience Manager] customers at the platform-level during the report look-back period and that could be matched with your chosen [!UICONTROL destination]. <br><br>この指標は次の情報が得られるため便利です。 <ul><li>特定のターゲット設定に到達 [!UICONTROL addressable audience] で [!DNL Audience Manager] きる合計のサイズ [!UICONTROL destination]。</li><li>ターゲットプラットフォームについての [!DNL Audience Manager] のプロファイルプールの規模、およびそのオーディエンスのサイズ。</li></ul> |
| [!UICONTROL Customer Total Audience] | A count of devices that have realized either a [!UICONTROL rule-based trait] on your properties or an [!UICONTROL onboarded trait] from your offline files during the look-back window. |
| [!UICONTROL Addressable Audience Match Rate] | A count of overlap of devices that have realized either a [!UICONTROL rule-based trait] or an [!UICONTROL onboarded trait] during the look-back window and devices that we have an ID sync with the chosen [!UICONTROL destination] regardless of the time of syncs.<br><br>この指標は次のようなデバイスを表しています。<ul><li>Have realized either a [!UICONTROL rule-based] or an [!UICONTROL onboarded trait] during the look-back window `AND`</li><li>Have an ID sync with the chosen [!UICONTROL destination] regardless of the time of syncs.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] は、割合で表されます。 |
| [!UICONTROL Total Segment Population] | A count of all the devices that were a member of your [!UICONTROL segment] during the report look-back period. |
| [!UICONTROL Segment Addressable Audience] | The number of users who have belonged to the [!UICONTROL segment] during the report look-back period and have an active ID sync on your site. [!UICONTROL Segments] は、 [!UICONTROL traits] Audience Marketplaceで取得した、独自のファーストパーティデータと、サードパーティデータおよびサードパーティデータを含むこ [とができます](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)。 <br><br>ヒント：1日間のルックバック期間と共に使用すると、この指標は、現在の状態を把握するのに役立ち [!UICONTROL segments]ます。 This is because the [!UICONTROL Segment Addressable Audience] metric represents the users who stayed in a [!UICONTROL segment] throughout the previous day. Combine this with the fact that [!DNL Audience Manager] refreshes [!UICONTROL Addressable Audiences] daily, combining this metric and lookback period provides the most up-to-date snapshot of your [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] は、割合で表されます。 |

## [!UICONTROL Addressable Audiences] インターフェイス {#addressable-audience-interface}

[!UICONTROL Addressable Audience]機能は、この抽象的な概念を定量化可能データに変換します。[!DNL Audience Manager] は、一目でわかる視覚化された情報と表形式の数値データによってオーディエンスの重複を表示します。

[!UICONTROL Addressable Audiences]は&#x200B;**[!UICONTROL Audience Data > Destinations]**&#x200B;にあります。「**[!UICONTROL Integrated Platforms > Device-Based]**」を選択して、アドレス可能なオーディエンス指標を表示します。

![](assets/addressable-audiences-landing.png)

The three metrics you can see on the [!UICONTROL Addressable Audiences] landing page represent:

| 指標 | 説明 |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | This metric represents the [!UICONTROL Customer Addressable Audience] (described in the table above) *for the last 30 days.* |
| **[!UICONTROL Match Rate]** | This metric represents the [!UICONTROL Addressable Audience Match Rate] (described in the table above) *for the last 30 days*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | A count of all devices that have interacted with all [!DNL Audience Manager] customers at the platform-level during the report look-back period and that could be matched with this [!UICONTROL destination]. 詳しくは、[プラットフォームレベルの指標](/help/using/features/addressable-audiences.md#platform-level-metrics)を参照してください。 |

Click on the name of a [!UICONTROL server-to-server destination] to view your addressable audience data. Note, this feature returns data for [!UICONTROL server-to-server destinations] only and access requires administrator permissions.

![](assets/addressableAudiences.png)

このデータは以下の目的に使用できます。

* **予測と計画：**[!UICONTROL Segment Addressable Audience]データは、オーディエンスのターゲティングおよびアクティベーションをおこなうために、宛先に送ろうとしているセグメントに関する、より詳細な情報を提供します。

* **パフォーマンスのレビュー：**[!UICONTROL Addressable Audiences]機能は、トラブルシューティングのツールでもあります。キャンペーンのパフォーマンスをレビューしてキャンペーンでリーチできた範囲を把握し、期待した結果が得られなかった場合は、ターゲティング／アクティベーションパートナーも含めて多角的に確認することができます。

### サードパーティデータの予測およびマッチ率に対する示唆

オーディエンスを獲得するためにサードパーティデータを購入する前に、他のデータプロバイダーとの重複を検証することができます。これにより、新しいデータを購入する前に、十分な情報に基づいた意思決定が可能になります。購入したサードパーティデータの ID 同期は、データの重複だけでなく、サードパーティプロバイダーと [!DNL Audience Manager] の他のあらゆるお客様との関連にも影響されます。[!DNL Adobe]の担当コンサルタントは、関連性のある他のデータソースを特定し、今後見込まれるキャンペーンを最適化するお手伝いをします。

### モバイルユーザーとマッチ率

There are gaps when trying to connect [!DNL Safari] or mobile app users where there are no third-party [!DNL cookies] present. That makes it difficult to sync users with some partners because only those [!DNL Adobe] IDs for synced third-party [!DNL cookies] are provided in the media delivery logs. This is a reason why you might see [low match rates](../features/addressable-audiences.md#low-match-rates) for your [!UICONTROL destinations].

## およびの日付範囲 [!UICONTROL Addressable Audiences] [!UICONTROL Destinations] {#date-ranges}

以下のセクションを読み、使用可能な日付範囲について、および [!UICONTROL Addressable Audience] または [!UICONTROL Destination] のレポートのそれぞれの間隔からのデータ経過時間を確認します。

## 利用可能な日付範囲およびタイムゾーン {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

[!UICONTROL Addressable Audiences]と[宛先](../features/destinations/destinations.md)のレポートでは、同じ日付範囲の間隔が使用されます。日付範囲には以下のオプションがあります。

* [!UICONTROL Last 1 Day]（直前の 24 時間の午前 0 時から午前 0 時までがこの期間となります。実際の時刻または現在の時刻に基づく指標ではありません）。
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

すべての日付および日付範囲は [!DNL UTC] タイムゾーンで設定されます。[Audience Manager のタイムゾーン](../reference/aam-time-zones.md)を参照してください。

## 日付範囲の期間内のデータ {#date-range-intervals}

[!UICONTROL Addressable Audience]および[!UICONTROL Destination]指標は、選択した時間間隔内に訪れた個別ユーザーの数を返します。例えば、1 人の訪問者は複数回サイトに訪れた場合でも、1 回のみカウントされます。初回の訪問が一意の訪問となり、これが記録されます。それ以降の訪問は再訪問となり、一意ではないためカウントされません。

選択した時間間隔内かそれより古いデータが日付範囲に含まれ、時間の経過に伴い、それぞれのレポート期間から外れていきます。例えば、[!UICONTROL Last 30 Days]オプションを選択した後、2 人の訪問者が訪れたとします。レポートでは、これらの訪問者は：

* これより長い期間（60 日、90 日、全期間）に対して返される結果に&#x200B;*含まれます*。
* [!UICONTROL Last 30 Day]より短い期間のオプション（現在、7 日、14 日）には&#x200B;*含まれません*。

また、31 日目には、これらの訪問者は 60 日、90 日、[!UICONTROL Lifetime]の結果にのみ含められます。これは、30 日の期間を超えたからです。訪問者は[!UICONTROL Lifetime]より古くなることはありません。

## [!UICONTROL Addressable Audiences] 指標 {#addressable-audience-metrics}

ここでは、[!UICONTROL Addressable Audiences] で提供される指標のタイプについて説明します。

### お客様レベルの指標 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

これらの指標は訪問者がサイトに訪れたとき、または [!DNL Audience Manager] にインバウンドデータファイルを送信したときに適合した特性のデータを返します。これらの指標は、お客様のアカウントに対応するオーディエンスサイズに関し、包括的な情報を提供します。

| 指標 | 説明 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | A count of overlap of devices that have realized either a [!UICONTROL rule-based trait] or an [!UICONTROL onboarded trait] during the look-back window and devices that we have an ID sync with the chosen destination regardless of the time of syncs.<br><br>この指標は次のようなデバイスを表しています。<ul><li>Have realized either a [!UICONTROL rule-based] or an [!UICONTROL onboarded trait] during the look-back window `AND`</li><li>Have an ID sync with the chosen [!UICONTROL destination] regardless of the time of syncs.</li></ul> |
| [!UICONTROL Customer Total Audience] | A count of devices that have realized either a [!UICONTROL rule-based trait] on your properties or an [!UICONTROL onboarded trait] from your offline files during the look-back window. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] は、割合で表されます。 |

### セグメントレベルのマッチ率の指標 {#segment-level-metrics}

These metrics return data on [!UICONTROL segment] membership. They help provide a more granular and accurate view of the audience size for each of your [!UICONTROL segments].

>[!NOTE]
>
>The way the look-back window is applied at the [!UICONTROL segment] level is different from that at the customer level. Visitors can come to the site and realize a [!UICONTROL trait] 10 days ago, and they could qualify for a [!UICONTROL segment] since then and dropped out of the [!UICONTROL segment] 2 days ago. When the 7 day look-back is applied, these visitors will be counted at the [!UICONTROL segment] level but not at the customer level.

| 指標 | 説明 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | The number of users who have belonged to the [!UICONTROL segment] during the report look-back period and have an active ID sync on your site. Segments can include your own first-party data and second party and third party data, via [!UICONTROL traits] acquired in the [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>ヒント：1日間のルックバック期間と共に使用すると、この指標は、現在の状態を把握するのに役立ち [!UICONTROL segments]ます。 This is because the [!UICONTROL Segment Addressable Audience] metric represents the users who stayed in a [!UICONTROL segment] throughout the previous day. Combine this with the fact that [!DNL Audience Manager] refreshes [!UICONTROL Addressable Audiences] daily, combining this metric and lookback period provides the most up-to-date snapshot of your [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | A count of all the devices that were a member of your [!UICONTROL segment] during the report look-back period. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] は、割合で表されます。 |

### プラットフォームレベルの指標 {#platform-level-metrics}

This metric returns data on activities collected across all [!DNL Audience Manager] customers. They can provide a broader view of the customer&#39;s audience compared with the aggregated [!DNL Audience Manager] customers.

| 指標 | 説明 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | A count of all devices that have interacted with all [!DNL Audience Manager] customers at the platform-level during the report look-back period and that could be matched with your chosen [!UICONTROL destination]. <br><br>この指標は次の情報が得られるため便利です。<ul><li>特定のターゲット設定先 [!UICONTROL total addressable audience] で到達 [!DNL Audience Manager] できるサイズ。</li><li>ターゲットプラットフォームについての [!DNL Audience Manager] のプロファイルプールの規模、およびそのオーディエンスのサイズ。</li></ul> |

## [!UICONTROL Customer] と [!UICONTROL Segment Addressable Audiences] の比較 {#comparing-metrics}

1 つの指標が大幅に他と異なる場合、[!UICONTROL Customer Addressable Audience] と [!UICONTROL Segment Addressable Audience] の指標を比較しないでください。これらは個々に異なる独立した指標です。上記の説明のとおり、これらはそれぞれ異なるデータセットから引き出されるものです。そのため、一方の指標がもう一方の指標より大きくても、何も結論付けるべきではありません。これらの比較を通して言えるのは以下のことのみとなります。

* [!UICONTROL Customer Addressable Audiences] は、自社のファーストパーティデータ [!UICONTROL trait] の実現に基づいています **。 この指標からは、データパートナーとの統合に関して幅広い包括的な情報が得られます。

* [!UICONTROL Segment Addressable Audiences]は、*自社のファーストパーティデータとセカンドパーティおよびサードパーティデータのセグメント認定*&#x200B;に基づきます。This metric provides a granular, more accurate view of your [!UICONTROL addressable audiences] in a targeting platform.

## Causes of Low Match Rates for [!UICONTROL Addressable Audiences] {#low-match-rates}

[!UICONTROL Addressable Audience]のマッチ率の低下またはレポートされる数値の不一致を引き起こす原因となる一般的な要素。

| 原因 | 説明 |
|---|---|
| モバイルトラフィック | Most [!UICONTROL server-to-server] integrations rely on synchronization processes facilitated by third-party [!DNL cookies]. However, mobile environments do not use third-party [!DNL cookies]. As a result, your [!UICONTROL Addressable Audiences] numbers may seem low compared to [!UICONTROL segment] size. <br><br>2018年1月時点で、モバイルオーディエンスは、 [!DNL Google] オーディエンス用に設定されたものと同じ方法でアクティブ化でき [!DNL Adobe Advertising Cloud][!UICONTROL cookie-based] ます。 While this means that you can send [!UICONTROL segments] with combined [!DNL cookie] and mobile ID membership to your [!DNL Google] and [!DNL Advertising Cloud] destinations, keep in mind that [!UICONTROL Addressable Audiences] only display the overlap between [!DNL cookie] IDs and destinations. [!DNL Audience Manager] は、100 %のモバイルオーディエンスをに送信し [!UICONTROL destinations]ますが、モバイルオーディエンスは [!UICONTROL Addressable Audience] 指標で測定されません。 <br><br>**注意**:例えば、1,000,000の母集団 [!UICONTROL segment] を持つを例にとります。 これを宛先 [!UICONTROL segment] または宛先にマップすると、700,000個のデバイス [!DNL Google] と70%のデバイスが表示さ [!DNL Adobe Advertising Cloud][!UICONTROL Addressable Audience][!UICONTROL Match Rate] れる場合があります。 The membership of 700,000 consists of [!DNL cookie] IDs which have an ID sync with the [!UICONTROL destination]. Your [!UICONTROL Addressable Audience] might, in fact, be much higher, because addressable mobile IDs do not appear in this metric. |
| [!DNL Safari] トラフィック | [!DNL Safari] サードパーティをブロック [!DNL cookies]します。 This prevents [!DNL Audience Manager] from synchronizing IDs with the [!UICONTROL destination]. [ITP 2.0の導入に伴い](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)、ユー [!UICONTROL addressable audiences][!DNL Safari] ザを含めないことを期待できます。 |
| 追跡されたメディアのインプレッション | 広告サーバーにおいて推奨される慣例により、ID 同期は広告タグ内でおこなわれません。大規模なオフサイト広告をおこなう場合、これらの環境ではユーザーとサードパーティの統合先は同期されません。Also, a large amount of collected media impression data could reduce [!UICONTROL addressable audience] numbers. |

## トラブルシューティング [!UICONTROL Addressable Audiences] {#troubleshooting}

[!UICONTROL Addressable Audiences]はマッチ率を割り出すだけでなく、トラブルシューティングのツールとしても使用できます。

For example, let&#39;s say you send a segment to a [!UICONTROL destination] and that [!UICONTROL destination] shows low reporting numbers. [!UICONTROL Addressable Audience]の結果を確認することで、これが技術的な問題なのか、または単にマッチ率が低いだけなのかがわかります。A low match rate shows your [!UICONTROL destination] isn&#39;t all that great for your selected segments. However, a difference in the [!UICONTROL total addressable audience] numbers between [!DNL Audience Manager] and the [!UICONTROL destination] indicates an integration, synchronization, or other technical problem. その場合、担当のアカウントマネージャーにお問い合わせください。
