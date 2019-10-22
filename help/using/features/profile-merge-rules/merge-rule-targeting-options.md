---
description: プロファイル結合ルールオプションを使用すると、オーディエンスを広げることも、ビジネスのニーズや目標に基づいて特定のオーディエンスに的を絞ることもできます。これらの一般的なユースケースでは、使用可能なオプションを使用して個人、団体、クロスデバイスのターゲティングに対応する結合ルールを作成する方法を調べています。
seo-description: プロファイル結合ルールオプションを使用すると、オーディエンスを広げることも、ビジネスのニーズや目標に基づいて特定のオーディエンスに的を絞ることもできます。これらの一般的なユースケースでは、使用可能なオプションを使用して個人、団体、クロスデバイスのターゲティングに対応する結合ルールを作成する方法を調べています。
seo-title: プロファイル結合ルールの一般的なユースケース
solution: Audience Manager
title: プロファイル結合ルールの一般的なユースケース
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: 532c69981ebc082bd411a9232e9ef207b59dace5

---


# プロファイル結合ルールの一般的なユースケース {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules]オプションを使用すると、オーディエンスを広げることも、ビジネスのニーズや目標に基づいて特定のオーディエンスに的を絞ることもできます。これらの一般的なユースケースでは、使用可能なオプションを使用して個人、団体、クロスデバイスのターゲティングに対応する結合ルールを作成する方法を調べています。[!UICONTROL Profile Merge Rules] リアルタイム宛先とバッチ宛先を操作します。

>[!TIP]
>
>これらの[!UICONTROL Merge Rule]設定の定義と説明については、[定義済みのプロファイルの結合ルールオプション](merge-rule-definitions.md)を参照してください。

## デバイスのターゲット設定 {#device-personalization}

このシナリオは、ユーザー認証を考慮せずに、デバイスID（DSP、オンサイトパーソナライゼーションプラットフォーム、その他のデバイスベースのターゲティングプラットフォーム）をサポートするターゲットプラットフォームを使用して、Audience Managerで定義したオーディエンスセグメントの単一のデバイスプロファイルを評価する場合に適用されます。

デバイスプロファイルのみをターゲットにするルールを作成する場合は、 **[!UICONTROL No Cross-Device Profile]** +を選択しま **[!UICONTROL Device Profile]**&#x200B;す。

![デバイスのみ](assets/device-only.png)

ジョンがスマートフォンを3つ持っているとします そのうち2つはデータプランAのiPhone 7で、うち1つはSamsung on Data Plan bです。3台のデバイスの認証状態を考慮せず、Johnの携帯電話会社は、データプランAで実行するiPhone 7デバイスに対してのみ、データプランのアップグレードを提供したいと考えています。

「+」ルールを使 **[!UICONTROL No Cross-Device Profile]** 用し、両方 **[!UICONTROL Device Profile]** がセグ [!DNL Device 1][!DNL Device 3] メントに適格ですが、「デバイス2」は無視されます。

![デバイスのみ](assets/device-management.png)

## 共有デバイスのターゲット設定 {#target-shared-devices}

ジョンと妻のジェーンが同じノートパソコンを使ってオンラインストアに行き、いろいろな商品を注文したとします。

ジョンは旅行券や特別取引の予約に自分の口座を使うが、ジェーンは音楽や映画の買い物に自分の口座を使う。

ストアのマーケティングチームは、 **[!UICONTROL Current Authenticated Profiles]** +ルールを使用して、認証されたアクティビティに基づいて、 **[!UICONTROL No Device Profile]** 特定の掘り出し物を持つJohnとJaneをターゲットに設定できます。

![電流装置なし](assets/current-no-device.png)

このルールを使用すると、Audience Managerは、デバイスプロファイルを完全に無視し、セグメントにJohnのCRM IDを修飾し、JaneのCRM IDを修飾しません。

![共有デバイスターゲティング](assets/shared-device-targeting.png)

## オンライン/オフラインのターゲット設定 {#device-household-targeting}

この使用例は、家庭のID管理に関するものです。 会社は、 **[!UICONTROL Last Authenticated Profiles]** +ルールを使用して、1つのデバイスプロファイルを、そのデバイスで最後に認証されたプロファイルと結合で **[!UICONTROL Device Profile]** きます。

![last-device-profile](assets/last-device-profile.png)

年収が100.000ドルを超える世帯で構成されるセグメントに、オンになるデバイスが少なくとも1つ含まれているとし [!DNL iPhone 7] ます [!DNL Data Plan B]。 2つの家庭プロファイル（デバイス間プロファイル）があり、それぞれが2つの異なるデバイスプロファイルに接続されています。 セグメントに適合するために必要な特性は、デバイスプロファイルとデバイスプロファイルに分散されます。

Audience Managerは、すべてのデバイスとデバイス間のプロファイルのペアを結合して、結合された特徴のセットがセグメントに適しているかどうかを確認します。 Audience Managerは、結合に含まれるすべてのプロファイルを評価するので、デバイスプロファイルと家庭用プロファイルの両方をセグメント化できます。

デバイスと世帯プロファイルの間のリンクにより、Audience Managerはセグメントに適格ですが、 [!DNL Household 2] 適格ではありません [!DNL Household 1]。 から、 [!DNL Household 2]セグメント [!DNL Device 3] にのみ該当します。 これに [!UICONTROL Profile Merge Rule] より、マーケターは個々のデバイス()や広範な家庭([!DNL Device 3][!DNL Household 2])に一貫したマーケティングメッセージを配信できるようになりました。

![家庭経営の](assets/household-management.png)

## 人ベースの宛先のターゲット設定 {#all-cross-device}

> [!IMPORTANT]
>
> この記事には、この機能の設定と使用方法を説明する製品ドキュメントが含まれています。法的なアドバイスは何も含まれません。法律に関するガイダンスについては、御社の顧問弁護士にアドバイスを求めてください。

このターゲット設定シナリオは、アドオンを購入した顧客のみが使 [!DNL People-Based Destinations] 用できます。 このルールを使用すると、マーケターは、自分の認証済みデータに基づいて顧客に連絡を取ることができます。

例えば、あるオンライン小売業者が、ソーシャルプラットフォームを通じて既存の顧客に連絡し、以前の注文に基づいてパーソナライズされたオファーを表示したいとします。 With [!UICONTROL People-Based Destinations], they can ingest hashed email addresses from their own [!DNL CRM] into Audience Manager, build segments from the offline data, and send these segments to the social platforms they want to advertise on, using that hashed identifier, optimizing their advertising spending.

このオプションの詳細については、「人ベースの [宛先」を参照してください](../destinations/people-based-destinations-overview.md)。

![オールクロスデバイス](assets/all-cross-device.png)

## デバイスグラフオプション {#device-graph-options}

[!UICONTROL Profile Merge]ルールの「[!UICONTROL device graph]」オプションの選択は、デジタルプロパティや事業目標に応じた条件によって異なります。ここで紹介する一般的なガイドラインは、どの種類のグラフをどのような場合に使用すればよいか判別するために便利です。これらのオプションを使用するには、[Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) メンバーであるか、外部デバイスグラフとの契約関係があることが必要です。以下の表は、デバイスグラフオプションをどのような場合に選択すればよいかを示しています。具体的なユースケースについては、[プロファイルリンクデバイスグラフのユースケース](profile-link-use-case.md)および[外部デバイスグラフのユースケース](external-graph-use-cases.md)を参照してください。

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> デバイスグラフタイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profile Link Device Graph</span> </p> </td> 
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

の使用例の概要については、以下のビデオをご覧くださ [!UICONTROL Profile Merge Rules]い。

>[!VIDEO](https://video.tv.adobe.com/v/28975/?captions=jpn)

>[!MORE_LIKE_THIS]
>
>* [プロファイルリンクデバイスグラフのユースケース](profile-link-use-case.md)
>* [ 外部デバイスグラフのユースケース](external-graph-use-cases.md)
>* [プロファイル結合ルール FAQ](../../faq/faq-profile-merge.md)

