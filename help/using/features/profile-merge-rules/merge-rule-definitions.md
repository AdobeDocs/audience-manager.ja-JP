---
description: 結合ルールオプションを使用すると、Audience Manager がセグメント化に使用するデータのタイプを制御できます。結合ルールには、プロファイルリンクデバイスグラフ、Adobe Experience Cloud Device Co-op、または Audience Manager と統合しているその他のサードパーティデバイスグラフプロバイダーによってマッピングされたデバイスプロファイルを含めることができます。プロファイル結合ルールは最大で 3 つ作成できます。
seo-description: 結合ルールオプションを使用すると、Audience Manager がセグメント化に使用するデータのタイプを制御できます。結合ルールには、プロファイルリンクデバイスグラフ、Adobe Experience Cloud Device Co-op、または Audience Manager と統合しているその他のサードパーティデバイスグラフプロバイダーによってマッピングされたデバイスプロファイルを含めることができます。プロファイル結合ルールは最大で 3 つ作成できます。
seo-title: 定義済みのプロファイルの結合ルールオプション
solution: Audience Manager
title: 定義済みのプロファイルの結合ルールオプション
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 定義済みのプロファイルの結合ルールオプション{#profile-merge-rule-options-defined}

結合ルールオプションを使用すると、Audience Manager がセグメント化に使用するデータのタイプを制御できます。A merge rule can include device profiles mapped by the [!UICONTROL Profile Link] device graph, the [!UICONTROL Adobe Experience Cloud Device Co-op], and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 3 [!UICONTROL Profile Merge Rules].

You build a [!UICONTROL Profile Merge Rule] by making a selection from these options:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> 認証済みオプション</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> 認証済みプロファイルオプション</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> デバイスオプション</a> </li>
</ul>

## 認証済みオプション {#auth-options}

[!UICONTROL Authenticated Options] 認証解除および認証されたユーザーを選択して、セグメント化用のデバイス間プロファイルを活用できます。これらのオプションにより、共有デバイスで特定のユーザーを識別してそのユーザーにリーチすることができます。匿名ユーザーと認証済みユーザーについて詳しくは、[Audience Manager での訪問者の認証状態](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 認証済みオプション </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> No Authenticated Profile</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> が認証済みユーザーから収集したデータを使用ないよう設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Current Authenticated Profile</span></b> </p> </td> 
   <td colname="col2"> <p>訪問者がサイトにログインした場合に <span class="keyword">Audience Manager</span> が認証済みプロファイルでデータの読み取りと書き込みをおこなうよう設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Last Authenticated Profile</span></b> </p> </td> 
   <td colname="col2"> <p>デバイスに最後にログインしたユーザーの認証済みプロファイルから <span class="keyword">Audience Manager</span> がデータを読み取るよう設定します。 </p> <p>このオプションを選択すると、<span class="keyword">Audience Manager</span> はユーザーが匿名ユーザーの場合に新しい特性データを認証済みプロファイルに書き込みません。認証時に、新しい特性データがユーザーの認証済みプロファイルに書き込まれます。 </p> </td>
  </tr> 
 </tbody>
</table>

## 認証済みプロファイルオプション {#profile-options}

The [!UICONTROL Authenticated Profile Options] lists your cross-device data sources. These options use the names you provided when you created a cross-device data source (see [Create a Cross-Device Data Source](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)). 各プロファイルルールで使用するデバイス間データソースは最大 3 つ選択できます。The [!UICONTROL Authenticated Profile Options] are available when you choose **[!UICONTROL Current Authenticated Profile]** or **[!UICONTROL Last Authenticated Profile]**.

## デバイスオプション {#device-options}

[!UICONTROL Device Options] では、使用するタイプを選択 *`device profile`*[!UICONTROL Profile Merge Rule]できます。デバイスプロファイルは、ユーザーが匿名で Web を閲覧している際に収集した特性で構成されます。プロファイル結合ルールには少なくとも、1 つの認証済みオプションと 1 つのデバイスオプションが含まれます。

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
   <td colname="col1"> <p> <b><span class="uicontrol"> Current Device Profile</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> が匿名デバイスプロファイルをセグメント化に使用するよう設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profile Link Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> が、現在のデバイスと、ユーザーが最後に認証を受けた 3 件のデバイスからプロファイルを読み取るよう設定します。このデバイスグラフは、<span class="keyword">Audience Manager</span> で独自のファーストパーティデータに対して構築されます。デジタルプロパティにまたがって高度な認証を使用している顧客に最適です。<span class="wintitle">プロファイルリンク</span>デバイスグラフはリアルタイムで更新されます。This option is available when you select <b><span class="uicontrol"> Current Authenticated Profile</span></b> or <b><span class="uicontrol"> Last Authenticated Profile</span></b>. このオプションを使用する場合は、認証済みのプロファイルを 1 つだけ選択できます（その他は <span class="keyword">Audience Manager</span> により自動的にグレー表示されます）。<a href="../../features/profile-merge-rules/profile-link-use-case.md">プロファイルリンクデバイスグラフのユースケース</a>も参照してください。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> が <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external">Experience Cloud Device Co-op</a> によって提供されたリンクを使用してデバイスプロファイルを結合するよう設定します。 </p> <p><span class="keyword">Device Co-op</span> は、参加するお客様がデバイスリンク情報を共有するデジタル協業です。<span class="keyword">Device Co-op</span> はこのデータを<span class="term">デバイスグラフ</span>で処理します。デバイスグラフは、デバイスをリンクし、デバイスクラスターを形成します。このリンクは<a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external">確率論的データと決定論的データ</a>から構築されます。クラスターは、1 人の匿名の人物によって使用されるデバイスのグループを表します。<span class="keyword">Device Co-op</span> は、メンバー間でこれらのクラスターを共有します。これにより、メンバーは、価値のある一貫したデバイス間エクスペリエンスをその顧客に提供できます。 </p> <p> <span class="wintitle">Device Co-op</span> について詳しくは、以下を参照してください。 </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Device Co-op の概要</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> メンバーシップ要件</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> デバイスグラフ：内部処理と出力</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external">Audience Manager と外部デバイスグラフ</a>（PDF ダウンロード） </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>サードパーティデバイスグラフオプション</b>（個人と世帯） </p> </td>
   <td colname="col2"> <p>これらのオプションを使用すると、サードパーティベンダーによるデバイスグラフテクノロジーに基づいて結合ルールを構築できます。サードパーティデバイスグラフから、以下の情報が得られます。 </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 確率論的データと決定論的データ。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">個人レベルまたは世帯レベルでのデータ。 </li> 
     </ul> </p> <p>これらのオプションを使用するには、<span class="keyword">Audience Manager</span> と統合しているデバイスグラフプロバイダーの顧客でなければなりません。詳細情報や基本情報については、アカウントマネージャーにお問い合わせください。 </p> <p>詳細については、&lt; a href="../../ features/profile- merge- rules/external- graph- usage- case. md）. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_LIKE_THIS]
>
>* [プロファイル結合ルール FAQ](../../faq/faq-profile-merge.md)

