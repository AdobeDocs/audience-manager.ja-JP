---
description: プロファイル結合ルールオプションを使用すると、オーディエンスを広げることも、ビジネスのニーズや目標に基づいて特定のオーディエンスに的を絞ることもできます。これらの一般的なユースケースでは、使用可能なオプションを使用して個人、団体、クロスデバイスのターゲット設定に対応する結合ルールを作成する方法を調べています。現時点では、プロファイル結合ルールはリアルタイムの宛先でのみ機能します。
seo-description: プロファイル結合ルールオプションを使用すると、オーディエンスを広げることも、ビジネスのニーズや目標に基づいて特定のオーディエンスに的を絞ることもできます。これらの一般的なユースケースでは、使用可能なオプションを使用して個人、団体、クロスデバイスのターゲット設定に対応する結合ルールを作成する方法を調べています。現時点では、プロファイル結合ルールはリアルタイムの宛先でのみ機能します。
seo-title: プロファイル結合ルールの一般的なユースケース
solution: Audience Manager
title: プロファイル結合ルールの一般的なユースケース
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# プロファイル結合ルールの一般的なユースケース {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] オプションを使用すると、ビジネスニーズや目標に基づいて、オーディエンスの焦点を特定のオーディエンスに拡大または制限できます。これらの一般的なユースケースでは、使用可能なオプションを使用して個人、団体、クロスデバイスのターゲット設定に対応する結合ルールを作成する方法を調べています。Currently, [!UICONTROL Profile Merge Rules] work with real-time destinations only.

![](assets/merge-rules-options.png)

>[!TIP]
>
>For definitions and descriptions of these [!UICONTROL Merge Rule] settings, see [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

## Focused targeting {#focused-targeting}

Web サイトでユーザー認証をおこなうと、[!DNL Audience Manager] に対する宣言済み ID の呼び出しが実行されます。このイベントの後、[!DNL Audience Manager] は認証済みプロファイルで特性データの書き込み（およびデータの読み取り）をおこないます。[!DNL Audience Manager] では、認証済みプロファイルにより次のことができます。

* 特定のユーザーに該当する認証済みプロファイルに特性を書き込む。
* セグメント化のため複数のデバイスユーザーを識別し、区別する。

### 認証済みユーザーへのリーチ

認証されたプロファイルオプションを使用すると、オフライン属性に基づいてWebサイトまたはアプリにログオンしているユーザーをターゲットにするルールを作成できます。例えば、金融サービス会社はこのオプションを使用して、ターゲットクレジットカードのアップグレードオファーや、利益またはオフラインアクティビティに基づく特別なサービスオファーをターゲット化したユーザーをターゲット化します。また、航空会社は獲得マイル数に基づいて、オファーの対象となる認証済みフリークエントフライヤーをターゲット設定します。

To create a rule that reaches only authenticated users, select **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. このオプションは、認証されたプロファイルデータのみを使用してセグメントを評価します。このルールでは、匿名デバイスプロファイルのデータは無視されます。

To also include data in the anonymous device profile, use the **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** rule.

### 以前の認証状態に基づきユーザーにリーチ

これらのオプションを使用すると、閲覧中ではあってもログオンしていない特定のユーザーにリーチします。この操作は、ユーザーレベルの推定ターゲット設定に依存するオプションを使用しておこなうことができます。推定ターゲット設定により、サイトで明確に認証されていなくてもオンラインで閲覧中である人にリーチすることができます。この方式では、最後に認証されたプロファイルでデータの読み取りを実行します（書き込みはおこないません）。また、認証済みプロファイルをクリーンな状態にしておくために、[!DNL Audience Manager] は新しい特性認定を、認証済みプロファイルではなくデバイスプロファイルに書き込みます。例えば、サイトやアプリにログオンしていない既存ユーザーに対して、各種のオファーをテストしようとしているマーケターがいるとします。マーケターはこれらの広告を、現在の未認証顧客に対してテストして、どのオファーで多くの応答を得られるかテストすることができます。

次に、事前認証に基づいてユーザーに到達するルールの例を示します。

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Expanded targeting {#expanded-targeting}

特定の顧客にリーチするためのルールに加えて、ターゲット設定に使用するデータセットを拡大するためのルールもマーケターには必要です。[!UICONTROL Profile Merge Rules] デバイスプロファイルオプションを使用してこれを実行できます。デバイスオプションは、ユーザーが1つまたは複数のデバイスで匿名状態になったときに認識される特性に基づいて描画されるので、セグメント化に適格なデータセットを拡張します。これは、家庭デバイスグラフを使用して、または家庭のすべてのデバイスを使用して、デバイスのすべてのデバイスでユーザーに到達する場合に便利です。このオプションの使用例としては、家族の休暇オファーを含めることができます。この場合、任意のデバイスのユーザーがオファーに関心を示している場合、そのオファーを含むすべてのデバイスにリーチします。

To create a rule that expands the targeting data set, select the **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** rule.

<!-- 

<p>Rules that use the device graph option extend your data set even further. With the device graph option, <span class="keyword"> Audience Manager</span> relies on the device profiles aggregated from the last 3 devices that a visitor used for authentication to your site. The device graph rules include: </p> 
<p> 
 <ul id="ul_3008B6AF16EC408F98EC4088111281FB"> 
  <li id="li_FA2087F1ED454CD0B9E09656B79ED23B"> <b><span class="uicontrol"> Current Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
  <li id="li_001A8DB517CB4EE394DBD530F2080FD5"> <b><span class="uicontrol"> Last Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
 </ul> </p> 
<p> 
 <note type="tip">
  Create a simple rule with 
  <b><span class="uicontrol"> No Authenticated Profile</span></b> + 
  <b><span class="uicontrol"> Current Device Profile</span></b> when you're still developing a strategy and are unsure about which options to choose or if your site doesn't use authentication. 
 </note> </p>

 -->

## デバイスグラフオプション {#device-graph-options}

Choosing a [!UICONTROL device graph] option for a [!UICONTROL Profile Merge] rule depends on conditions unique to your digital properties and business goals. ここで紹介する一般的なガイドラインは、どの種類のグラフをどのような場合に使用すればよいか判別するために便利です。これらのオプションを使用するには、[!DNL Adobe Experience Cloud Device Co-op] メンバーであるか、外部デバイスグラフとの契約関係があることが必要です。以下の表は、デバイスグラフオプションをどのような場合に選択すればよいかを示しています。具体的なユースケースについては、[プロファイルリンクデバイスグラフのユースケース](../../features/profile-merge-rules/profile-link-use-case.md)および[外部デバイスグラフのユースケース](../../features/profile-merge-rules/external-graph-use-cases.md)を参照してください。

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> デバイスグラフタイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profile Link</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">プロファイルリンク</span>オプションで作成された<span class="wintitle">プロファイル結合</span>ルールは、次の場合に最適です。 </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">高レベルなユーザー認証を導入しているデジタルプロパティ。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">集中的な低リーチのキャンペーン。<span class="wintitle">プロファイルリンク</span>デバイスグラフは、決定論的データについてのみ構築されます。このデバイスプロファイルのプールは、必ず未認証のユーザーとデバイスのプールより小さくなります。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">ユーザーがセグメント化認定のため未認証状態でなければならない場合。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部デバイスグラフオプション </p> </td> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external">Experience Cloud Device Co-op</a> や、<span class="keyword">Audience Manager</span> と統合された外部デバイスグラフで作成された<span class="wintitle">プロファイル結合</span>ルールは、次のものに最適です。 </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">低レベルなユーザー認証を導入しているデジタルプロパティ。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">広範囲で高リーチのブランドキャンペーン。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">ユーザーがセグメント化認定のために未認証状態である必要がない場合。 </li> 
     </ul> </p> <p> <p>ヒント：低レベルの認証を使用していて、デバイスグラフプロバイダーとは関係がない <span class="keyword">Experience Cloud</span> ユーザーには、<span class="keyword">Device Co-op</span> が最適です。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [プロファイルリンクデバイスグラフのユースケース](../../features/profile-merge-rules/profile-link-use-case.md)
>* [ 外部デバイスグラフのユースケース](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [プロファイル結合ルール FAQ](../../faq/faq-profile-merge.md)

