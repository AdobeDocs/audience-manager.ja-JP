---
description: 消費者のプライバシーおよびオプトアウト手順に関連する一般に認められたベストプラクティスに対する Audience Manager の統合と準拠について説明します。
seo-description: 消費者のプライバシーおよびオプトアウト手順に関連する一般に認められたベストプラクティスに対する Audience Manager の統合と準拠について説明します。
seo-title: データのプライバシー
solution: Audience Manager
title: データのプライバシー
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

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

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**難読化方法：**[!DNL IP]「プライバシーバイデザイン」の原則に従い、Adobe Audience Manager では、すべての地域に対してグローバルに、または特定の国に対して、UI からの IP 難読化を有効にすることができます。When you enable this setting, the last octet (the last portion) of the [!DNL IP] address is immediately discarded when the [!DNL IP] address is ingested into Audience Manager. Audience Manager discards this part of the [!DNL IP] address prior to processing (including before any optional geographic lookup or logging of the [!DNL IP] address). 次に例を示します。

* マスク前： `255.255.255.255`
* マスク後： `255.255.255.0`

>[!NOTE]
>
>Audience Manager UI で アドレスを難読化する方法については、[IP アドレスの難読化](/help/using/features/administration/ip-obfuscation.md)をお読みください。[!DNL IP]

以下のビデオで、アドレスの不明化がAudience Managerでどのよ [!DNL IP] うに機能するかを確認してください。

[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=jpn)

**地理的分類：**[!DNL IP] アドレスの難読化を有効にした場合、その アドレスの残りのオクテットは引き続き、Audience Manager の地域特性およびレポートに使用できます。[!DNL IP]If you do not enable [!DNL IP] address obfuscation, Audience Manager uses the full [!DNL IP] address. You can use the Geographic Segmentation feature that allows you to identify an [!DNL IP] location by geographic area in either case, but with some slight loss of precision when [!DNL IP] obfuscation is being used. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. 地域レベルおよび国レベルの情報の取得に関しては、それほど大きな影響はありません。地理的セグメンテーションデータの精度は市区町村レベルまたは郵便番号レベルにとどまり、個人レベルにまでは及びません。[地域に基づくターゲティング](/help/using/features/traits/trait-geotarget-keys.md)と、地理的変数を使用した特性の設定方法についてお読みください。

## 関連する概念 {#related-concepts}

* [オプトアウト管理](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [プライバシーとデータ保持に関するよくある質問](/help/using/faq/faq-privacy.md)