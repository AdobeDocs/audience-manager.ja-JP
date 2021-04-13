---
description: セグメントパフォーマンスレポートは、インプレッション数およびリアルタイムセグメントのユニーク数を使用して、マッピングされたセグメントとマッピングされていないセグメントを比較します。マッピングされたセグメントとは、作成してターゲティングのために宛先に送信したセグメントのことです。マッピングされていないセグメントとは、作成したもののターゲティングのために宛先に送信していないセグメントのことです。レポート内およびレポート間でこれらの異なるセグメントタイプを比較することで、既存のキャンペーンを最適化し、見落としていたセグメントを宛先に送信してターゲティングをおこなうことができます。
seo-description: セグメントパフォーマンスレポートは、インプレッション数およびリアルタイムセグメントのユニーク数を使用して、マッピングされたセグメントとマッピングされていないセグメントを比較します。マッピングされたセグメントとは、作成してターゲティングのために宛先に送信したセグメントのことです。マッピングされていないセグメントとは、作成したもののターゲティングのために宛先に送信していないセグメントのことです。レポート内およびレポート間でこれらの異なるセグメントタイプを比較することで、既存のキャンペーンを最適化し、見落としていたセグメントを宛先に送信してターゲティングをおこなうことができます。
seo-title: セグメントパフォーマンスレポート
solution: Audience Manager
title: セグメントパフォーマンスレポート 発行者
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization レポート
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 99%

---

# セグメントパフォーマンスレポート {#segment-performance-report}

セグメントパフォーマンスレポートは、インプレッション数およびリアルタイムセグメントのユニーク数を使用して、マッピングされたセグメントとマッピングされていないセグメントを比較します。

マッピングされたセグメントとは、作成してターゲティングのために宛先に送信したセグメントのことです。マッピングされていないセグメントとは、作成したもののターゲティングのために宛先に送信していないセグメントのことです。

レポート内およびレポート間でこれらの異なるセグメントタイプを比較することで、既存のキャンペーンを最適化し、見落としていたセグメントを宛先に送信してターゲティングをおこなうことができます。

## ユースケース {#use-cases}

[!UICONTROL Segment Performance] レポートを使用すると、次のことができます。

* スケールやパフォーマンスを促進しているマッピングされたオーディエンスセグメントを特定する。
* 過去のパフォーマンスに対するオーディエンスの貢献度に基づいて、今後のキャンペーンで導入するマッピングされていないセグメントを特定する。

## セグメントパフォーマンスレポートの使用  {#using-segment-performance-report}

「**[!UICONTROL Mapped]**」と「**[!UICONTROL Unmapped]**」を切り替えて、宛先にマッピングされているセグメントとマッピングされていないセグメントのどちらかを選択します。「**[!UICONTROL All]**」を選択すると、すべてのセグメントがレポートに含まれます。

**Day Range** コントロールと **Date Through** コントロールを使用して、ルックバック範囲を調整します。7 日と 30 日のルックバック期間は、日付が日曜日の場合にのみ有効であることに注意してください。

「**[!UICONTROL Line Item]**」ドロップダウンボックスを使用して、情報を求めている Web プロパティを選択します。

「**[!UICONTROL Segment Data Source]**」ドロップダウンボックスで、レポートに表示するセグメントが含まれているデータソースを選択します。

「**[!UICONTROL Segment]**」ドロップダウンボックスを使用して、レポートに表示するセグメントを選択します。

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers] を有効にする際には、[Google Ad Manager（旧称 DFP）データファイルを Audience Manager に読み込む](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)の手順 3 に記載されているように、[!UICONTROL Line Item IDs] の記述メタデータを含める必要があります。これにより、Web プロパティの詳細が[!UICONTROL Line Item ID] ではなく[!UICONTROL Line Item]として表示されるようになります。

## 結果の解釈 {#interpreting-results}

[!UICONTROL Segment Performance]レポートは次のようになります。レポート内でバブルをクリックすると、基になっているデータが表示されます。追加情報については、サンプルレポートの下の表を参照してください。

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>セグメント </p> </td> 
   <td colname="col2"> <p>このセグメントに割り当てた名前（英数字）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segment ID </p> </td> 
   <td colname="col2"> <p>このセグメントの一意な ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Line item </p> </td> 
   <td colname="col2"> <p>このレポートの対象となっている Web プロパティ。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Clicks </p> </td> 
   <td colname="col2"> <p>この特性のメンバーが Web プロパティ内の項目をクリックした回数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impressions </p> </td> 
   <td colname="col2"> <p>この特性のメンバーにインベントリが表示された回数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>クリックスルー率。 </p> <p>この指標は、クリックで遂行されたインプレッションの割合（パーセント）を示します。クリック数をインプレッション数で除算すると、この指標が得られます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Realtime Segment Population </p> </td> 
   <td colname="col2"> <p>指定した時間範囲にリアルタイムで認識され、また <span class="keyword"> Audience Manager</span> で認識された時点でセグメントについて認定されたユニーク訪問者の実際の数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## マッピングされたセグメントの結果を読み取る方法 {#read-mapped-segment}

レポート内でマッピングされたセグメントの位置から、どのセグメントのパフォーマンスが高く、どの部分で調整が必要であるかが明確にわかります。

レポートを読み取りやすくするために、以下のサンプルレポートのように、結果を仮想線（赤色）とカテゴリで 4 つのセクションに分けると便利です。例のラベルを参考にして、セグメントのパフォーマンスとその結果への対応を把握できます。

![](assets/publisher_segment_performance_mapped.png)

## マッピングされていないセグメントの結果を読み取る方法 {#read-unmapped-segment}

[!UICONTROL Segment Performance]レポートで、マッピングされていないセグメントを確認すると、これまでターゲティング対象として考えられていなかった新しいセグメントを発見できます。実際、これらのセグメントの一部は、マッピングされているセグメントよりパフォーマンスが高くなる可能性があります。

このレポートを読み取りやすくするために、以下のサンプルレポートのように、結果を仮想線（赤色）とカテゴリで 4 つのセクションに分けると便利です。

![](assets/publisher_segment_performance_unmapped.png)
