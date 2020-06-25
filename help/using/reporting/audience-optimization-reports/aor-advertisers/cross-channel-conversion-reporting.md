---
description: Audience Optimization レポートの「クロスチャネルコンバージョン」オプションを使用すると、提供されたオンラインのインプレッションやクリックがオフラインのコンバージョンにどの程度貢献しているかを把握することができます。
seo-description: Audience Optimization レポートの「クロスチャネルコンバージョン」オプションを使用すると、提供されたオンラインのインプレッションやクリックがオフラインのコンバージョンにどの程度貢献しているかを把握することができます。
seo-title: クロスチャネルコンバージョン
solution: Audience Manager
title: クロスチャネルコンバージョン
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 100%

---


# クロスチャネルコンバージョン{#cross-channel-conversion}

Audience Optimization レポートの「クロスチャネルコンバージョン」オプションを使用すると、提供されたオンラインのインプレッションやクリックがオフラインのコンバージョンにどの程度貢献しているかを把握することができます。

[!UICONTROL Cross Channel Conversion]レポートは、[!DNL DoubleClick Campaign Manager]（DCM）プラットフォームから得られた結果と [!DNL Audience Manager] のコンバージョン特性を組み合わせたものです。これにより、オフラインのコンバージョンをオンラインのインプレッションやクリックに関連付けることができます。

[!UICONTROL Cross Channel Conversion]は、[セグメントパフォーマンス](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) レポートと[最適な頻度](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md)レポートに使用できます。

[!UICONTROL Cross Channel Conversion]レポートを表示するには、**[!UICONTROL AAM+DCM]**&#x200B;ドロップダウンリストで **[!UICONTROL Platform]** アイテムを選択します。

[!UICONTROL Cross Channel Conversion]をセットアップする際に考慮すべき重要な事項を次の表に示します。

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
