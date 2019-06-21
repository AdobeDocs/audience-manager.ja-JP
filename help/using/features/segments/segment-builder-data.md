---
description: セグメントビルダーで特性を追加または削除すると、実際と推定のセグメントユーザー数データと一緒に、実際の特性ユーザー数が表示されます。推定ユーザー数のデータは、キャンペーンに適したセグメントを作成するのに役立ちます。
seo-description: セグメントビルダーで特性を追加／削除することで、特性の実際の母集団やセグメント母集団データの実際値と推測値を表示できます。推定ユーザー数のデータは、キャンペーンに適したセグメントを作成するのに役立ちます。
seo-title: セグメントビルダーの特性およびセグメント母集団データ
solution: Audience Manager
title: セグメントビルダーの特性およびセグメント母集団データ
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# セグメントビルダーにおける特性とセグメントのユーザー数データ {#trait-and-segment-population-data-in-segment-builder}

Add and remove traits in [!UICONTROL Segment Builder] to see actual trait populations along with actual and estimated segment population data. 推定ユーザー数のデータは、キャンペーンに適したセグメントを作成するのに役に立ちます。

## 特性母集団データ {#trait-population-data}

[!UICONTROL Segment Builder][!UICONTROL Total Trait Population] をクリックします。このデータは、「[!UICONTROL Basic View]」セクションで選択した特性の周囲の青色のフィールドに表示されます。

![](assets/trait-size.png)

次の表は、特性母集団の指標です。

<table id="table_9D837CF9ACA04D04BEE5925EC0B4A5D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 説明 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 合計特性母集団</span> </p> </td>
   <td colname="col2"> <p>選択した特性がプロファイルにある一意の ID の数。 </p> </td>
  </tr> 
 </tbody> 
</table>

## 実際のセグメント母集団と推定セグメント母集団の計算 {#calculating-real-estimated-populations}

新しいセグメントの作成時、または既存のセグメントの変更時は、Audience Manager で実際のリアルタイムセグメント母集団と合計セグメント母集団が表示されるまでに最大 24 時間かかります。

ただし、セグメントのリアルタイム母集団と合計母集団のサイズの予測は Audience Manager ですぐにおこなうことができます。この予測はサンプリングされた履歴データに基づいておこなわれ、95% の信頼区間で結果が返されます。

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder], a blue bar on the estimated population graphs indicates the possible upper and lower ranges for segment size. 過去のパフォーマンスから将来の結果が保証されているわけではありませんが、推定データを使用すると新しいセグメントや編集したセグメントのサイズがどの程度になる可能性があるか把握できます。

## セグメント母集団データの概要 {#segment-populations}

[!UICONTROL Segment Builder] セグメントの作成および編集の際に、セグメント母集団データを表示します。

* For estimated segment population data (real-time and total), [!UICONTROL Segment Builder] does not update the graphs automatically as you add or remove traits in a segment. 「**[!UICONTROL Calculate Estimates]**」をクリックすると、推定された母集団の数値が表示（または更新）されます。

* For actual (real) segment population data (real-time and total), [!UICONTROL Segment Builder] updates the segment graph automatically when you load an existing segment. 新しいセグメントを作成した場合、または既存のセグメントに新しい特性を追加した場合、実際の母集団データはセグメントの作成から 24 時間が経過するまで更新されません。

![](assets/segment-data.png)

以下の表で、推定されたセグメント母集団データと実際のセグメント母集団データの詳細を確認してください。

## 推定セグメント母集団データの定義 {#estimated-segment-population}

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
   <td colname="col2"> <p>指定した時間範囲にリアルタイムで認識され、また Audience Manager で認識された時点でセグメントについて認定された個別訪問者の推定数。 </p> <p><span class="wintitle">セグメントビルダー</span>では、直近 30 日間の特性母集団（<span class="wintitle">合計特性母集団</span>）は、特性と、リアルタイムに評価されたセグメントで異なります。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">特性の場合、直近 30 日間の指標では、その 30 日間で特性に認定された個別ユーザーが計上されます。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">リアルタイムに評価されたセグメントの場合、直近 30 日間の指標では、過去のいずれかの時点で（当該セグメントの）特性について認定され、その 30 日間で Audience Manager により再度認識されたユーザーが計上されます。例えば、60 日前に特性について認定され、10 日前に再度認識されたユーザーがいるとします。このデータでは、このユーザーが特性について認定されてから 30 日間を超えているので、このユーザーは特性数に加算されません。ただし、リアルタイムに評価されたセグメントの過去 30 日間の数には含まれます。30 日間はセグメントの対象として認定されたからです。 </li>
     </ul> </p> <p> <p>注意：「<span class="wintitle">Estimated Real-Time Population</span><span class="wintitle"></span>」指標には、<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">デバイスグラフオプション</a>を使用するプロファイル結合ルールにより実行された結合に基づきセグメントについて認定されたデバイスは含まれません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Estimated Total Population (Potential)</span> </p> </td> 
   <td colname="col2"> <p>新しいセグメント、または変更されたセグメントに含まれる可能性がある個別訪問者の推定数。他の大部分の予測と同様に、過去のパフォーマンスから将来の結果が保証されているわけではありませんが、推定合計数は次の用途で使用できます。 </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">セグメントの作成時に、新しいセグメントや変更後のセグメントがリーチできるユーザーの数を把握する。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">目標に応じてセグメントを調整する。例えば、大規模なセグメントはブランド認知キャンペーンに便利で、小規模なセグメントは対象を限定したターゲティングやリターゲティングキャンペーンに便利です。 </li> 
     </ul> </p> <p> <p>注意：「<span class="wintitle">Estimated Total Population</span><span class="wintitle"></span>」指標には、<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">デバイスグラフオプション</a>を使用するプロファイル結合ルールにより実行された結合に基づきセグメントについて認定されたデバイスは含まれません。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 既存（実際）のセグメント母集団データの定義 {#existing-segment-population}

[!UICONTROL Profile Merge Rules] は、実際のリアルタイムと合計人口の合計に影響します。These totals vary depending on if the [!UICONTROL Profile Merge Rule] a segment belongs to uses a device graph option or not. [定義済みのプロファイルの結合ルールオプション](../../features/profile-merge-rules/merge-rule-definitions.md)も参照してください。

### デバイスグラフオプションがない結合ルールのセグメント母集団データ

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created without a device graph option. These are the device options settings **[!UICONTROL No Device Options]** and **[!UICONTROL Current Device Proflie]**.

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
   <td colname="col2"> <p>指定した時間範囲にリアルタイムで認識され、また Audience Manager で認識された時点でセグメントについて認定された個別訪問者の実際の数。 </p> <p><span class="wintitle">セグメントビルダー</span>では、直近 30 日間の特性母集団（<span class="wintitle">合計特性母集団</span>）は、特性と、リアルタイムに評価されたセグメントで異なります。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">特性の場合、直近 30 日間の指標では、その 30 日間で特性に認定された個別ユーザーが計上されます。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">リアルタイムに評価されたセグメントの場合、直近 30 日間の指標では、過去のいずれかの時点で（当該セグメントの）特性について認定され、その 30 日間で Audience Manager により再度認識されたユーザーが計上されます。例えば、60 日前に特性について認定され、10 日前に再度認識されたユーザーがいるとします。このデータでは、このユーザーが特性について認定されてから 30 日間を超えているので、このユーザーは特性数に加算されません。ただし、リアルタイムに評価されたセグメントの過去 30 日間の数には含まれます。30 日間はセグメントの対象として認定されたからです。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Total Population (Existing)</span> </p> </td> 
   <td colname="col2"> <p>前日のセグメントについて認定された個別訪問者の実際の数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### デバイスグラフオプションを使用する結合ルールのセグメント母集団データ

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created with a device graph option. これらは、[!UICONTROL Profile Link Device Graph]、[!DNL Adobe] デバイスグラフおよび他の使用可能なサードパーティのデバイスグラフのデバイス設定です。

<table id="table_157EC6E5B5C44EB899854CA10B090F60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Real-Time Population (Existing)</span> </p> </td> 
   <td colname="col2"> <p>現在のプロファイルのうち、デバイスグラフで連結された他の最大 3 つのデバイスプロファイルと結合された場合に、<span class="keyword">Audience Manager</span> での認識時にセグメントについて認定する特性を含むプロファイルを使用する、リアルタイムで認識されるデバイスの実際の数。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Total Population (Existing)</span> </p> </td> 
   <td colname="col2"> <p>デバイスグラフで連結された他の最大 3 つのデバイスプロファイルで結合された場合にセグメントについて認定されたプロファイルを使用するデバイスの合計数。 </p> </td>
  </tr>
 </tbody>
</table>

### セグメント母集団の見積もり時における最新性と頻度の式による制限

[!UICONTROL Segment Builder] は、最大4つの最新性および頻度式を含むセグメントルールのセグメントサイズを指定します。セグメントルールの作成時に選択する最新性と頻度の式が 4 つを超えると、母集団の見積もり時にセグメント見積もりの画面にエラーが表示されます。

### セグメント母集団の推定時における結合ルールによる制限

現在、セグメントサイズ見積もりでプロファイル結合ルールが考慮されていないことが原因の既知の制限があります。For example, look at segments with the **No Authenticated Profile + Current Device Profile** [merge rule](../../features/profile-merge-rules/merge-rule-definitions.md). 現在のセグメント推定数の計算方法では、推定された母集団に認証済みプロファイルが含まれます。しかし、既存のセグメント母集団では、認証済みプロファイルが適切に無視されます。

>[!MORE_LIKE_THIS]
>
>* [プロファイル結合ルールおよびデバイスグラフに関するよくある質問](../../faq/faq-profile-merge.md)
>* [Profile Link](../../features/profile-merge-rules/merge-rules-overview.md)

