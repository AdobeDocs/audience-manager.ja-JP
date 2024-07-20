---
description: セグメントパフォーマンスレポートは、インプレッションおよびコンバージョン率を使用して、マッピングされたセグメントとマッピングされていないセグメントを比較します。マッピングされたセグメントとは、作成してターゲティングのために宛先に送信したセグメントのことです。マッピングされていないセグメントとは、作成したもののターゲティングのために宛先に送信していないセグメントのことです。レポート内およびレポート間でこれらの異なるセグメントタイプを比較することで、既存のキャンペーンを最適化し、見落としていたセグメントを宛先に送信してターゲティングをおこなうことができます。
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and conversion rates. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: セグメントパフォーマンスレポート
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 100%

---

# セグメントパフォーマンスレポート{#segment-performance-report}

[!UICONTROL Segment Performance]レポートは、インプレッションおよびコンバージョン率を使用して、マッピングされたセグメントとマッピングされていないセグメントを比較します。マッピングされたセグメントとは、作成してターゲティングのために宛先に送信したセグメントのことです。マッピングされていないセグメントとは、作成したもののターゲティングのために宛先に送信していないセグメントのことです。レポート内およびレポート間でこれらの異なるセグメントタイプを比較することで、既存のキャンペーンを最適化し、見落としていたセグメントを宛先に送信してターゲティングをおこなうことができます。

## マッピングされたセグメントの結果を読み取る方法 {#read-mapped-segment-results}

マッピングされた[!UICONTROL Segment Performance]レポートには、作成し、ターゲティングのために宛先に送信したすべてのセグメントが表示されます。レポートのマッピングされたセグメントの位置によって、パフォーマンスが高いセグメントや、何らかの調整が必要な箇所について多くの情報が提供されます。

レポートを読み取りやすくするために、以下のサンプルレポートのように、結果を仮想線（赤色）とカテゴリで 4 つのセクションに分けると便利です。

![](assets/mapped-segment-performance.png)

例のラベルと、次の表を参考にして、セグメントのパフォーマンスとその結果への対応を把握します。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 配置の意味 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上</b> </p> </td> 
   <td colname="col2"> <p>コンバージョン率は良好です。 </p> <p>インプレッションを増やすとさらにコンバージョンを得られる可能性があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下</b> </p> </td> 
   <td colname="col2"> <p>コンバージョン率が低くなっています。 </p> <p>このセグメントはターゲティングから外すこともできます。このセクションのセグメントは、マッピングされていないセグメント結果のセグメントとの比較に適しています。マッピングされていないセグメントの一部が、現在ターゲティングしているセグメントよりパフォーマンスが高い可能性があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上</b> </p> </td> 
   <td colname="col2"> <p>パフォーマンスが高くなっています。これらのセグメントはそのままにしておきます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下</b> </p> </td> 
   <td colname="col2"> <p>コンバージョン率が低く、インプレッションは高くなっています。 </p> <p>このセクションのセグメントはパフォーマンスが低くなっています。このセグメントの予算は、レポートの左上のセクションにあるセグメントに振り向ける必要があります。これにより、インプレッションが減少し、右上のセクションにあるセグメントのコンバージョン率が向上します。また、これらのマッピングされたセグメントを、マッピングされていないセグメントと比較します。マッピングされていないセグメントの一部が、現在ターゲティングしているセグメントよりパフォーマンスが高い可能性があります。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## マッピングされていないセグメントの結果を読み取る方法 {#read-unmapped-segment-results}

[!UICONTROL Segment Performance]レポートで、マッピングされていないセグメントを確認すると、これまでターゲティング対象として考えられていなかった新しいセグメントを発見できます。実際、これらのセグメントの一部は、マッピングされているセグメントよりパフォーマンスが高くなる可能性があります。マッピングされていないセグメントがこのレポートの対象となるには、所定の認定基準を満たす必要があります。マッピングされていないセグメントがこのレポートの対象となるための条件は次のとおりです。

* マッピングされているすべてのセグメントの平均よりもコンバージョンが多い。
* マッピングされていないセグメントのうち、コンバージョン率で上位 100 件の中にある。

レポートを読み取りやすくするために、以下のサンプルレポートのように、結果を仮想線（赤色）とカテゴリで 4 つのセクションに分けると便利です。

![](assets/unmapped-segment-performance.png)

このレポートでは、左上のセクションにある、マッピングされていないセグメントに注目します。このマッピングされていないセグメントは、他の 3 つのセクションに比べて、コンバージョン率は高く、インプレッションは低くなっています。

>[!NOTE]
>
>7 日と 30 日のルックバック期間は、「**[!UICONTROL Date Through]**」の日付が日曜日の場合のみ有効です。
