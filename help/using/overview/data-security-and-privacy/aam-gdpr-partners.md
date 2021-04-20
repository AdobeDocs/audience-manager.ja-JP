---
description: このページでは、入手可能になったときにパートナーから直接提供される情報の概要と、Audience Manager の運用に関連する影響について説明します。パートナー側でこれらの更新をおこなう場合の主な影響は、2018 年 5 月 25 日に施行された GDPR（EU 一般データ保護規則）と、新しい IAB GDPR Transparency & Consent Framework（透明性と同意に関するフレームワーク、以下「IAB フレームワーク」）の結果です。
seo-description: このページでは、入手可能になったときにパートナーから直接提供される情報の概要と、Audience Manager の運用に関連する影響について説明します。パートナー側でこれらの更新をおこなう場合の主な影響は、2018 年 5 月 25 日に施行された GDPR（EU 一般データ保護規則）と、新しい IAB GDPR Transparency & Consent Framework（透明性と同意に関するフレームワーク、以下「IAB フレームワーク」）の結果です。
seo-title: 宛先の GDPR に関する考慮事項
solution: Audience Manager
title: 宛先の GDPR に関する考慮事項
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Data Governance & Privacy
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 99%

---

# 宛先の GDPR に関する考慮事項 {#gdpr-considerations-for-destinations}

このページでは、入手可能になったときにパートナーから直接提供される情報の概要と、Audience Manager の運用に関連する影響について説明します。パートナー側でこれらの更新をおこなう場合の主な影響は、2018 年 5 月 25 日に施行された GDPR（EU 一般データ保護規則）と、新しい IAB GDPR Transparency &amp; Consent Framework（透明性と同意に関するフレームワーク、以下「IAB フレームワーク」）の結果です。

アドビパートナーには独自のビジネスプロセスがあり、時には Audience Manager との統合要件の更新を決定することもあります。アドビでは、Audience Manager パートナーエコシステムと積極的に協力して、お客様に変更を絶えずお知らせしています。

<!-- ## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table> -->

## Audience Manager ユーザーインターフェイスの更新 - Yahoo／Oath／DataX との統合 {#ui-update}

上記 IAB フレームワークへの更新に加えて、Yahoo／Oath／DataX では、分類 API と Audience API に **gdpr** および **gdpr_mode** という新しいパラメーターを追加しました。これらのパラメーターは、データプロセッサーまたはデータコントローラーとして特定のセグメントを処理する権限があることを Yahoo／Oath／DataX に知らせます。結果的に、Yahoo／Oath／DataX の宛先にセグメントを送信する Audience Manager のお客様は、Oath との合意に基づいて、適切なパラメーター（プロセッサーまたはコントローラー）を指定する必要があります。

担当のコンサルタントまたはクライアントケアに問い合わせて、正しいパラメーターを設定してください。アドビでは、この更新の依頼をお客様から書面で受け取る場合を除き、お客様の代わりにこの更新をおこなうことはできません。Yahoo／Oath／DataX 担当者に問い合わせて、これらのパラメーターの定義を十分に理解してください。
