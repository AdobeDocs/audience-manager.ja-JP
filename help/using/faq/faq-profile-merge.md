---
description: プロファイル結合ルールおよびデバイスグラフに関するよくある質問への回答。
keywords: Organization ID
seo-description: プロファイル結合ルールおよびデバイスグラフに関するよくある質問への回答。
seo-title: プロファイル結合ルールおよびデバイスグラフに関するよくある質問
solution: Audience Manager
title: プロファイル結合ルールおよびデバイスグラフに関するよくある質問
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 100%

---


# プロファイル結合ルールおよびデバイスグラフに関するよくある質問 {#profile-merge-rules-and-device-graph-faq}

プロファイル結合ルールおよびデバイスグラフに関するよくある質問への回答。

<!-- profile-merge-faq.xml -->

## デバイスグラフの基礎知識 {#device-graph-basics}

**デバイスグラフとは何ですか？**

デバイスグラフは、匿名デバイスのグループを定義する、ID マッピングのセットです。これにより、各デバイスから収集されたシグナルの共通要素に基づいて、デバイスが個人または世帯に関連付けられます。これらのシグナルにより、デバイスが個人レベルまたは世帯レベルで識別されます。

 

**外部デバイスグラフとは何ですか？**

外部デバイスグラフは、[!DNL Audience Manager] のデバイスグラフのうち、クロスデバイスデータソースのみから作成されたものでないものを指します。例えば、[プロファイル結合ルール](../features/profile-merge-rules/merge-rules-start.md)を作成し、[!UICONTROL Co-op Device Graph] またはサードパーティのデバイスグラフオプションを選択した場合、外部デバイスグラフを使用していることになります。[デバイスオプション](../features/profile-merge-rules/merge-rule-definitions.md#device-options)を参照してください。

 

**外部デバイスグラフを [!UICONTROL Profile Merge Rule] で使用する一般的な例にはどのようなものがありますか？**

[!UICONTROL Profile Merge Rule]でデバイスグラフを使用する主な目的は、特定のセグメントについて、1 件の個人または世帯に属する複数のデバイスを評価および認定することです。セグメント自体にも様々な用途があります。例えば、DSP が提供する広告により見込み客のオーディエンスをターゲット化したり、サイト上のパーソナライゼーションプラットフォームから顧客のオンサイトエクスペリエンスをパーソナライズ化することが挙げられます。[外部デバイスグラフのユースケース](../features/profile-merge-rules/external-graph-use-cases.md)を参照してください。

 

**Audience Manager は世界中どこででも外部デバイスグラフをサポートしていますか？**

いいえ。外部デバイスグラフは米国とカナダでのみ使用可能です。

 

**[!DNL Audience Manager] はどのくらいの頻度で外部デバイスグラフのデータを更新しますか？**

週に 1 回です。

 

## デバイスグラフとプロファイル結合ルール {#device-graph-profile-merge-rules}

**[!DNL Audience Manager] はデバイスグラフをどのように使用しますか？**

[!DNL Audience Manager] では、デバイスグラフは[プロファイル結合ルールの作成](../features/profile-merge-rules/merge-rules-start.md)時に設定オプションとして表示されます。[!UICONTROL Profile Merge Rules]を通じて、これらのデバイスグラフは次の点で [!DNL Audience Manager] に便利です。

* 複数のデバイスプロファイルを結合する。特性のスーパーセットが 1 つ作成されます。
* この特性のスーパーセットをセグメント認定のために評価する（デバイスプロファイルの個別の評価はしません）。
* 認定されたデバイスを、使用可能なセグメントに追加する。

 

**[!UICONTROL Profile Merge Rules] はいくつ作成することができますか？**

現在、[!UICONTROL Profile Merge Rules] は最大 4 つまで作成できます。4 つ目のプロファイル結合ルール（[!UICONTROL All Cross-Device Profiles]）は、[!UICONTROL People-Based Destinations] アドオンを購入したユーザーのみが使用できます。

 

**デバイスグラフを [!UICONTROL Profile Merge Rule] で使用する場合、[!DNL Audience Manager] は何件のデバイスプロファイルを結合して読み取りますか？**

[!UICONTROL Profile Merge Rule] を使用してデバイスのセグメント認定をおこなう場合、Audience Manager は現在のデバイスプロファイルと、選択したデバイスグラフオプションでリンクされたその他最大 99 件のデバイスプロファイルを結合して読み取ります。

 

**[!UICONTROL Profile Merge Rule] で使用する場合、どのデバイスがセグメント認定されますか？**

[!DNL Audience Manager] が結合して読み取るデバイスは、セグメント認定されるデバイスと同じです。

 

**デバイスグラフを使用する [!UICONTROL Profile Merge Rule] により認定されたセグメントを、[!DNL Audience Manager] はどこに送信できますか？**

[!DNL Audience Manager] はセグメントをバッチファイルまたはリアルタイムで宛先に送信できます。

 

## セグメント、デバイスグラフ、プロファイル結合ルール {#segments-device-graphs-rules}

**デバイスグラフを使用する [!UICONTROL Profile Merge Rule] でデバイスがセグメント認定されない場合、[!DNL Audience Manager] はどのようにしてデバイスのセグメント化を解除しますか？**

Audience Manager は、デバイスグラフを使用する [!UICONTROL Profile Merge Rule] でセグメントを評価する場合、最大 100 台のデバイスを結合します。セグメント化解除シグナルが発行された場合、現在のデバイスとリアルタイムに認識された最大 99 台の追加デバイスが宛先のセグメントから削除されます。セグメント化の解除について詳しくは、[プロファイルの結合ルールとデバイスのセグメント化解除プロセス](../features/profile-merge-rules/merge-rule-unsegment.md)を参照してください。

 

**宛先でデバイスのセグメント化解除が可能な場合、デバイスグラフを使用する [!UICONTROL Profile Merge Rules] によりデバイスがセグメントから削除されますか？**

はい。上記の説明を参照してください。

 

**デバイスグラフを使用する [!UICONTROL Profile Merge Rule] でセグメントを作成し、そのセグメントがリアルタイムのデータとオンボードのデータの両方を使用している場合、オンボードのデータが変更するとそのセグメントは更新されますか？**

はい。

 

**セグメントサイズの予測には、デバイスグラフオプションを使用する [!UICONTROL Profile Merge Rule] で設定される結合に基づいてセグメント認定されるデバイスは含まれますか？**

いいえ。[セグメントビルダーの特性およびセグメント母集団データ](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/features/segments/segment-builder-data.html)で、[!UICONTROL Estimated Real-Time Population] および [!UICONTROL Estimated Total Population] の定義を参照してください。

 

**[!UICONTROL Addressable Audiences] には、デバイスグラフオプションを使用する [!UICONTROL Profile Merge Rule] で設定される結合に基づいてセグメント認定されるデバイスは含まれますか？**

はい。

 

**セグメントで [!UICONTROL No Cross-Device Profile] が設定されている [!UICONTROL Profile Merge Rule] を使用していて、デバイスをセグメント認定する特性が認証済みプロファイルのみについて保存される場合、セグメントの合計母集団は 0 になりますか？**

はい。プロファイル結合ルールが [!UICONTROL No Cross-Device Profile] に設定されている場合、Audience Manager は、セグメント評価で黒相デバイス対応プロファイルに保存された特性をカウントしませ ん。

 

## 特性頻度、デバイスグラフ、プロファイル結合ルール {#trait-freq-device-rules}

**[!DNL Audience Manager] はデバイスグラフを使用する [!UICONTROL Profile Merge Rule] で、特性頻度をどのように計算しますか？**

特性頻度とは、複数のデバイス間における特定の特性に対する認定の数を合計したものです。わかりやすいようにユースケースを紹介します。

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

 

## レポート、デバイスグラフ、プロファイル結合ルール {#reports-device-graphs-rules}

**デバイスグラフを使用する [!UICONTROL Profile Merge Rule] で到達できるデバイスの数は確認できますか？**

はい。レポートは [!UICONTROL Profile Merge Rule] レベルでデータを返します。レポートのデータは毎日更新されます。データはデバイスグラフでリンクされているデバイスではなく、アカウントで認識されるデバイスに基づいています。詳しくは、[プロファイル結合ルールのレポート指標](../features/profile-merge-rules/profile-link-metrics.md)を参照してください。

 

**デバイスグラフを使用する [!UICONTROL Profile Merge Rules] では、特定のセグメントから&#x200B;*リアルタイム*で認定されているデバイスの数を確認することはできますか？**

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

 

**デバイスグラフを使用する [!UICONTROL Profile Merge Rule] による特定のセグメントで認定されているデバイスの総数は確認できますか？**

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

 

**デバイスグラフを使用する [!UICONTROL Profile Merge Rule] を用いてセグメントに認定されているデバイスは、[!UICONTROL Interactive] レポート、[!UICONTROL Overlap] レポート、および [!UICONTROL Audience Optimization] レポートに含まれますか？**

いいえ。

**2020 年 3 月 17 日以降、Adobe Campaign へのセグメントエクスポートで、セグメント母集団がゼロと表示されるのはなぜですか。**

2019 年後半に、クロスデバイス ID を使用して生成されたバッチファイルの精度を向上させるために、一連のプロファイル結合ルールの機能強化がリリースされました。これらの機能強化は、2020 年 3 月 17 日（火）より、Audience Manager インスタンスで厳密に適用されます。そのため、クロスプロファイル ID を使用して宛先にマッピングされたセグメントは、一部のデバイス結合ルールの設定でエクスポートの生成を停止します。

クロスデバイス ID（Adobe Campaign など）を使用して、Audience Manager インスタンスと宛先を正しく統合するには、次の要件を満たす必要があります。

1. Adobe Campaign の宣言済み ID の宛先にマッピングされたセグメントで使用されるプロファイルの結合ルールを確認します。認証済みのすべてのプロファイルをエクスポートに含めることができるように、プロファイルのマージルールでは [!UICONTROL Last Authenticated Profile] オプションを使用する必要があります。プロファイル結合ルールで別のオプションを使用している場合は、[!UICONTROL Last Authenticated Profile] に切り替えます。
2. プロファイル結合ルール設定で、Adobe Campaign の宣言済み ID データソースを選択します。

>[!NOTE]
>
> この状況に直面するお客様のプロファイル結合ルールの制限を 1 つ増やしまた。これにより、Adobe Campaign の宣言済み ID の宛先にマッピングされたセグメントに対して、他の用途のプロファイル結合ルールを変更しなくても、専用のプロファイル結合ルールを作成できます。

>[!MORELIKETHIS]
>
>* [プロファイルリンク](../features/profile-merge-rules/profile-link-use-case.md)

