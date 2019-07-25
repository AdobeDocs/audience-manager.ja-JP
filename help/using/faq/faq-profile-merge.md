---
description: プロファイル結合ルールおよびデバイスグラフに関するよくある質問への回答。
keywords: 組織 ID
seo-description: プロファイル結合ルールおよびデバイスグラフに関するよくある質問への回答。
seo-title: プロファイル結合ルールおよびデバイスグラフに関するよくある質問
solution: Audience Manager
title: プロファイル結合ルールおよびデバイスグラフに関するよくある質問
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# プロファイル結合ルールおよびデバイスグラフに関するよくある質問{#profile-merge-rules-and-device-graph-faq}

プロファイル結合ルールおよびデバイスグラフに関するよくある質問への回答。

<!-- 

profile-merge-faq.xml

 -->

## デバイスグラフの基礎知識 {#device-graph-basics}

**デバイスグラフとは何ですか？**

デバイスグラフは、匿名デバイスのグループを定義する、ID マッピングのセットです。これにより、各デバイスから収集されたシグナルの共通要素に基づいて、デバイスが個人または世帯に関連付けられます。これらのシグナルにより、デバイスが個人レベルまたは世帯レベルで識別されます。

<br> 

**外部デバイスグラフとは何ですか？**

外部デバイスグラフは、[!DNL Audience Manager] のデバイスグラフのうち、クロスデバイスデータソースのみから作成されたものでないものを指します。例えば、[プロファイル結合ルール](../features/profile-merge-rules/merge-rules-start.md)を作成し、[!UICONTROL Co-op Device Graph] またはサードパーティのデバイスグラフオプションを選択した場合、外部デバイスグラフを使用していることになります。[デバイスオプション](../features/profile-merge-rules/merge-rule-definitions.md#device-options)を参照してください。

<br> 

**外部デバイスグラフを使用する場合の一般的な使用例は何[!UICONTROL Profile Merge Rule]ですか。**

The main objective of using a device graph in a [!UICONTROL Profile Merge Rule] is to evaluate and qualify multiple devices belonging to a single person or household for a specific segment. セグメント自体にも様々な用途があります。例えば、DSP が提供する広告により見込み客のオーディエンスをターゲット化したり、サイト上のパーソナライゼーションプラットフォームから顧客のオンサイトエクスペリエンスをパーソナライズ化することが挙げられます。詳しくは、[外部デバイスグラフのユースケース](../features/profile-merge-rules/external-graph-use-cases.md)を参照してください。

<br> 

**Audience Manager は世界中どこででも外部デバイスグラフをサポートしていますか？**

いいえ。外部デバイスグラフは米国とカナダでのみ使用可能です。

<br> 

**[!DNL Audience Manager]はどのくらいの頻度で外部デバイスグラフのデータを更新しますか？**

週に 1 回です。

<br> 

## デバイスグラフとプロファイル結合ルール {#device-graph-profile-merge-rules}

**[!DNL Audience Manager]はデバイスグラフをどのように使用しますか？**

[!DNL Audience Manager] では、デバイスグラフは[プロファイル結合ルールの作成](../features/profile-merge-rules/merge-rules-start.md)時に設定オプションとして表示されます。Through your [!UICONTROL Profile Merge Rules], these device graphs help [!DNL Audience Manager]:

* 複数のデバイスプロファイルを結合する。特性のスーパーセットが 1 つ作成されます。
* この特性のスーパーセットをセグメント認定のために評価する（デバイスプロファイルの個別の評価はしません）。
* 認定されたデバイスを、使用可能なセグメントに追加する。

<br> 

**作成[!UICONTROL Profile Merge Rules]できますか?**

Currently, you can create a maximum of 3 [!UICONTROL Profile Merge Rules].

<br> 

**デバイスグラフの使用時に[!DNL Audience Manager]結合および読み取りを行うデバイスプロファイルはいくつ[!UICONTROL Profile Merge Rule]ありますか。**

When qualifying a device for a segment using a [!UICONTROL Profile Merge Rule], Audience Manager merges and reads the current device profile and a maximum of 3 additional device profiles linked by your selected device graph option.

<br> 

**デバイスグラフを使用しているときにセグメントに合致するデバイスはどれ[!UICONTROL Profile Merge Rule]か。**

[!DNL Audience Manager] が結合して読み取るデバイスは、セグメント認定されるデバイスと同じです。

>[!NOTE]
>
>外部デバイスグラフについて、[!DNL Audience Manager] はデバイス間のマッピングをプラットフォームレベルで保存し、3 つのデバイスを選択します。このとき、[!DNL Audience Manager] のインスタンスにあるデバイスとの関係は評価されません。

<br> 

**デバイスグラフを含むセグメントを使用すると、どのデバイス&#x200B;**[!UICONTROL Profile Merge Rule]がセグメントに適合できるか。**

デバイスがセグメント認定されるには、当該セグメントの作成後に[エッジデータサーバー](../reference/system-components/components-edge.md)上にある Audience Manager がそのデバイスを認識する必要があります。さらに、エッジサーバーは次の処理をおこないます。

* プロファイルデータを最大 14 日間保存する。
* 14 日間を超えて非アクティブなデバイスプロファイルを削除する。注意：この処理ではエッジからのデータのみが削除されます。他のシステムでは、さらに長い期間レコードが保存されます。詳しくは、[プライバシーとデータ保持についてよくある質問](../faq/faq-privacy.md)も参照してください。
* [!DNL Audience Manager] がプラットフォーム全体で当該のプロファイルのアクティビティを記録した場合、この 14 日間の間隔をリセットする。

[データ収集コンポーネント](../reference/system-components/components-data-collection.md)も参照してください。

<br> 

**デバイスグラフを使用しているのによって選定されたセグメント[!DNL Audience Manager][!UICONTROL Profile Merge Rule]はどこで送信できますか。**

[!DNL Audience Manager] はセグメントをバッチファイルまたはリアルタイムで宛先に送信できます。上記の FAQ の項目でも述べたように、デバイスがセグメント認定されるには、当該セグメントの作成後に[エッジデータサーバー](../reference/system-components/components-edge.md)上にある [!DNL Audience Manager] でそのデバイスが認識される必要があります。

<br> 

## セグメント、デバイスグラフ、プロファイル結合ルール {#segments-device-graphs-rules}

**デバイスグラフを使用するセグメントの資格がない場合、デバイスの[!DNL Audience Manager]セグメントを解除[!UICONTROL Profile Merge Rule]する方法を教えてください。**

Audience Manager merges up to four devices when evaluating segments with a [!UICONTROL Profile Merge Rule] that uses a device graph. セグメント化解除シグナルが発行された場合、現在のデバイスとリアルタイムに認識された 3 つの追加デバイスが宛先のセグメントから削除されます。例えば、6 つのデバイスから成るクラスターでは、最大 4 つのデバイスが結合され、評価されて、セグメントの対象として認定されます。同様に、最大 4 つのデバイスが結合され、評価されて、セグメント化解除されます。

<br> 

**宛先がデバイスのセグメントを解除できる場合、デバイスグラフを使用してデバイスをセグメント[!UICONTROL Profile Merge Rules]から削除できますか。**

はい。上記の説明を参照してください。

<br> 

**デバイスグラフを使用している[!UICONTROL Profile Merge Rule]セグメントを作成し、セグメントがリアルタイムとオンボーブの両方のデータを使用している場合、セグメントの更新データの変更時にセグメントが更新されますか。**

いいえ。Currently, [!DNL Audience Manager] evaluates segments with a [!UICONTROL Profile Merge Rule] that uses a device graph in real-time only. セグメントが評価された後にオンボードの特性に対しておこなわれた更新は、デバイスが次に[エッジデータサーバー](../reference/system-components/components-edge.md)で認識されるときにセグメント認定に使用されます。この場合、デバイスプロファイルがエッジサーバーでまだアクティブであり、オンボードのデータがそのシステムで使用可能になっていることが前提となります。詳しくは、[プライバシーとデータ保持についてよくある質問](../faq/faq-privacy.md)も参照してください。

<br> 

**セグメントサイズの予測には、デバイスグラフオプションを使用する接続に基づく、セグメントに基づく[!UICONTROL Profile Merge Rule]セグメントの予測が含まれますか。**

いいえ。See the definitions for the [!UICONTROL Estimated Real-Time Population] and [!UICONTROL Estimated Total Population] in [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

**デバイスグラフオプションを使用している接続に基づいてセグメントに合致するデバイス[!UICONTROL Addressable Audiences][!UICONTROL Profile Merge Rule]を含めますか。**

はい。

<br> 

**セグメントで使用する[!UICONTROL Profile Merge Rule]と[!UICONTROL No Authenticated Profile]、セグメントのデバイスを修飾する特性が認証されたプロファイルにのみ保存されている場合、セグメントの合計訪問者数は0になります。**

いいえ。現在、Audience Manager は認証済みプロファイルにマッピングされているデバイスをセグメント認定で計上します。

<br> 

## 特性頻度、デバイスグラフ、プロファイル結合ルール {#trait-freq-device-rules}

**デバイスグラフを使用する特性の頻度[!DNL Audience Manager]の計算[!UICONTROL Profile Merge Rule]方法を教えてください。**

特性頻度とは、複数のデバイス間における特定の特性の認定の数を合計したものです。わかりやすいようにユースケースを紹介します。

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ユースケース </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>条件</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">デバイスグラフにより、Device A と Device B がリンクされています。 </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">デバイスグラフオプションを使用する<span class="wintitle">プロファイル結合ルール</span>があります。 </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">1 つの特性（Trait 1）で構成される 1 つのセグメント（Segment 1）があり、Trait 1 の頻度は 8 です。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>アクション</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Audience Manager</span> は Device A と Device B のデバイスプロファイルを読み取り、結合します。この結果、次のようになります。 </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Device A が Trait 1 について 3 回認定されている。Trait 1 の頻度は 3 である。 </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Device B が Trait 1 について 5 回認定されている。Trait 1 の頻度は 5 である。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Audience Manager</span> は特性 1 の頻度を合計した値の 8（3 + 5 = 8）を使用して、セグメント認定を決定します。頻度が 8 であることから、Device A と Device B は Segment 1 に認定されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

## レポート、デバイスグラフ、プロファイル結合ルール {#reports-device-graphs-rules}

**デバイスグラフを使用するデバイスの数[!UICONTROL Profile Merge Rule]が表示されますか。**

はい。Reports return data at the [!UICONTROL Profile Merge Rule] level. レポートのデータは毎日更新されます。データはデバイスグラフでリンクされているデバイスではなく、アカウントで認識されるデバイスに基づいています。詳しくは、[プロファイル結合ルールのレポート指標](../features/profile-merge-rules/profile-link-metrics.md)を参照してください。

<br> 

**デバイスグラフを使用して、特定のセグメントのデバイス数を&#x200B;*リアルタイム*[!UICONTROL Profile Merge Rules]で確認できますか。**

はい。リアルタイム母集団指標により、現在のデバイス（リアルタイムで認識されているデバイス）のセグメント認定が、デバイスグラフでリンクされているすべてのデバイスからのプロファイルを使用してキャプチャされます。

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ユースケースの要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>条件</b> </p> </td> 
   <td colname="col2"> <p>以下のものがあるとします。 </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segment 1。次の特性と認定ロジックにより作成されています。Segment 1 = Trait A and Trait B and Trait C </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">Device 1（現在のデバイス）、Device 2（デバイスグラフ）、Device 3（デバイスグラフ）の 3 つのデバイスプロファイル。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>アクション</b> </p> </td> 
   <td colname="col2"> <p>使用可能な特性がそれぞれデバイスに関連付けられています。 </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Device 1：Trait A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Device 2：Trait B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Device 3：Trait C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>上記の要素により、Segment 1 の合計母集団は 1 となります。 </p> <p>この場合、<span class="wintitle">プロファイル結合ルール</span>はすべてのデバイスとその特性を使用して、セグメント認定を決定します。つまり、Device 1、2、3 が Segment 1 で認定されますが、上記のとおり、リアルタイムのセグメント母集団には Device 1 しか含まれません。理由は以下のとおりです。 </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 は現在のデバイスで、Audience Manager <span class="wintitle">データ収集サーバー</span>（<span class="wintitle">DCS</span>）をリアルタイムで操作している。 </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Device 2 および 3 はデバイスグラフによって Device 1 に関連付けられているが、Device 1 と同時に DCS を操作していない。 </li> 
     </ul> </p> <p>この結果、Device 2 および 3 はリアルタイムのセグメント母集団指標には含まれません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**デバイスグラフを使用している特定のセグメントのデバイスの合計[!UICONTROL Profile Merge Rule]数を確認できますか。**

はい。合計セグメント母集団指標には、デバイスグラフからの結合に基づきセグメント認定されている追加デバイスも含まれます。

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ユースケースの要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>条件</b> </p> </td> 
   <td colname="col2"> <p>以下のものがあるとします。 </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segment 1。次の特性と認定ロジックにより作成されています。Segment 1 = Trait A and Trait B and Trait C </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">Device 1（現在のデバイス）、Device 2（デバイスグラフ）、Device 3（デバイスグラフ）の 3 つのデバイスプロファイル。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>関連付け</b> </p> </td> 
   <td colname="col2"> <p>使用可能な特性がそれぞれデバイスに関連付けられています。 </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Device 1：Trait A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Device 2：Trait B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Device 3：Trait C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>上記の要素により、Segment 1 の合計母集団は 3 となります。 </p> <p>この場合、<span class="wintitle">プロファイル結合ルール</span>はすべてのデバイスとその特性を使用して、セグメント認定を決定します。つまり、Device 1、2、3 が Segment 1 で認定され、3 つすべてが合計母集団に含まれます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**[!UICONTROL Profile Merge Rule][!UICONTROL Interactive]レポート、[!UICONTROL Overlap]レポート、[!UICONTROL Audience Optimization]レポートに含まれるデバイスグラフを使用しているセグメントに合致するデバイスは、次のようになります。**

×

>[!MORE_LIKE_THIS]
>
>* [Profile Link](../features/profile-merge-rules/merge-rules-overview.md)

