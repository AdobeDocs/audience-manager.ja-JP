---
description: Audience Optimization レポートの「Cross Channel Conversion」オプションを使用すると、提供されたオンラインのインプレッションやクリックがオフラインのコンバージョンにどの程度貢献しているかを把握することができます。
seo-description: Audience Optimization レポートの「Cross Channel Conversion」オプションを使用すると、提供されたオンラインのインプレッションやクリックがオフラインのコンバージョンにどの程度貢献しているかを把握することができます。
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Cross Channel Conversion
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# クロスチャネルコンバージョン{#cross-channel-conversion}

Audience Optimization レポートの「Cross Channel Conversion」オプションを使用すると、提供されたオンラインのインプレッションやクリックがオフラインのコンバージョンにどの程度貢献しているかを把握することができます。

[!UICONTROL Cross Channel Conversion] レポートでは、 [!DNL DoubleClick Campaign Manager] （DCM）プラットフォームの結果をコンバージョン特性と [!DNL Audience Manager] 組み合わせています。これにより、オフラインのコンバージョンをオンラインのインプレッションやクリックに関連付けることができます。

[!UICONTROL Cross Channel Conversion][セグメントのパフォーマンスレポート](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) と [最適な頻度](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) レポートで使用できます。

To view the [!UICONTROL Cross Channel Conversion] reports, select the **[!UICONTROL AAM+DCM]** item in the **[!UICONTROL Platform]** drop-down list.

The following table lists important considerations when setting up [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 考慮事項 </th> 
   <th class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>コンバージョン特性の最小数 </p> </td> 
   <td colname="col1"> <p><span class="wintitle">クロスチャネルコンバージョン</span>レポートを実行するには、コンバージョン特性を少なくとも 1 つデータソースに割り当てる必要があります。特性について詳しくは、<a href="../../../features/traits/create-onboarded-rule-based-traits.md">特性の基本情報</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>コンバージョン特性の最大数 </p> </td> 
   <td colname="col1"> <p>レポートでは、ユーザーから<i>最大</i> 50 個のコンバージョン特性を取り込みます。上限に達した場合は、特性 ID の昇順に並べたコンバージョン特性の最初の 50 個がレポートで使用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>アトリビューション期間 </p> </td> 
   <td> <p> <b><span class="uicontrol">AAM+DCM</span></b> アトリビューション期間は 14 日です。つまり、最近の 2 週間に示されたコンバージョン特性のみ考慮されます。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ラストタッチ方法論 </p> </td> 
   <td> <p>ユーザーがコンバージョンの前に最後に見たクリエイティブが、コンバージョンに貢献します。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>クリックかインプレッションか </p> </td> 
   <td> <p>クリックとインプレッションがまったく同じ時刻に発生した場合、アトリビューションを決定する際には、クリックがインプレッションより優先します。例えば、複数のクリエイティブが表示されるページでは、クリックされたものがコンバージョンにつながります。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>データ最新性 </p> </td> 
   <td> <p>レポートは、必ず、前日に得られたデータについて計算されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>
