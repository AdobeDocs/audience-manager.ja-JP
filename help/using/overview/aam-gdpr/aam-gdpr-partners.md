---
description: このページでは、入手可能になったときにパートナーから直接提供される情報の概要と、Audience Manager の運用に関連する影響について説明します。パートナー側でこれらの更新をおこなう場合の主な影響は、2018 年 5 月 25 日に施行された GDPR（EU 一般データ保護規則）と、新しい IAB GDPR Transparency & Consent Framework（透明性と同意に関するフレームワーク、以下「IAB フレームワーク」）の結果です。
seo-description: このページでは、入手可能になったときにパートナーから直接提供される情報の概要と、Audience Manager の運用に関連する影響について説明します。パートナー側でこれらの更新をおこなう場合の主な影響は、2018 年 5 月 25 日に施行された GDPR（EU 一般データ保護規則）と、新しい IAB GDPR Transparency & Consent Framework（透明性と同意に関するフレームワーク、以下「IAB フレームワーク」）の結果です。
seo-title: 宛先の GDPR に関する考慮事項
solution: Audience Manager
title: 宛先の GDPR に関する考慮事項
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: 69be038d0f2d31b6b5eda20041082c1890abc38f

---


# 宛先の GDPR に関する考慮事項{#gdpr-considerations-for-destinations}

このページでは、入手可能になったときにパートナーから直接提供される情報の概要と、Audience Manager の運用に関連する影響について説明します。パートナー側でこれらの更新をおこなう場合の主な影響は、2018 年 5 月 25 日に施行された GDPR（EU 一般データ保護規則）と、新しい IAB GDPR Transparency &amp; Consent Framework（透明性と同意に関するフレームワーク、以下「IAB フレームワーク」）の結果です。

アドビパートナーには独自のビジネスプロセスがあり、時には Audience Manager との統合要件の更新を決定することもあります。アドビでは、Audience Manager パートナーエコシステムと積極的に協力して、お客様に変更を絶えずお知らせしています。

## Audience Manager パートナー向け最新情報 - ID 同期 {#partner-updates-id-syncs}

以下の表に示すとおり、一部のパートナーでは、GDPR 標準に準拠するために、Audience Manager との統合要件を変更して、IAB フレームワークに基づくサポートを組み込むようになりました。

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>パートナー名 </p> </th> 
   <th colname="col2" class="entry"> <p>予想される影響 </p> </th> 
   <th colname="col3" class="entry"> <p>変更ステータス </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>欧州連合（EU）内のユーザーに対する ID 同期がパートナー側で廃止されます </p> </td> 
   <td colname="col3"> <p>2018 年 5 月 22 日以降実施中 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>欧州連合（EU）内のユーザーに対する ID 同期がパートナー側で廃止されます </p> </td> 
   <td colname="col3"> <p>未実施 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>欧州連合（EU）内のユーザーに対する ID 同期がパートナー側で廃止されます </p> </td> 
   <td colname="col3"> <p>未実施 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>欧州連合（EU）内のユーザーに対する ID 同期がパートナー側で廃止されます </p> </td> 
   <td colname="col3"> <p>未実施 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager UI 更新 - Yahoo／Oath／DataX との統合 {#ui-update}

上記 IAB フレームワークへの更新に加えて、Yahoo／Oath／DataX では、分類 API と Audience API に **gdpr** および **gdpr_mode** という新しいパラメーターを追加しました。これらのパラメーターは、データプロセッサーまたはデータコントローラーとして特定のセグメントを処理する権限があることを Yahoo／Oath／DataX に知らせます。結果的に、Yahoo／Oath／DataX の宛先にセグメントを送信する Audience Manager のお客様は、Oath との合意に基づいて、適切なパラメーター（プロセッサーまたはコントローラー）を指定する必要があります。

担当のコンサルタントまたはクライアントケアに問い合わせて、正しいパラメーターを設定してください。アドビでは、この更新の依頼をお客様から書面で受け取る場合を除き、お客様の代わりにこの更新をおこなうことはできません。Yahoo／Oath／DataX 担当者に問い合わせて、これらのパラメーターの定義を十分に理解してください。

## セグメント解除に対応している Audience Manager パートナー {#aam-partners-with-unsegmentation}

お客様が GDPR 要求を自動化できるよう、Audience Manager からアクティベーションパートナーに対してセグメント解除（またはセグメント削除）の情報が送信され、データ主体からの削除要求が通知されます。

ただし、一部のアクティベーションパートナーは、以下のいずれかまたは両方の状態である場合があります。

1. アドビからのセグメント解除の要求をサポートしていない。
1. 30 日に 1 回より高い頻度でアドビからの更新を受け取ることができない。

このような場合、お客様はアクティベーションパートナーに対して、Audience Manager から自動で削除要求を送信することはできません。Audience Manager のアクティベーションパートナーの中でどれがセグメント解除をサポートしているかを確認するには、[パートナーに関する Excel シート](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)をダウンロードしてください。
