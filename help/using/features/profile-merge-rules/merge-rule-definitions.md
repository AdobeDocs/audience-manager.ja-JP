---
description: 結合ルールオプションを使用すると、Audience Manager がセグメント化に使用するデータのタイプを制御できます。結合ルールには、プロファイルリンクデバイスグラフ、Adobe Experience Cloud Device Co-op、または Audience Manager と統合しているその他のサードパーティデバイスグラフプロバイダーによってマッピングされたデバイスプロファイルを含めることができます。プロファイル結合ルールは最大で 4 つ作成できます。
seo-description: 結合ルールオプションを使用すると、Audience Manager がセグメント化に使用するデータのタイプを制御できます。結合ルールには、プロファイルリンクデバイスグラフ、Adobe Experience Cloud Device Co-op、または Audience Manager と統合しているその他のサードパーティデバイスグラフプロバイダーによってマッピングされたデバイスプロファイルを含めることができます。プロファイル結合ルールは最大で 4 つ作成できます。
seo-title: 定義済みのプロファイルの結合ルールオプション
solution: Audience Manager
title: 定義済みのプロファイルの結合ルールオプション
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: e8729366a62ec82aa906fe043cf594bff837c737

---


# 定義済みのプロファイルの結合ルールオプション {#profile-merge-rule-options-defined}

結合ルールオプションを使用すると、Audience Manager がセグメント化に使用するデータのタイプを制御できます。結合ルールには、[!UICONTROL Profile Link] デバイスグラフ、[!UICONTROL Adobe Experience Cloud Device Co-op]、および Audience Manager と統合しているその他のサードパーティデバイスグラフプロバイダーによってマッピングされたデバイスプロファイルを含めることができます。最大4 つの[!UICONTROL Profile Merge Rules]を作成できます。4 つ目の [!UICONTROL Profile Merge Rule] は、[!UICONTROL People-Based Destinations] アドオンを購入した顧客のみが利用できます。

[!UICONTROL Profile Merge Rule Setup] で、以下のオプションから選択し、[!UICONTROL Profile Merge Rule] を構築します。

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## プロファイルの結合ルールオプションの概要 {#overview}

プロファイル結合ルールでは、特定の使用例に合わせて様々なルールの組み合わせを使用できます。それぞれのルールの組み合わせを使用するタイミングについて詳しくは、次の表を参照してください。

| クロスデバイス対応オプション | デバイスオプション | 使用可否 | 評価タイプ | オーディエンスラボのサポート | ユースケース |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| クロスデバイス対応プロファイルなし | デバイスプロファイル | すべての顧客 | リアルタイムとバッチ | ○ | [デバイスのターゲティング](merge-rule-targeting-options.md#device-personalization) |
| クロスデバイス対応プロファイルなし | 外部デバイスグラフ（Co-op デバイスグラフを含む） | すべての顧客 | リアルタイムとバッチ | × | [デバイスのターゲティングの拡張](external-graph-use-cases.md#audience-expansion) |
| 現在の認証済みプロファイル | デバイスプロファイルなし | すべての顧客 | リアルタイムのみ | × | [共有デバイスのターゲティング](merge-rule-targeting-options.md#target-shared-devices) |
| 最後に認証されたプロファイル | デバイスプロファイル | すべての顧客 | リアルタイムとバッチ | ○ | [オンライン／オフラインでのターゲティング](merge-rule-targeting-options.md#device-household-targeting) |
| 最後に認証されたプロファイル | プロファイルリンクデバイスグラフ | すべての顧客 | リアルタイムとバッチ | ○ | [クロスデバイスでのターゲティング](profile-link-use-case.md#cross-device-personalization) |
| 最後に認証されたプロファイル | 外部デバイスグラフ（Co-op デバイスグラフを含む） | すべての顧客 | リアルタイムとバッチ | × | [高度なクロスデバイスターゲティング](external-graph-use-cases.md#advanced-graph-expansion) |
| すべてのクロスデバイス対応プロファイル | なし | [People-Based Destinations](../destinations/people-based-destinations-overview.md) のユーザー専用 | バッチのみ | × | [People-Based Destinations のターゲティング](merge-rule-targeting-options.md#all-cross-device) |

## プロファイル結合ルールセグメントの評価 {#segment-evaluation}

[!UICONTROL Profile Merge Rules] 設定に応じて、Audience Manager はリアルタイム、バッチまたはその両方でセグメント評価を実行できます。

* リアルタイムセグメント評価では、セグメントに認定するため、[!DNL DCS] は訪問者がデジタルプロパティにリアルタイムでアクセスしたことを確認する必要があります。
* バッチセグメント評価は、以前に認定された特性に対して実行されます。
* [!UICONTROL Profile Merge Rules] は、リアルタイムセグメント評価とバッチセグメント評価の両方をサポートし、リアルタイム訪問者アクティビティと以前に認定された特性を組み合わせます。

## プロファイル結合ルールレポートの遅延 {#reporting-latency}

リアルタイムのセグメント評価は、[!UICONTROL Profile Merge Rules] レポートに即座に反映されます。

バッチセグメントの評価は、[プロファイル結合ルールレポート](profile-link-metrics.md)に反映されるまでに最大 24 時間かかる場合があります。

## クロスデバイス対応オプション {#auth-options}

[!UICONTROL Cross-Device Options] を使用すると、未認証ユーザーと認証済みユーザーを選択し、クロスデバイスプロファイルをセグメント化に利用することができます。これらのオプションにより、共有デバイスで特定のユーザーを識別してそのユーザーにリーチすることができます。匿名ユーザーと認証済みユーザーについて詳しくは、[Audience Manager での訪問者認証の状態](../../reference/visitor-authentication-states.md)を参照してください。

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> クロスデバイス対応オプション </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">クロスデバイス対応プロファイルなし</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> が認証済みユーザーから収集したデータを使用ないよう設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">現在の認証済みプロファイル</span></b> </p> </td> 
   <td colname="col2"> <p>訪問者がサイトにログインした場合に <span class="keyword">Audience Manager</span> が認証済みプロファイルでデータの読み取りと書き込みをおこなうよう設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">最後に認証されたプロファイル</span></b> </p> </td> 
   <td colname="col2"> <p>デバイスに最後にログインしたユーザーの認証済みプロファイルから <span class="keyword">Audience Manager</span> がデータを読み取るよう設定します。 </p> <p>このオプションを選択すると、<span class="keyword">Audience Manager</span> はユーザーが匿名ユーザーの場合に新しい特性データを認証済みプロファイルに書き込みません。認証時に、新しい特性データがユーザーの認証済みプロファイルに書き込まれます。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">すべてのクロスデバイス対応プロファイル</span></b> </p> </td> 
   <td colname="col2"> <p>認証状態に関係なく、すべてのクロスデバイス対応プロファイルからデータを読み取るよう Audience Manager に伝えます。このオプションは、People-Based Destinations アドオンを購入した Audience Manager ユーザーのみが使用できます。</p> </td>
  </tr>
 </tbody>
</table>

## クロスデバイス対応プロファイルオプション {#profile-options}

[!UICONTROL Cross-Device Profile Options]には、クロスデバイス対応データソースが一覧表示されます。これらのオプションは、クロスデバイス対応データソースの作成時に提供した名前を使用します（[クロスデバイス対応データソース](merge-rules-start.md#create-data-source)を参照）。各プロファイルルールで使用するクロスデバイス対応データソースは最大 3 つ選択できます。[!UICONTROL Authenticated Profile Options]は、**[!UICONTROL Current Authenticated Profiles]**&#x200B;または&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;を選択したときに使用できます。

## デバイスオプション {#device-options}

[!UICONTROL Device Options]では、*`device profile`*&#x200B;で使用する [!UICONTROL Profile Merge Rule] のタイプを選択できます。デバイスプロファイルは、匿名の閲覧アクティビティから収集された特性を使用して作成されます。プロファイル結合ルールには少なくとも、1 つの認証済みオプションと 1 つのデバイスオプションが含まれます。

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> デバイスオプション </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> No Device Profile</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> が匿名プロファイルに含まれる特性をセグメント化に使用しないよう設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">デバイスプロファイル</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> が匿名デバイスプロファイルをセグメント化に使用するよう設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profile Link Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> が、現在のデバイスに加え、ユーザーが最後に認証を受けた他の 100 台までのデバイスからプロファイルを読み取るよう指示します。このデバイスグラフは、<span class="keyword">Audience Manager</span> で独自のファーストパーティデータに対して構築されます。デジタルプロパティにまたがって高度な認証を使用している顧客に最適です。<span class="wintitle">プロファイルリンク</span>デバイスグラフはリアルタイムで更新されます。このオプションは、「<b><span class="uicontrol">Current Authenticated Profile</span></b>」または「<b><span class="uicontrol">Last Authenticated Profile</span></b>」を選択した場合に使用できます。このオプションを使用する場合は、認証済みのプロファイルを 1 つだけ選択できます（その他は <span class="keyword">Audience Manager</span> により自動的にグレー表示されます）。<a href="profile-link-use-case.md">プロファイルリンクデバイスグラフのユースケース</a>も参照してください。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager </span>に対し、<a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a> が提供するリンクを使用して、現在のデバイスおよび他の 100 台までのデバイスからプロファイルを読み取るように指示します。 </p> <p><span class="keyword">Device Co-op</span> は、参加するお客様がデバイスリンク情報を共有するデジタル協業です。<span class="keyword">Device Co-op</span> はこのデータを<span class="term">デバイスグラフ</span>で処理します。デバイスグラフは、デバイスをリンクし、デバイスクラスターを形成します。このリンクは<a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external">確率論的データと決定論的データ</a>から構築されます。クラスターは、1 人の匿名の人物によって使用されるデバイスのグループを表します。<span class="keyword">Device Co-op</span> は、メンバー間でこれらのクラスターを共有します。これにより、メンバーは、価値のある一貫したクロスデバイスエクスペリエンスをその顧客に提供できます。 </p> <p> <span class="wintitle">Device Co-op</span> について詳しくは、以下を参照してください。 </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/ja-JP/device-co-op/using/home.html" format="https" scope="external"> Device Co-op の概要</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> メンバーシップ要件</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> デバイスグラフ：内部処理と出力</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>サードパーティデバイスグラフオプション</b>（個人と世帯） </p> </td>
   <td colname="col2"> <p>これらのオプションを使用すると、サードパーティベンダーによるデバイスグラフテクノロジーに基づいて結合ルールを構築できます。サードパーティデバイスグラフから、以下の情報が得られます。 </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 確率論的データと決定論的データ。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">個人レベルまたは世帯レベルでのデータ。 </li> 
     </ul> </p> <p>これらのオプションを使用するには、<span class="keyword">Audience Manager</span> と統合しているデバイスグラフプロバイダーの顧客でなければなりません。詳細情報や基本情報については、アカウントマネージャーにお問い合わせください。 </p> </td>
  </tr>
 </tbody>
</table>

## 外部結合ポリシー {#external-merge-policies}

他の Experience Cloud ソリューションから自動的に作成されたオーディエンスセグメントは、Audience Manager の外部で定義された結合ルールに基づいて、[!UICONTROL External Merge Policy] を使用しているとしてマークされます。例えば、[Audience Manager と Adobe Experience Platform の間でのオーディエンスの共有](../../integration/integration-aep/aam-aep-audience-sharing.md)を参照してください。

>[!MORELIKETHIS]
>
>* [プロファイル結合ルール FAQ](../../faq/faq-profile-merge.md)

