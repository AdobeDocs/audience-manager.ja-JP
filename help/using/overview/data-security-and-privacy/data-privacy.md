---
description: 消費者のプライバシーおよびオプトアウト手順に関連する一般に認められたベストプラクティスに対する Audience Manager の統合と準拠について説明します。
seo-description: 消費者のプライバシーおよびオプトアウト手順に関連する一般に認められたベストプラクティスに対する Audience Manager の統合と準拠について説明します。
seo-title: データのプライバシー
solution: Audience Manager
title: データのプライバシー
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

---


# データのプライバシー{#data-privacy}

消費者のプライバシーおよびオプトアウト手順に関連する一般に認められたベストプラクティスに対する Audience Manager の統合と準拠について説明します。

## データのプライバシー {#data-privacy-center}

[アドビプライバシーセンター](https://www.adobe.com/privacy/opt-out.html)を参照してください。

## 消費者のプライバシー保護 {#consumer-privacy-protection}

Audience Manager では、利用するオンラインブランドとの間で消費者が暗黙に結ぶ契約を認識します。両者とも、匿名データ要素の透過的な交換のメリットを得ることができます。

* 消費者は、パーソナライズされたコンテンツ、割引製品オファー、効率化されたユーザーエクスペリエンスを得ることができます。
* ブランドは、複数のオンラインビジネスモデルをサポートする非常に重要な収入源を得ることができます。

このモデルの継続的なサポートの一環として、Audience Manager では、消費者への透明性と管理を提供し、オンライン行動ターゲティング広告（OBA）に関する自主的行動規範を遵守および強化することに引き続き全力で取り組んでいます。

## オプトアウト管理 {#opt-out-management}

オプトアウトに関するドキュメントは拡充され、別個のドキュメントに移動しました。詳しくは、[オプトアウト管理](../../overview/data-security-and-privacy/opt-out-management.md)を参照してください。

<!-- 

<p>  </p>
<table id="table_A1FF33B328BD451FAFF6C6B8422F928B"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="2.74*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Opt-Out For </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
    <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page</a> provides 1-click features that let you control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section</a> of the Privacy Choices page. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Browsers that do not support third-party cookies </p> </td> 
    <td colname="col2"> <p>See <a href="../../features/declared-ids.md#declared-id-targeting"> Declared ID Targeting</a>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Mobile devices </p> </td> 
    <td colname="col2"> <p>See the opt-out and privacy settings for: </p> <p> 
      <ul id="ul_86EFAB879215403D937B5148C26A41D9"> 
       <li id="li_C0B544E8F4FE473B94A5436D3A60BDB1"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android devices</a> </li> 
       <li id="li_26C787BAB729499A9FEDF055E9AB0637"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS devices</a> </li> 
      </ul> </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

## IP アドレスの収集と IP アドレスの難読化 {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

顧客の Web サイトにアクセスする訪問者の IP アドレスは Adobe Data Processing Center（DPC）に転送され、同センターで保存される場合があります。訪問者のネットワーク設定によっては、この IP アドレスが訪問者のコンピューターの IP アドレスと一致しないことがあります。例えば、この IP アドレスは、Network Address Translation（NAT）ファイアウォール、HTTP プロキシ、またはインターネットゲートウェイの外部 IP アドレスである可能性があります。

**IP 難読化方法：**「プライバシーバイデザイン」の原則に従い、Adobe Audience Manager では、すべての地域に対してグローバルに、または特定の国に対して、UI からの IP 難読化を有効にすることができます。この設定を有効にすると、IP アドレスが Audience Manager に取り込まれると、IP アドレスの最後のオクテット（最後の部分）は即座に破棄されます。Audience Manager は、処理（オプションの IP アドレスの地域の参照またはログ作成を含む）に先立って、IP アドレスのこの部分を破棄します。次に例を示します。

* マスク前： `255.255.255.255`
* マスク後： `255.255.255.0`

>[!NOTE]
>
>Audience Manager UI で IP アドレスを難読化する方法については、[IP アドレスの難読化](/help/using/features/administration/ip-obfuscation.md)をお読みください。

**地理的分類：** IP アドレスの難読化を有効にした場合、その IP アドレスの残りのオクテットは引き続き、Audience Manager の地域特性およびレポートに使用できます。IP アドレスの難読化を有効にしない場合、Audience Manager は完全な IP アドレスを使用します。どちらの場合でも、IP の場所を地理的地域によって特定できる地理的セグメンテーション機能を使用できますが、IP の難読化を使用している場合は、精度が少し落ちます。IP アドレスの不明化をおこなうと、市レベルの情報の取得が著しく困難になる場合があります。地域レベルおよび国レベルの情報の取得に関しては、それほど大きな影響はありません。地理的セグメンテーションデータの精度は市区町村レベルまたは郵便番号レベルにとどまり、個人レベルにまでは及びません。[地域に基づくターゲティング](/help/using/features/traits/trait-geotarget-keys.md)と、地理的変数を使用した特性の設定方法についてお読みください。

## 関連する概念 {#related-concepts}

* [オプトアウト管理](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [プライバシーとデータ保持に関するよくある質問](/help/using/faq/faq-privacy.md)