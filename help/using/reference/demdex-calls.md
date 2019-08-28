---
description: Audience Manager および Experience Cloud ID サービスは demdex.net ドメインを呼び出し、そこからデータを受け取ります。アドビが見慣れないサードパーティドメインを扱っているように見えるかもしれませんが、そうではありません。この節では、demdex.net 呼び出しの構成要素について説明します。
seo-description: Audience Manager および Experience Cloud ID サービスは demdex.net ドメインを呼び出し、そこからデータを受け取ります。アドビが見慣れないサードパーティドメインを扱っているように見えるかもしれませんが、そうではありません。この節では、demdex.net 呼び出しの構成要素について説明します。
seo-title: demdex ドメインの呼び出しについて
solution: Audience Manager
title: demdex ドメインの呼び出しについて
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: ht
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# demdex ドメインの呼び出しについて{#understanding-calls-to-the-demdex-domain}

Audience Manager および Experience Cloud ID サービスは demdex.net ドメインを呼び出し、そこからデータを受け取ります。アドビが見慣れないサードパーティドメインを扱っているように見えるかもしれませんが、そうではありません。この節では、demdex.net 呼び出しの構成要素について説明します。

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 呼び出しの構成要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>これは、<span class="keyword">アドビ</span>が管理する従来のドメインです。<span class="keyword">Audience Manager</span> の買収前の名前（<span class="keyword">Demdex</span>）を反映したものです。<span class="keyword">アドビ</span>は 2011 年に <span class="keyword">Demdex</span> を買収し、<span class="keyword">Audience Manager</span> というブランド名に変更しました。このドメインは、<span class="keyword">Audience Manager</span>、<span class="wintitle">ID サービス</span>、アドビの既存のユーザーベースに密接に関連しているので、変更することは困難です。詳しくは、<a href="../overview/aam-overview.md#history-and-background">歴史と背景</a>を参照してください。 </p> <p>従来の <code>demdex.net</code> 呼び出しに他のプレフィックスが付いている場合があります（例：<code>dcs.demdex.net</code>、<code>fast.demdex.net</code> など）。プレフィックスにかかわらず、<code><i> something</i>.demdex.net</code> への呼び出しは常に<span class="keyword">アドビ</span>への呼び出しであり、不明な、または疑わしいサードパーティドメインへの呼び出しではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> は <span class="wintitle">Data Provider Match</span>（データプロバイダーマッチ）の略語です。これにより、<span class="keyword">Audience Manager</span> または <span class="wintitle">ID サービス</span>からの呼び出しで同期または ID 要求のために顧客データが渡されていることが、<span class="keyword">アドビ</span>の社内システムにわかります。これは、<code>Audience Manager</code> または <span class="keyword">ID サービス</span> からの <span class="wintitle">demdex.net</span> 呼び出しとして最も一般的なものです。 </p> <p><span class="wintitle">DPM 呼び出しの次の基本事項に留意してください。</span> </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b><span class="keyword">Audience Manager</span></b><span class="wintitle"></span>：<span class="keyword">Audience Manager</span> からの DPM 呼び出しでは、データを<span class="wintitle">データ収集サーバー</span>および<span class="wintitle">プロファイルキャッシュサーバー</span>に送信します。詳しくは、<a href="../reference/system-components/components-data-collection.md">データ収集コンポーネント</a>を参照してください。 </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b><span class="wintitle">ID サービス</span></b><span class="wintitle"></span>：<span class="wintitle">ID サービス</span>からの DPM 呼び出しは訪問者 ID の要求になります。詳しくは、<a href="https://marketing.adobe.com/resources/help/ja_JP/mcvid/mcvid_cookies.html" format="https" scope="external">Cookie と Experience Cloud ID サービス</a>および<a href="https://marketing.adobe.com/resources/help/ja_JP/mcvid/mcvid_id_request.html" format="https" scope="external">Experience Cloud ID サービスによる ID の要求と設定</a>を参照してください。 </li> 
     </ul> </p> <p> <p>注意：<span class="wintitle">ID サービス</span>のお客様はドメイン名の <span class="wintitle">DPM</span> プレフィックスを変更できます。詳しくは、<a href="https://marketing.adobe.com/resources/help/ja_JP/mcvid/mcvid-subdomain-config.html" format="https" scope="external">audienceManager Server and audienceManagerServerSecure </a>を参照してください。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Experience Cloud ID サービス](https://marketing.adobe.com/resources/help/ja_JP/mcvid/)
>* [Audience Manager の cookie](https://marketing.adobe.com/resources/help/ja_JP/whitepapers/cookies/cookies_am.html)

