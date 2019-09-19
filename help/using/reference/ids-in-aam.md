---
description: Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。
seo-title: Audience Manager で使用される ID の一覧
solution: Audience Manager
title: Audience Manager で使用される ID の一覧
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Audience Manager で使用される ID の一覧{#index-of-ids-in-audience-manager}

Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。

<table frame="all" id="table_6727BA8BBF2C40E48768126B4EC9984E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> 名前と説明 </th> 
   <th colname="col3" class="entry"> 例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>AAM UUID </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword">Audience Manager</span> の一意のユーザー ID</b> </p> <p> 数値型で 38 桁のデバイス ID。<span class="keyword">Audience Manager</span> はこの値を、操作するデバイスのそれぞれに関連付けます。Audience Manager UIで一意のユーザーのメンションが表示される場合は常に、この ID を考慮してください。<p><span class="keyword">Audience Manager</span> はこの ID を、「demdex.net」サードパーティドメインの Cookie として保存します。</p> </p> <p>Audience Manager UUID は、イベント呼び出しで d_uuid シグナルとして送信されます。 </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ImsOrgId </p> </td> 
   <td colname="col2"> <p> <b>組織 ID</b> </p> <p>会社が Experience Cloud にサインアップする際に生成される ID です。会社の組織 ID を検索する方法については、<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> 組織とアカウントのリンク</a>を確認し、組織 ID の検索までスクロールしてください。</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>パートナー ID</b> </p> <p> PID は、<span class="keyword">Audience Manager</span> での会社の ID です。<span class="keyword">Audience Manager</span> は imsOrgId を PID に関連付けます。 </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID、MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>Experience Cloud ID（ECID、レガシー略称 MID または MCID）は、組織 ID と <span class="keyword"> Audience Manager</span> の一意のユーザー ID から数学的に生成されます。これらの ID が変わらない限り、特定のユーザーに関する正しい ECID を生成できるかどうかは、単純に計算上の問題になります。同じ組織 ID と Audience Manager UUID があれば、いつでも同じ ECID 値が得られます。ECID について詳しくは、<a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies と Experience Cloud ID</a> のドキュメントを参照してください。 </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>特性 ID</b> </p> <p>特性 ID は、<span class="keyword"> Audience Manager</span> 環境内の特性を一意に識別します。ユーザーインターフェイス（UI）の各特性に特性 ID が割り当てられます。 </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>セグメント ID </b> </p> <p>セグメント ID は、<span class="keyword"> Audience Manager</span> 環境内のセグメントを一意に識別します。UI の各セグメントにセグメント ID が割り当てられます。 </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>csegID </p> </td> 
   <td colname="col2"> <p> <b>レガシーセグメント ID</b> </p> <p>この ID は、<span class="keyword"> Audience Manager</span> 環境内のセグメントを一意に識別します。UI の各セグメントにレガシーセグメント ID が割り当てられます。 </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>destID </p> </td> 
   <td colname="col2"> <p> <b>宛先 ID</b> </p> <p>宛先 ID は、<span class="keyword"> Audience Manager</span> 環境内の宛先を一意に識別します。UI の各宛先に ID が割り当てられます。 </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>データソース ID（データプロバイダー ID）</b> </p> <p>データソース ID は ID または特性の名前空間です。UI の各データソース（データプロバイダー）に ID が割り当てられます。 </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>データプロバイダー個別ユーザー ID</b><b>（CRM ID）</b> </p> <p>サードパーティ ID。CRM システムのエンドユーザーを識別するための ID です。DPUUID を <span class="keyword">Audience Manager</span> の UUID と同期したり、別の<span class="wintitle">データソース</span>（DPID）からの DPUUID を <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md">ID 同期プロセス</a>で同期したりできます。 </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM ID </p> </td> 
   <td colname="col2"> <p>上記の DPUUID を参照してください。 </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID、CID_IC </p> </td>
   <td colname="col2"> <p> <b>顧客 ID、顧客 ID 統合コード</b> </p> <p> <b>CID と CID_IC のキーと値のペアは<a href="../reference/cid.md">DPID と DPUUID</a> の代わりに使用されます。</b>これは DPID と DPUUID と同じ機能ですが、1 つのキーと値のペアにデータプロバイダー ID とユーザー ID（または統合コード）が含まれるので、より効率的です。 </p> </td> 
   <td colname="col3"> <p><code> 81841%013ad2948b1570a7e408a7cfb7ff4879e4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GAID </li>
      <li>RIDA</li>
      <li>MAID</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>Device Advertising ID</b> </p> <p>各ハードウェアデバイスに一意の ID で、広告目的で使用されます。通常は、デバイスの製造元またはデバイスのオペレーティングシステムにより設定されます。 </p> </td> 
   <td colname="col3"> <p>IDFA、GAID、Roku ID、Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>デバイス広告 ID - IDFA - iOS デバイス</b> </p> <p> <b>IDFA</b> ID はモバイルデバイス識別子で、デバイスの製造元により設定されます。この ID は iOS オペレーティングシステムを使用するデバイスを表します。 </p> </td> 
   <td colname="col3"> <p> 形式は厳密に 32 文字の<i>大文字</i>の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。 </p> <p><code> AEBE52E7-03EE-455A-B3C4-E57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>デバイス広告 ID - GAID - Android デバイス</b> </p> <p><b>GAID</b> ID はモバイルデバイス識別子で、デバイスの製造元により設定されます。この ID は Android オペレーティングシステムを使用するデバイスを表します。 </p> </td> 
   <td colname="col3"> <p>形式は厳密に 32 文字の<i>小文字</i>の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。 </p> <p> <code> e4fe9bde-caa0-47b6-908d-ffba3fa184f2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Roku ストリーミングデバイス</b> </p> <p><b>GAID</b> RIDA ID はストリーミングデバイス識別子で、Roku デバイスの製造元より設定されます。</p> </td>
   <td colname="col3"> <p>形式は厳密に 32 文字の<i>小文字</i>の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。 </p> <p> <code> fcb2a29c-315a-5e6b-bcfd-d889ba19aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Microsoft Advertising ID - MAID - Windows 10 デバイス</b> </p> <p><b>MAID</b> ID は、デバイスごと、ユーザーごとに Windows 10 で生成されるデバイス識別子です。</p> </td>
   <td colname="col3"> <p>MAID は英数字の形式です。</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Samsung デバイス</b> </p> Samsung DUID は、Samsung TV より設定されるデバイス識別子です。</p> </td>
   <td colname="col3"> <p>Samsung DUID は英数字の形式です。</p></td>
  </tr>
 </tbody> 
</table>