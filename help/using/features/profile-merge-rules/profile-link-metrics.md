---
description: Profile Link 指標は、サイトへの認証をおこなうユーザーやデバイスに関するデータを提供します。プロファイルリンクのデータとグラフは、結合ルールを作成したとき、または Profile Merge Rules ダッシュボードで既存のルールをクリックしたときに、動的に更新されます。これらの指標には、他のサードパーティのデバイスグラフソースからのデバイスグラフが含まれる場合があります。
seo-description: Profile Link metrics provide data about people and devices that authenticate to your site. The data and graphs in Profile Link update dynamically as you create a merge rules or when you click an existing rule from the Profile Merge Rules dashboard. These metrics can include device graph from other third-party device graph sources.
seo-title: Report Metrics for Profile Merge Rules
solution: Audience Manager
title: プロファイル結合ルールのレポート指標
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Profile Merge
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 82%

---

# プロファイル結合ルールのレポート指標 {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule]指標は、サイトへの認証をおこなうユーザーやデバイスに関するデータを提供します。[!UICONTROL Profile Merge Rule Reports] のデータとグラフは、結合ルールを作成したとき、または [!UICONTROL Profile Merge Rules] ダッシュボードで既存のルールをクリックしたときに、動的に更新されます。これらの指標には、他のサードパーティのデバイスグラフソースからのデバイスグラフが含まれます。

## 結合ルールの指標 {#merge-rule-metrics}

結合ルールにより、でアクセス可能なサードパーティのデバイスグラフからのデータが使用されると、データが横並びの棒グラフで返されます [!DNL Audience Manager]. これにより、認証済みのファーストパーティのデータを、サードパーティのデバイスグラフから得られるクロスデバイスデータと比較できます。 このデータは毎日更新されます。

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Authenticated Activity</span></b> </p> </td> 
   <td colname="col2"> <p>以下の項目が表示されます。 </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle">Active People</span>：直近 60 日間でサイトで認証されたユーザーの数。 </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle">Cross Device</span>：選択した<a href="merge-rule-definitions.md">認証済みプロファイル</a>の<a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html?lang=ja">データソース</a>に、そのデータソースが存在した期間内に保存された<a href="merge-rules-start.md#create-data-source">クロスデバイス ID</a> の総数。 </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle">% Active People</span>：「<span class="wintitle">Active People</span>」を割合として表します。 </li> 
    </ul> <p> 「<span class="wintitle">Authenticated Activity</span>」では、アクティブなユーザー数、ユーザーの総数、割合によってデータを比較することができます。これにより、ユーザー数が多いデータソースや、アクティブなユーザーの割合が多いデータソースを特定できます。また、データソースの比較により、オーディエンス全体と比べてアクティブなユーザーの割合が多い値を特定することもできます。例えば、全期間ユーザー数が少なくアクティブなユーザー数が多いデータソースのほうが、全期間ユーザー数が多くアクティブなユーザー数が少ないデータソースより重要であることがあります。 </p> <p> <p>注意：「<span class="wintitle">Authenticated Activity</span>」指標の対象となっているのは<span class="wintitle">プロファイルリンク</span>データのみです。このレポートには<span class="wintitle">デバイスグラフ</span>データは含まれません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Average Devices per Person</span></b> </p> </td> 
   <td colname="col2"> <p> 選択したデータソースについて、サイトで認証された訪問者が使用しているデバイスの平均数を示しています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Total Devices</span></b> </p> </td> 
   <td colname="col2"> <p>選択したデータソースについて、サイトでの認証に使用されたデバイスの総数を示しています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Total People</span></b> </p> </td> 
   <td colname="col2"> <p>選択したデータソースについて、明確に識別されたユーザーの総数を示しています。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## デバイスグラフの指標 {#device-graph-metrics}

[!UICONTROL Merge Rules]レポートには、選択したデータソースとデバイスグラフについて、サイトを訪問したユーザーとデバイスの総数に関するデータも記載されます。これらの指標では、事前設定された期間（ルックバック期間）に基づいてデータが返されます。この期間は、ルールの作成時に選択したデバイスオプションによって異なります。次の表は、デバイスグラフオプションごとのレポート間隔の一覧です。

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> デバイスグラフオプション </th> 
   <th colname="col2" class="entry"> レポートのルックバック間隔 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> プロファイルリンク</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">ユーザー総数：60 日 </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">デバイス総数：120 日 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">ユーザー総数：180 日 </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">デバイス総数：180 日 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">ユーザー総数：60 日 </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">デバイス総数：60 日 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## サンプルのレポート {#sample-reports}

### 標準プロファイルリンクレポート

標準の[!UICONTROL Profile Link]レポートは、次の例のようになります。複数（最大 3 つ）のデータソースを使用する結合ルールでは、データソースごとに異なるタブでグラフが表示されます。この結合ルールでは、[!UICONTROL external device graph] のデータは対象となりません。

![](assets/profile-link-metrics.png)

### デバイスグラフデータによるプロファイルリンクレポート

A [!UICONTROL Profile Link Device Graph] サードパーティのデバイスグラフのデバイスグラフデータを含むレポートに表示される [!UICONTROL Profile Link] とデバイスグラフのデータが横並びの棒グラフで表示されます。 これらのグラフを横並びに配置することで、 [!UICONTROL Profile Link] 単独で 複数（最大 3 つ）のデータソースを使用する結合ルールでは、データソースごとに異なるタブでグラフが表示されます。[!UICONTROL Authenticated Activity] のグラフと指標では、[!DNL Adobe]のデバイスグラフや、その他の [!DNL Audience Manager] からアクセスできるサードパーティのデバイスグラフからのデータは返されません。

![](assets/profile-link-graph.png)

## プロファイルリンクのトレンドグラフ {#profile-link-trend}

[!UICONTROL Profile Link]レポートには、他のデータ視覚化手段に加えて、線グラフもあります。この線グラフは、時間の経過に伴うプロファイルルールのトレンドを示しています。トレンドグラフ（およびその他のレポート）は、[!UICONTROL Profile Merge Rules] ランディングページ（**[!UICONTROL Audience Data > Profile Merge Rules]**）からルールをクリックすると利用できます。にアクセスできるサードパーティのデバイスグラフのメンバーの場合、デバイスグラフのデータがこれらのグラフの対象になります [!DNL Audience Manager]. トレンドラインをクリックすると、基になるデータが表示されます。

>[!MORELIKETHIS]
>
>* [プロファイル結合ルール FAQ](../../faq/faq-profile-merge.md)

