---
description: データ収集サーバー（DCS）に渡すことができるデータの構文とサポートされている属性（キー値ペア）について説明します。この情報は、DCS リクエストの形式設定や DCS システムから返されるパラメーターの理解に役立ちます。
seo-description: データ収集サーバー（DCS）に渡すことができるデータの構文とサポートされている属性（キー値ペア）について説明します。この情報は、DCS リクエストの形式設定や DCS システムから返されるパラメーターの理解に役立ちます。
seo-title: DCS API 呼び出しでサポートされている属性
solution: Audience Manager
title: DCS API 呼び出しでサポートされている属性
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 100%

---


# [!DNL DCS] [!DNL API]呼び出しでサポートされている属性 {#supported-attributes-for-dcs-api-calls}

[!UICONTROL Data Collection Servers]（[!DNL DCS]）に渡すことができるデータの構文とサポートされている属性（キー値ペア）について説明します。この情報は、[!DNL DCS] リクエストの形式設定や DCS システムから返されるパラメーターの理解に役立ちます。

## 属性プレフィックス {#attribute-prefixes}

[!DNL DCS] では、キー値ペアのキーに付加されている特定のプレフィックスに基づいて、渡すデータのタイプを分類します。

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> キープレフィックス </th> 
   <th colname="col2" class="entry"> 対応するデータの種類 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>顧客定義属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> 属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP ヘッダーデータ。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>非公開の顧客定義属性。 </p> <p> DCS では、キーに <code> p_</code> プレフィックスが含まれていれば、お客様独自の非公開データを受信します。非公開データは特性評価に使用されますが、アドビのシステムにはログとして記録されず、保存もされません。例えば、<code> customers = p_age&lt;25</code> として定義されている特性があり、イベント呼び出しで <code> p_age=23</code> を渡すとしましょう。これらの条件を仮定すると、年齢に基づき絞り込まれたユーザーはこの特性に絞り込まれますが、このキー値ペアは、<span class="keyword">Audience Manager</span> にリクエストが受信された後で削除され、ログには記録されません。 </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_] 属性 {#d-attributes}

[!DNL DCS] からのレスポンスが必要でない限り、これらはすべてオプションです。[!DNL DCS] からのレスポンスが必要な場合は、`d_rtbd=json` が必須です。

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 属性 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_caller</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">DCS</span> API の呼び出しをおこなっている呼び出し元の特定に使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">DCS</span> レスポンスをコールバック関数の関数パラメーターとして使用して、実行する JavaScript 関数を指定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> で割り当てられたデータプロバイダー ID（<code> DPID</code>）とデータプロバイダーユーザー ID（<code> DPUUID</code>）のペアを 1 つ以上含んでいます。<code> DPID</code> と <code> DPUUID</code> のペアを複数使用する場合、各ペアを非印字文字 <code> %01</code> で区切ります。例：<code><i>DPID</i>%01<i>DPUUUID</i></code> </p> <p><code> d_cid</code> は、（廃止予定だが、まだサポートされている）<code> d_dpid</code> および <code> d_dpuuid</code> に代わるものです。詳しくは、<a href="../../../reference/cid.md">DPID と DPUUID に代わる CID</a> を参照してください。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>統合コードとそれに関連する一意のユーザー ID が単一のキー値ペアとして含まれています。 </p> <p><code> d_cid_ic</code> は、（廃止予定だが、まだサポートされている）<code> d_dpid</code> および <code> d_dpuuid</code> に代わるものです。詳しくは、<a href="../../../reference/cid.md">DPID と DPUUID に代わる CID</a> を参照してください。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>児童保護法に従うために、サードパーティ Cookie の使用を無効にします。このパラメーターは、アドビの Adobe Experience Platform ID サービスにより動的に設定されるもので、<code> idSyncDisable3rdPartySyncing</code> 設定に依存します。<a href="https://docs.adobe.com/content/help/ja-JP/id-service/using/reference/coppa.html" format="https" scope="external">Adobe Experience Platform ID サービスの COPPA のサポート</a>を参照してください。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>オプションです。お客様のご依頼に応じて有効になります。担当の Adobe Audience Manager コンサルタントまたはカスタマーケアにお問い合わせください。 </p> <p>特性とセグメントを <code> JSON</code> レスポンスに格納して返すように指定します。 </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> の場合は、セグメントの<a href="../../../reference/ids-in-aam.md">レガシーセグメント ID</a> を返します。 </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> の場合は、セグメントのセグメント ID を返します。 </p> </li>
     </ul> </p> <p>サンプルレスポンスは次のようになります。 </p> <p>
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>廃止されました。<code> d_cid</code> と <code> d_cid_ic</code> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>廃止されました。<code> d_cid</code> と <code> d_cid_ic</code> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>URL の宛先データを <code> JSON</code> レスポンスで返します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code>  は、Adobe Analytics と Audience Manager の統合用に確保されている属性です。 </p> <p>それらの属性を使用する特性は、作成しないようお勧めします。アドビは、確保している属性をいつでも変更できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>レスポンスで使用する <code> JSON</code> のバージョンを指定します。通常、これは <code> d_jsonv=1</code> に設定してください。<code> d_jsonv=0</code> に設定すると、ID の同期が無効になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Experience Cloud</span> ID サービスで設定および使用される Experience Cloud ID を指定します。ECID について詳しくは、<a href="https://docs.adobe.com/content/help/ja-JP/id-service/using/intro/cookies.html" format="https" scope="external">Cookie と Experience Cloud Identity Service</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>名前空間 ID です。使用されている JavaScript コンテナを示します。<span class="wintitle">DIL</span> での ID 同期に使用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Audience Manager でモバイルからのリクエストとデスクトップからのリクエストを区別できるようにします。次の値がサポートされています。 </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>廃止されました。<code> d_rs</code> は、<span class="keyword">Adobe Analytics</span> と <span class="keyword">Audience Manager</span> のレガシー統合用に確保されている属性です。 </p> <p>それらの属性を使用する特性は、作成しないようお勧めします。アドビは、確保している属性をいつでも変更できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">DCS</span> からの <code> JSON</code> レスポンスが必要な場合には必須です。 </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">これを省略すると、<span class="wintitle">DCS</span> はヘッダーでピクセルを返します。 </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">これを含めると、<span class="wintitle">DCS</span> はレスポンスの本文で <code> JSON</code> オブジェクトを返します。次の例を参照してください。実際のレスポンスはもっと複雑になります。 </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> は、<span class="term">スコア ID</span> を意味します。これは特性またはセグメントの一意の ID です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>特性評価用のデータソースを渡します。このデータソースに含まれている特性のみ評価されます。 </p> <p>例えば、以下の特性があるとしましょう。 </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120">次の仕様の<b>特性 T1</b>： </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">特性ルール：「<code> key1 == val1</code>」 </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">データソース（<a href="../../../reference/ids-in-aam.md">DPID</a>）：1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID 統合コード： ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601">次の仕様の<b>特性 T2</b>： </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">特性ルール：「<code> key2 == val2</code>」 </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">データソース（DPID）：2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID 統合コード： ic2 </li> 
     </ul> </p> <p>サンプル呼び出し <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code> では、特性 T1 のみ返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>目的は上記の <code> d_tdpid</code> パラメーターとまったく同じです。ただし、このパラメーターでは、データソースは統合コードを使用して渡されます。 </p> <p>引き続き上記の特性に対して、次のサンプル呼び出しを考えてみましょう。 </p> <p><code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code> の場合、特性 T2 のみ返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>一意のユーザー ID。この値が Cookie から得られない場合に、訪問者を特定します。 </p> </td> 
  </tr>
 </tbody>
</table>