---
description: セグメントビルダーで特性を追加および削除して、実際の特性の母集団を、実際および推定のセグメント母集団データと共に確認します。推定母集団サイズのデータは、キャンペーンに適したセグメントを作成するのに役立ちます。
seo-description: セグメントビルダーで特性を追加および削除して、実際の特性の母集団を、実際および推定のセグメント母集団データと共に確認します。推定母集団サイズのデータは、キャンペーンに適したセグメントを作成するのに役立ちます。
seo-title: セグメントビルダーにおける特性とセグメントのユーザー数データ
solution: Audience Manager
title: セグメントビルダーにおける特性とセグメントのユーザー数データ
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 100%

---


# [!UICONTROL Segment Builder] の [!UICONTROL Trait][!UICONTROL Segment] {#trait-and-segment-population-data-in-segment-builder}

[!UICONTROL Segment Builder]の[!UICONTROL traits]で特性を追加または削除すると、実際のセグメント母集団データや推定セグメント母集団データと一緒に、実際の[!UICONTROL trait]母集団数が表示されます。推定母集団サイズのデータは、キャンペーンに適したセグメントを作成するのに役立ちます。

## [!UICONTROL Trait] 母集団データ {#trait-population-data}

[!UICONTROL Segment Builder]には、[!UICONTROL trait]をセグメントに追加した日の前日の[!UICONTROL Total Trait Population]が表示されます。このデータは、[!UICONTROL Basic View]セクションで選択した[!UICONTROL trait]の周囲の青色のフィールドに表示されます。

![](assets/trait-size.png)

次の表は、特性母集団の指標です。


| 指標 | 説明 |
---------|----------|
| [!UICONTROL Total Trait Population] | 選択した特性がプロファイルにある一意の ID の数。 |


## 実際のセグメント母集団と推定セグメント母集団の計算  {#calculating-real-estimated-populations}

新しいセグメントの作成時、または既存のセグメントの変更時は、Audience Manager で実際のリアルタイムセグメント母集団と合計セグメント母集団が表示されるまでに最大 24 時間かかります。

ただし、セグメントのリアルタイム母集団と合計母集団のサイズの予測は Audience Manager ですぐにおこなうことができます。この予測はサンプリングされた履歴データに基づいておこなわれ、95％の信頼区間で結果が返されます。

![](assets/confidence-interval.png)

[!UICONTROL Segment Builder]では、推定母集団グラフの青色の棒はセグメントのサイズの範囲の上限と下限を表します。過去のパフォーマンスから将来の結果が保証されているわけではありませんが、推定データを使用すると新しいセグメントや編集したセグメントのサイズがどの程度になる可能性があるか把握できます。

## セグメント母集団データの概要  {#segment-populations}

[!UICONTROL Segment Builder]では、セグメントの作成時や編集時にセグメント母集団データが表示されます。

* 推定されたセグメント母集団データ（リアルタイムと合計）について、[!UICONTROL Segment Builder]でセグメントの特性の追加や削除を実行してもグラフは自動的には更新されません。**[!UICONTROL Calculate Estimates]**&#x200B;をクリックすると、推定された母集団の数値が表示（または更新）されます。

* 実際のセグメント母集団データ（リアルタイムと合計）について、[!UICONTROL Segment Builder]で既存のセグメントを読み込むと、セグメントのグラフが自動的に更新されます。新しいセグメントを作成した場合、または既存のセグメントに新しい特性を追加した場合、実際の母集団データはセグメントの作成から 24 時間が経過するまで更新されません。

![](assets/segment-data.png)

以下の表で、推定されたセグメント母集団データと実際のセグメント母集団データの詳細を確認してください。

## 推定セグメント母集団データの定義  {#estimated-segment-population}

次の表は、推定母集団の指標です。

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Estimated Real-Time Population (Potential) </span> </p> </td> 
   <td colname="col2"> <p>指定した時間範囲にリアルタイムで認識され、また Audience Manager で認識された時点でセグメントについて認定されたユニーク訪問者の推定数。 </p> <p><span class="wintitle">セグメントビルダー</span>では、直近 30 日間の特性母集団（<span class="wintitle">Total Trait Populations</span>）は、特性と、リアルタイムに評価されたセグメントで異なります。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">特性の場合、直近 30 日間の指標では、その 30 日間で特性に認定されたユニークユーザーが計上されます。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">リアルタイムに評価されたセグメントの場合、直近 30 日間の指標では、過去のいずれかの時点で（当該セグメントの）特性について認定され、その 30 日間で Audience Manager により再度認識されたユーザーが計上されます。例えば、60 日前に特性について認定され、10 日前に再度認識されたユーザーがいるとします。このデータでは、このユーザーが特性について認定されてから 30 日間を超えているので、このユーザーは特性数に加算されません。ただし、リアルタイムに評価されたセグメントの過去 30 日間の数には含まれます。30 日間はセグメントの対象として認定されたからです。 </li>
     </ul> </p> <p> <p>注意：<span class="wintitle">Estimated Real-Time Population</span> 指標には、<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">デバイスグラフオプション</a>を使用する<span class="wintitle">プロファイル結合ルール</span>により実行された結合に基づきセグメントについて認定されたデバイスは含まれません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Estimated Total Population (Potential)</span> </p> </td> 
   <td colname="col2"> <p>新しいセグメント、または変更されたセグメントに含まれる可能性があるユニーク訪問者の推定数。他の大部分の予測と同様に、過去のパフォーマンスから将来の結果が保証されているわけではありませんが、推定合計数は次の用途で使用できます。 </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">セグメントの作成時に、新しいセグメントや変更後のセグメントがリーチできるユーザーの数を把握する。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">目標に応じてセグメントを調整する。例えば、大規模なセグメントはブランド認知キャンペーンに便利で、小規模なセグメントは対象を限定したターゲティングやリターゲティングキャンペーンに便利です。 </li> 
     </ul> </p> <p> <p>注意：<span class="wintitle">Estimated Total Population</span> 指標には、<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">デバイスグラフオプション</a>を使用する<span class="wintitle">プロファイル結合ルール</span>により実行された結合に基づきセグメントについて認定されたデバイスは含まれません。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 既存（実際）のセグメント母集団データの定義 {#existing-segment-population}

[!UICONTROL Profile Merge Rules]は、実際のリアルタイムおよび母集団合計数に影響を与えます。これらの合計は、セグメントが属する[!UICONTROL Profile Merge Rule]がデバイスグラフオプションを使用しているかどうかによって異なります。[定義済みのプロファイルの結合ルールオプション](../../features/profile-merge-rules/merge-rule-definitions.md)も参照してください。

### [!UICONTROL Merge Rules]用セグメント母集団データ（[!UICONTROL Device Graph Option]は使用しない）

次の表は、[!UICONTROL device graph]を使用せずに作成された[!UICONTROL Profile Merge Rule]でセグメントが使用されている場合の、実際のリアルタイム母集団と合計母集団の指標を示しています。これはデバイスオプション設定の&#x200B;**[!UICONTROL No Device Options]**&#x200B;および&#x200B;**[!UICONTROL Current Device Proflie]**&#x200B;です。

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Real-Time Population (Existing)</span> </p> </td> 
   <td colname="col2"> <p>指定した時間範囲にリアルタイムで認識され、また Audience Manager で認識された時点でセグメントについて認定されたユニーク訪問者の実際の数。 </p> <p><span class="wintitle">セグメントビルダー</span>では、直近 30 日間の特性母集団（<span class="wintitle">Total Trait Populations</span>）は、特性と、リアルタイムに評価されたセグメントで異なります。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">特性の場合、直近 30 日間の指標では、その 30 日間で特性に認定されたユニークユーザーが計上されます。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">リアルタイムに評価されたセグメントの場合、直近 30 日間の指標では、過去のいずれかの時点で（当該セグメントの）特性について認定され、その 30 日間で Audience Manager により再度認識されたユーザーが計上されます。例えば、60 日前に特性について認定され、10 日前に再度認識されたユーザーがいるとします。このデータでは、このユーザーが特性について認定されてから 30 日間を超えているので、このユーザーは特性数に加算されません。ただし、リアルタイムに評価されたセグメントの過去 30 日間の数には含まれます。30 日間はセグメントの対象として認定されたからです。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Total Population (Existing)</span> </p> </td> 
   <td colname="col2"> <p>前日のセグメントについて認定されたユニーク訪問者の実際の数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Merge Rules]のセグメント母集団データ（[!UICONTROL Device Graph]オプションあり）

次の表は、[!DNL device graph]オプションを使用せずに作成された[!UICONTROL Profile Merge Rule]でセグメントが使用されている場合の、実際のリアルタイム母集団と合計母集団の指標を示しています。これらは、[!UICONTROL Profile Link Device Graph]、[!DNL Adobe] [!DNL device graph]および他の使用可能なサードパーティの[!DNL device graph]に対するデバイス設定です。


| 列 A | 列 B |
---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | 現在のプロファイルのうち、デバイスグラフで連結された他の最大 100 台のデバイスプロファイルと結合された場合に、Audience Manager での認識時にセグメントについて認定する特性を含むプロファイルを使用する、リアルタイムで認識されるデバイスの実際の数。 |
| [!UICONTROL Total Population (Existing)] | デバイスグラフで連結された他の最大 100 台のデバイスプロファイルで結合された場合にセグメントについて認定されたプロファイルを使用するデバイスの合計数。 |

### セグメント母集団の見積もり時における最新性と頻度の式による制限

[!UICONTROL Segment Builder]では、最大 4 つの最新性と頻度の式を含むセグメントルールのセグメントサイズ見積もりをサポートしています。セグメントルールの作成時に選択する最新性と頻度の式が 4 つを超えると、母集団の見積もり時にセグメント見積もりの画面にエラーが表示されます。

### セグメント母集団の推定時における[!UICONTROL Merge Rules]による制限

現在、セグメントサイズ見積もりで[!UICONTROL profile merge rules]が考慮されていないことが原因で発生する、既知の制限があります。例えば、**[!UICONTROL No Authenticated Profile + Current Device Profile]**[ 結合ルール](../../features/profile-merge-rules/merge-rule-definitions.md)でのセグメントについて見てみましょう。現在のセグメント推定数の計算方法では、推定された母集団に認証済みプロファイルが含まれます。しかし、既存のセグメント母集団では、認証済みプロファイルが適切に無視されます。

>[!MORELIKETHIS]
>
>* [プロファイル結合ルールおよびデバイスグラフに関するよくある質問](../../faq/faq-profile-merge.md)
>* [プロファイルリンク](../profile-merge-rules/merge-rules-overview.md)

