---
description: アドレス可能なオーディエンスの機能およびユースケースの概要です。
keywords: DIL
seo-description: アドレス可能なオーディエンスの機能およびユースケースの概要です。
seo-title: アドレス可能なオーディエンス
solution: Audience Manager
title: アドレス可能なオーディエンス
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Addressable Audience {#addressable-audiences}

アドレス可能なオーディエンスの機能およびユースケースの概要です。

## アドレス可能なオーディエンスとは何か{#addressable-audience-description}

[!UICONTROL Addressable Audiences] この機能により、データ収集の対象 [!DNL Audience Manager] となるすべてのプロパティにわたって、オーディエンス間の重複が表示されます。この概念を理解するには、次の図を参照してください。各円の重複は、各種のアドレス可能なオーディエンスを示します。

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>Audience Managerの宛先のアドレス可能オーディエンス</b> </p> </td> 
   <td colname="col2"> <p>プラットフォームレベルにおいて、レポートのルックバック期間に Audience Manager のお客様とのやり取りがあり、選択した送信先と一致するデバイスの総数。 </p> <p>この指標は次の情報が得られるため便利です。 </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> 特定のターゲット送信先に関して <span class="keyword">Audience Manager</span> が到達できるアドレス可能なオーディエンス全体のサイズ。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">ターゲットプラットフォームについての <span class="keyword">Audience Manager</span> のプロファイルプールの規模、およびそのオーディエンスのサイズ。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>お客様のオーディエンスの総数</b> </p> </td> 
   <td colname="col2"> <p>ルックバック期間に、御社のシステムにおけるルールベースの特性、またはオフラインファイルからのオンボードの特性に適合したデバイスの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>アドレス可能オーディエンス一致率</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>ルックバック期間にルールベースの特性またはオンボードの特性に適合したデバイスと、同期のタイミングを問わず、選択された送信先との ID 同期がおこなわれたデバイスの間の重複数。 </p> 
    </draft-comment> <p>この指標は次のようなデバイスを表しています。 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">ルックバック期間にルールベースの特性またはオンボードの特性に適合し、<b>かつ</b>、 </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">同期の時間に関係なく、選択した送信先と ID が同期している。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>お客様の一致率</b> </p> </td> 
   <td colname="col2"> <p>「お客様のアドレス可能なオーディエンス ÷ お客様のオーディエンスの総数」を % で表現したもの。 </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>セグメント母集団の総数</b> </p> </td> 
   <td colname="col2"> <p>レポートのルックバック期間内にセグメントに属していたすべてのデバイスの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>セグメントのアドレス可能なオーディエンス</b> </p> </td> 
   <td colname="col2"> <p>レポートのルックバック期間中にセグメントに属しており、サイト上で ID 同期がアクティブとなっているユーザーの数。セグメントには、自社のファーストパーティデータと、セカンドパーティおよびサードパーティデータを含むことができます（<a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>ヒント：ルックバック期間を 1 日にした場合、この指標はセグメントの現在の状態を把握するのに役立ちます。それは、<span class="wintitle">セグメントのアドレス可能なオーディエンス</span>の指標が、前日の 1 日を通してセグメントに適合したユーザー数を示すからです。このことと、<span class="keyword">Audience Manager</span> では <span class="wintitle">アドレス可能なオーディエンス</span>が毎日更新されることを踏まえて、この指標とルックバック期間を組み合わせれば、セグメントに関する最新のスナップショットを得ることができます。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>セグメントの一致率</b> </p> </td> 
   <td colname="col2"> <p>セグメントのアドレス可能なオーディエンス ÷ セグメント母集団の総数を % で表現したもの。 </p> </td> 
  </tr>  
 </tbody> 
</table>

## アドレス可能なオーディエンスのインターフェイス {#addressable-audience-interface}

[!UICONTROL Addressable Audience] この抽象概念は、この抽象概念を定量化データに変換します。[!DNL Audience Manager] は、一目でわかる視覚化された情報と表形式の数値データによってオーディエンスの重複を表示します。

[!UICONTROL Addressable Audiences]**[!UICONTROL Audience Data > Destinations]** が配置されていることを確認します。Select **[!UICONTROL Integrated Platforms > Device-Based]** to see addressable audiences metrics.

![](assets/addressable-audiences-landing.png)

アドレスアドレス可能なオーディエンスのランディングページで表示できる指標は次の3つです。

| 指標 | 説明 |
---------|----------|
| **アドレス可能なオーディエンス（デバイス）** | This metric represents the Customer Addressable Audience (described in the table above) *for the last 30 days.* |
| **一致率** | This metric represents the Addressable Audience Match Rate (described in the table above) *for the last 30 days*. |
| **全期間アドレス可能オーディエンス（デバイス）** | レポートのルックバック期間中に、すべてのAudience Manager顧客に対してアクションが実行されているすべてのデバイスの数、およびこの宛先と一致する可能性のあるすべてのデバイスの数です。See [Platform-Level Metrics](/help/using/features/addressable-audiences.md#platform-level-metrics) for more information. |

サーバー間通信ベースの送信先の名前をクリックし、アドレス可能なオーディエンスデータを表示します。この機能はサーバー間通信ベースの送信先のデータのみを返し、アクセスには管理者権限が必要となることにご注意ください。

![](assets/addressableAudiences.png)

このデータは以下の目的に使用できます。

* **予測と計画:**[!UICONTROL Segment Addressable Audience] データを使用すると、オーディエンスのターゲット設定およびアクティブ化のために、送信先に送信するセグメントの精度を高めることができます。

* **パフォーマンス評価:**[!UICONTROL Addressable Audiences] この機能はトラブルシューティングツールでもあります。キャンペーンのパフォーマンスをレビューしてキャンペーンでリーチできた範囲を把握し、期待した結果が得られなかった場合は、ターゲティング／アクティベーションパートナーも含めて多角的に確認することができます。

### サードパーティデータの予測およびマッチ率に対する示唆

オーディエンスを獲得するためにサードパーティデータを購入する前に、他のデータプロバイダーとの重複を検証することができます。これにより、新しいデータを購入する前に、十分な情報に基づいた意思決定が可能になります。購入したサードパーティデータの ID 同期は、データの重複だけでなく、サードパーティプロバイダーと [!DNL Audience Manager] の他のあらゆるお客様との関連にも影響されます。[!DNL Adobe]の担当コンサルタントは、関連性のある他のデータソースを特定し、今後見込まれるキャンペーンを最適化するお手伝いをします。

### モバイルユーザーとマッチ率

There are gaps when trying to connect [!DNL Safari] or mobile app users where there are no third-party cookies present. メディアの配信ログでは同期されたサードパーティ Cookie の[!DNL Adobe] ID のみが提供されるので、パートナーによってはユーザーとの同期が困難になります。この結果、宛先の[マッチ率が低下](../features/addressable-audiences.md#low-match-rates)する可能性があります。

## アドレス可能なオーディエンスおよび宛先での日付範囲 {#date-ranges}

Read the sections below for available date ranges and how data ages out of each interval in the reports for an [!UICONTROL Addressable Audience] or [!UICONTROL Destination].

## 利用可能な日付範囲およびタイムゾーン {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Reports for your [!UICONTROL Addressable Audiences] and [Destinations](../features/destinations/destinations.md) use the same date range intervals. 日付範囲には以下のオプションがあります。

* [!UICONTROL Last 1 Day] （この間隔は、24時間前の午前0時から午前0時までに実行されます。これは、リアルタイム指標やリアルタイム指標ではありません）。
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

All dates and date ranges are set in the [!DNL UTC] time zone. See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## 日付範囲の期間内のデータ {#date-range-intervals}

[!UICONTROL Addressable Audience] および [!UICONTROL Destination] 指標は、選択した時間間隔の個別ユーザーの数を返します。例えば、1 人の訪問者は複数回サイトに訪れた場合でも、1 回のみカウントされます。初回の訪問が一意の訪問となり、これが記録されます。それ以降の訪問は再訪問となり、一意ではないためカウントされません。

選択した時間間隔内かそれより古いデータが日付範囲に含まれ、時間の経過に伴い、それぞれのレポート期間から外れていきます。For example, let&#39;s assume you see 2 visitors after choosing the [!UICONTROL Last 30 Days] option. レポートで、これらの訪問者は：

* *より長い時間間隔（60日、90日間、全期間）によって返される結果に* 含まれます。
* *オプション* （ [!UICONTROL Last 30 Day] 「現在」、&quot;7日間」および&quot;14日間」）の前の短い間隔には含められません。

And, on day 31, these visitors only show up in the 60 day, 90 day, and [!UICONTROL Lifetime] results. 30日の間隔が古くなっています。Visitors do not age out of the [!UICONTROL Lifetime] interval.

## アドレス可能なオーディエンスの指標 {#addressable-audience-metrics}

This section describes the types of metrics provided by [!UICONTROL Addressable Audiences].

### お客様レベルの指標 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

これらの指標は訪問者がサイトに訪れたとき、または [!DNL Audience Manager] にインバウンドデータファイルを送信したときに適合した特性のデータを返します。これらの指標は、お客様のアカウントに対応するオーディエンスサイズに関し、包括的な情報を提供します。

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>お客様のアドレス可能なオーディエンス</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>ルックバック期間にルールベースの特性またはオンボードの特性に適合したデバイスと、同期のタイミングを問わず、選択された送信先との ID 同期がおこなわれたデバイスの間の重複数。 </p> 
    </draft-comment> <p>この指標は次のようなデバイスを表しています。 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">ルックバック期間にルールベースの特性またはオンボードの特性に適合し、<b>かつ</b>、 </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">同期の時間に関係なく、選択した送信先と ID が同期している。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>お客様のオーディエンスの総数</b> </p> </td> 
   <td colname="col2"> <p>ルックバック期間に、御社のシステムにおけるルールベースの特性、またはオフラインファイルからのオンボードの特性に適合したデバイスの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>お客様の一致率</b> </p> </td> 
   <td colname="col2"> <p>「お客様のアドレス可能なオーディエンス ÷ お客様のオーディエンスの総数」を % で表現したもの。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### セグメントレベルの一致率の指標 {#segment-level-metrics}

これらの指標はセグメントのメンバーシップについてのデータを返します。これらは各セグメントについて、オーディエンスサイズに関するより詳細で正確な情報を提供します。

>[!NOTE]
>
>セグメントレベルとお客様レベルでは、ルックバック期間の適用のされ方が異なります。10 日前に訪問者がサイトに訪れてある特性に適合した場合、その後適合状態を維持し、2 日前にセグメントの適合が解除されます。7日のルックバックが適用されると、これらの訪問者はセグメントレベルでカウントされますが、顧客レベルではカウントされません。

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>セグメントのアドレス可能なオーディエンス</b> </p> </td> 
   <td colname="col2"> <p>レポートのルックバック期間中にセグメントに属しており、サイト上で ID 同期がアクティブとなっているユーザーの数。セグメントには、自社のファーストパーティデータと、セカンドパーティおよびサードパーティデータを含むことができます（<a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>ヒント：ルックバック期間を 1 日にした場合、この指標はセグメントの現在の状態を把握するのに役立ちます。それは、<span class="wintitle">セグメントのアドレス可能なオーディエンス</span>の指標が、前日の 1 日を通してセグメントに適合したユーザー数を示すからです。このことと、<span class="keyword">Audience Manager</span> では <span class="wintitle">アドレス可能なオーディエンス</span>が毎日更新されることを踏まえて、この指標とルックバック期間を組み合わせれば、セグメントに関する最新のスナップショットを得ることができます。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>セグメント母集団の総数</b> </p> </td> 
   <td colname="col2"> <p>レポートのルックバック期間内にセグメントに属していたすべてのデバイスの数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>セグメントの一致率</b> </p> </td> 
   <td colname="col2"> <p>セグメントのアドレス可能なオーディエンス ÷ セグメント母集団の総数を % で表現したもの。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### プラットフォームレベルの指標 {#platform-level-metrics}

この指標は、Audience Manager のすべてのお客様から収集したアクティビティについてのデータを返します。Audience Manager のお客様全体と比較することで、オーディエンスに関するより広い視野が得られます。

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Manager のアドレス可能なオーディエンス</b> </p> </td> 
   <td colname="col2"> <p>プラットフォームレベルにおいて、レポートのルックバック期間に Audience Manager のお客様とのやり取りがあり、選択した送信先と一致するデバイスの総数。 </p> <p>この指標は次の情報が得られるため便利です。 </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> 特定のターゲット送信先に関して <span class="keyword">Audience Manager</span> が到達できるアドレス可能なオーディエンス全体のサイズ。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">ターゲットプラットフォームについての <span class="keyword">Audience Manager</span> のプロファイルプールの規模、およびそのオーディエンスのサイズ。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## お客様のアドレス可能なオーディエンスとセグメントのアドレス可能なオーディエンスの比較{#comparing-metrics}

[!UICONTROL Customer Addressable Audience] 他の指標と比較して、 [!UICONTROL Segment Addressable Audience] 指標と指標を比較しないでください。これらは個々に異なる独立した指標です。上記の説明のとおり、これらはそれぞれ異なるデータセットから引き出されるものです。そのため、一方の指標がもう一方の指標より大きくても、何も結論付けるべきではありません。これらの比較を通して言えるのは以下のことのみとなります。

* [!UICONTROL Customer Addressable Audiences] は、独自のファーストパーティデータ *の特性再導入に基づいてい*ます。この指標からは、データパートナーとの統合に関して幅広い包括的な情報が得られます。

* [!UICONTROL Segment Addressable Audiences] は、独自のファーストパーティデータ、 *および2つ目およびサードパーティのデータ*のセグメント資格に基づいています。この指標からは、ターゲットプラットフォームのアドレス可能なオーディエンスに関してより詳細で正確な情報が得られます。

## アドレス可能なオーディエンスのマッチ率の低下の原因 {#low-match-rates}

Common elements responsible for low [!UICONTROL Addressable Audience] match rates or discrepancies in reported numbers.

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 原因 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>モバイルトラフィック</b> </p> </td> 
   <td colname="col2"> <p>サーバー間統合の大半はサードパーティ Cookie によって促進される同期プロセスに依拠しています。しかし、モバイル環境においては、サードパーティ Cookie は使用されません。その結果、アドレス可能なオーディエンスの数はセグメントサイズに対して少なく見えます。 </p> <p>2018 年 1 月以降、Cookie ベースのオーディエンス用に設定された Google および Adobe Advertising Cloud の同じ送信先において、モバイルオーディエンスをアクティブ化することができるようになりました。これにより、Cookie とモバイル ID のメンバーシップを組み合わせたセグメントを Google および Advertising Cloud の送信先に送信できますが、アドレス可能なオーディエンスにおいては Cookie ID と送信先の間の重複のみが表示されることに注意してください。Audience Manager はすべてのモバイルオーディエンスを送信先に送信しますが、モバイルオーディエンスはアドレス可能なオーディエンスの指標によって測定されません。 </p> <p> <p><b>注意</b>:例えば、1,000,000の母集団を持つセグメントを作成します。このセグメントを Google または Adobe Advertising Cloud の送信先にマッピングした結果、アドレス可能なオーディエンスは 700,000 デバイス、マッチ率は 70% となったとします。700,000 を構成するメンバーシップは、送信先との ID 同期がおこなわれた Cookie ID となります。アドレス可能なモバイル ID はこの指標では表示されないので、実際のアドレス可能なオーディエンスはこれよりも大きい可能性があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari トラフィック</b> </p> </td> 
   <td colname="col2"> <p>Safari ではサードパーティ Cookie はブロックされます。そのため、Audience Manager は送信先との ID 同期をおこなうことができません。<a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external">ITP 2.0</a> の導入によって、アドレス可能なオーディエンスに Safari ユーザーが含まれなくなります。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>追跡されたメディアのインプレッション</b> </p> </td> 
   <td colname="col2"> <p>広告サーバーにおいて推奨される慣例により、ID 同期は広告タグ内でおこなわれません。大規模なオフサイト広告をおこなう場合、これらの環境ではユーザーとサードパーティの統合先は同期されません。また、収集された大量のメディアインプレッションデータによって、アドレス可能なオーディエンスの数が少なくなることがあります。 </p> </td>
  </tr> 
 </tbody> 
</table>

## アドレス可能なオーディエンスを使用したトラブルシューティング {#troubleshooting}

In addition to surfacing match rates, you can also use [!UICONTROL Addressable Audiences] as a troubleshooting tool.

<!-- addressable-audiences-troubleshooting.xml -->

例えば、送信先にセグメントを送ったところ、その送信先についてレポートされた数値が低かったとします。[!UICONTROL Addressable Audience] 結果をチェックすると、これが技術的な問題か、低一致率のケースのみが表示されます。低いマッチ率は、選択したセグメントに対して送信先が適切でないことを示します。しかし、Audience Manager と送信先の間でアドレス可能なオーディエンスの合計数の違いがある場合、それは統合や同期などの技術的問題があることを示しています。その場合、担当のアカウントマネージャーにお問い合わせください。