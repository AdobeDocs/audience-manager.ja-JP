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

オプトアウトに関するドキュメントは拡充され、別個のドキュメントに移動しました。詳しくは、[オプトアウト管理](../../overview/data-security-and-privacy/opt-out-management.md).

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

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

顧客の Web サイトにアクセスする訪問者の IP アドレスは Adobe Data Processing Center（DPC）に転送され、同センターで保存される場合があります。訪問者のネットワーク設定によっては、IPアドレスが訪問者のコンピューターのIPアドレスを表しているとは限りません。例えば、この IP アドレスは、Network Address Translation（NAT）ファイアウォール、HTTP プロキシ、またはインターネットゲートウェイの外部 IP アドレスである可能性があります。

**IPの不明化方法:** Adobe Audience Managerでは、「プライバシーによるプライバシー」の原則に従って、すべての地理的地域または特定の国に対してグローバルにUIからのIPの不明化を有効にできます。この設定を有効にすると、IPアドレスの最後のオクテット（最後の部分）がAudience Managerに取り込まれたときに即座に破棄されます。Audience Managerは、処理前（オプションの地理的ルックアップまたはIPアドレスのログを含む）の前に、この部分のIPアドレスを破棄します。次に例を示します。

* マスク前： `255.255.255.255`
* マスク後： `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) to learn how to enable IP address obfuscation in the Audience Manager UI.

**地理的分類:** IPアドレスの不明化を有効にすると、そのIPアドレスの残りのオクテットは引き続き、Audience Managerの地域特性およびレポートに使用できます。IPアドレスの不明化を有効にしない場合、Audience Managerは完全なIPアドレスを使用します。地理的分類機能を使用すると、いずれかのケースで地域別にIPの場所を識別できますが、IPの不明化が使用されているときに若干正確な精度を保つことができます。IP アドレスの不明化をおこなうと、市レベルの情報の取得が著しく困難になる場合があります。地域および国レベルの情報の取得には、わずかな影響があります。地理的分類データは、市レベルまたは郵便番号レベルにのみ細分化され、個々のレベルには適用されません。[地域ターゲティング](/help/using/features/traits/trait-geotarget-keys.md) の詳細と、地理的な変数による特性の設定方法について説明します。

## 関連する概念 {#related-concepts}

* [オプトアウト管理](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [プライバシーとデータ保持の FAQ](/help/using/faq/faq-privacy.md)