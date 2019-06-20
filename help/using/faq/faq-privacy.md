---
description: プライバシーやデータに関してよくある質問や問題に対する回答。
seo-description: プライバシーやデータに関してよくある質問や問題に対する回答。
seo-title: プライバシーとデータ保持の FAQ
solution: Audience Manager
title: プライバシーとデータ保持の FAQ
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# プライバシーとデータ保持の FAQ{#privacy-and-data-retention-faq}

プライバシーやデータに関してよくある質問や問題に対する回答。

<!-- faq_privacy.xml -->

## プライバシーの FAQ {#privacy-faq}

>[!TIP]
>
>Visit the [Adobe Privacy Center](https://www.adobe.com/privacy.html) for more information.

**Audience Manager では Cookie をどのように使用し、どのような Cookie を設定しますか？**

詳しくは、[Audience Manager の Cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) を参照してください。

**米国の Audience Manager クライアントは EU 資産のユーザーをターゲットにすることができますか？**

はい。Audience Manager は、国際的な資産を持つクライアントと協力しています。EU には厳しいプライバシー法がありますが、Audience Manager では、ヨーロッパでファーストパーティデータをオーディエンスターゲティングに使用するクライアントを備えています。Audience Manager では、EU オーディエンスへのターゲティングをサポートできますが、現地のプライバシー規制法の遵守は当事者の責任においておこなう必要があります。

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## データ保持の FAQ {#data-retention-faq}

様々なデータタイプとストレージシステムについての保持期間を次の表に示します。

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> データタイプ、ソース、ストレージ </th> 
   <th colname="col2" class="entry"> データ保持期間 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>バックエンドサーバー </p> </td> 
   <td colname="col2"> <p>120 日 </p> <p> Audience Manager では、Audience Manager プラットフォームでユーザーを最後に確認してから 120 日後にユーザーデータをバックエンドサーバーから削除します。<span class="keyword">Audience Manager</span> がこの 120 日間にユーザーアクティビティを記録した場合は、次の 120 日間もデータを保管します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>エッジサーバー </p> </td> 
   <td colname="col2"> <p> 14 日 </p> <p>Audience Manager では、Audience Manager プラットフォームでユーザーを最後に確認してから 14 日後にユーザーデータをエッジエンドサーバーから削除します。<span class="keyword">Audience Manager</span> がこの 14 日間にユーザーアクティビティを記録した場合は、次の 14 日間もデータを保管します。14 日間経過後にユーザーが再びアクティブになった場合、最初の新規ページ表示時とユーザーが実行可能になるときの間には、遅延が発生します。アクティビティがない状態が 14 日間を超えて続いた場合は、完全なプロファイルをエッジセンターに戻すのに 6～18 時間かかります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>生のログ </p> </td> 
   <td colname="col2"> <p>180 日間（180 日間アクティビティがなかったら、その後削除） </p> <p>生のログは、HTTP 呼び出しを通じて、または <span class="keyword">Audience Manager</span> に送信されたオンボードファイルからエッジサーバーで受信されるデータです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>広告サーバーログ </p> </td> 
   <td colname="col2"> <p><b>レポート</b> </p> <p>ログファイルは、最大 30 日間、レポート目的で保持されます。不一致ログ（訪問者の広告サーバー ID と <span class="keyword">Audience Manager</span> ID の間に ID 同期がないログ）は、アドビのバックエンドストレージには永続的に保存されません。また、<span class="keyword">Amazon S3</span> に格納されている一致ログは最大 30 日間保持されます。 </p> <p><b>実用的なログファイル</b> </p> <p>一致ログも不一致ログも最大 30 日間、保持されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM レベルのプロファイル（認証済みプロファイル） </p> </td> 
   <td colname="col2"> <p>非アクティブなCRMレベルのプロファイル（顧客ID）のデフォルトの有効期間（TTL）間隔は24ヶ月です。ただし、Audience Manager UIを使用して、1か月から5年間の非アクティブなCRMレベルのプロファイルのTTL間隔を増減できます。これは、クロスデバイスデータソースを作成または編集するときに実行できます。</p> <p>For more information, see Data Source Settings in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>モバイルデバイス ID </p> </td> 
   <td colname="col2"> <p>モバイルデバイス ID（<a href="../reference/ids-in-aam.md">IDFA、GAID</a>）の保持条件は、最初の 2 行（バックエンドサーバーとエッジサーバー）で説明したサイクルに従います。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>顧客データフィード（CDF） </p> </td> 
   <td colname="col2"> <p>CDF ファイルには、<span class="keyword">Audience Manager</span> イベント呼び出し（/event）でサーバーに送信されるデータと同じものが含まれています。保持期間は 8 日です。CDF について詳しくは、<a href="../features/cdf-files.md">CDF の概要</a>および <a href="../faq/faq-cdf.md">CDF の FAQ</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>同期済み ID 間のマッピング </p> </td> 
   <td colname="col2"> <p>Mappings between synchronized IDs may be kept for the life of the associated <a href="../reference/ids-in-aam.md"> Audience Manager Unique User ID (AAM UUID)</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>インバウンドデータ </p> </td> 
   <td colname="col2"> <p>これは、FTP で <span class="keyword">Audience Manager</span> に送信される受信データ、または Amazon S3 ディレクトリに直接送信される受信データです。<span class="keyword"></span>詳しくは、<a href="../faq/faq-inbound-data-ingestion.md">受信顧客データ取り込みの FAQ</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アウトバウンドデータ </p> </td> 
   <td colname="col2"> <p>これは、<span class="keyword">Audience Manager</span> からサードパーティアクティベーションパートナーに送信されるバッチデータです。保持期間は 8 日です。アウトバウンドデータについて詳しくは、<a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">アウトバウンドバッチ転送</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 特性絞り込みデータ保持 {#trait-qual}

特性絞り込みのデータ保持オプションを次の表にまとめます。

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 特性の操作 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>特性を削除 </p> </td> 
   <td colname="col2"> <p>特性を削除すると、過去にその特性に絞り込まれたすべてのユーザープロファイルから特性絞り込みデータが削除されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>特性上限に到達 </p> </td> 
   <td colname="col2"> <p>ユーザーごとの特性絞り込みの上限を 100,000 件に設定しています。この制限は、認証済みプロファイルとデバイスプロファイルに適用されます。ユーザープロファイルがこの上限に達したら、先入れ先出し方式で古い特性絞り込みから順に削除します。 </p> <p>詳しくは、<a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit">特性絞り込みの制限</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

