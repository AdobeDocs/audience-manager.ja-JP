---
description: プライバシーやデータに関してよくある質問や問題に対する回答。
seo-description: プライバシーやデータに関してよくある質問や問題に対する回答。
seo-title: プライバシーとデータ保持に関するよくある質問
solution: Audience Manager
title: プライバシーとデータ保持に関するよくある質問
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: データ・ガバナンスとプライバシー
exl-id: bccf49d7-1a3b-4286-86fb-59e472af4501
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 99%

---

# プライバシーとデータ保持に関するよくある質問 {#privacy-and-data-retention-faq}

プライバシーやデータに関してよくある質問や問題に対する回答。

<!-- faq_privacy.xml -->

## プライバシーに関するよくある質問 {#privacy-faq}

>[!TIP]
>
>詳しくは、[アドビプライバシーセンター](https://www.adobe.com/jp/privacy.html)を参照してください。

**Audience Manager では Cookie をどのように使用し、どのような Cookie を設定しますか？**

詳しくは、[Audience Manager の Cookie](https://docs.adobe.com/content/help/ja-JP/core-services/interface/ec-cookies/cookies-am.html) を参照してください。

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
   <td colname="col2"> <p>120 日間 </p> <p> Audience Manager では、Audience Manager プラットフォームでユーザーを最後に確認してから 120 日後にユーザーデータをバックエンドサーバーから削除します。<span class="keyword">Audience Manager</span> がこの 120 日間のサイクル内にユーザーアクティビティを記録した場合、このデータはさらに 120 日間保持されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>エッジサーバー </p> </td> 
   <td colname="col2"> <p> 14 日間 </p> <p>Audience Manager では、Audience Manager プラットフォームでユーザーを最後に確認してから 14 日後にユーザーデータをエッジエンドサーバーから削除します。<span class="keyword">Audience Manager</span> がこの 14 日間のサイクル内にユーザーアクティビティを記録した場合、このデータはさらに 14 日間保持されます。14 日間のサイクルの後にユーザーが再度アクティブになった場合、最初の新規ページビューからユーザーが操作可能になるまでの間に遅延が発生します。14 日間アクティビティがない状態が続いた後、プロファイル全体をエッジセンターに戻すのに 6 ～ 18 時間かかります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>生のログ </p> </td> 
   <td colname="col2"> <p>60 日間（60 日間アクティビティがなかったら、その後削除） </p> <p>生のログは、HTTP 呼び出しを通じて、または <span class="keyword">Audience Manager</span> に送信されたオンボードファイルからエッジサーバーで受信されるデータです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>広告サーバーログ </p> </td> 
   <td colname="col2"> <p><b>レポート</b> </p> <p>ログファイルは、最大 30 日間、レポート目的で保持されます。不一致ログ（訪問者の広告サーバー ID と <span class="keyword">Audience Manager</span> ID の間に ID 同期がないログ）は、アドビのバックエンドストレージには永続的に保存されません。また、<span class="keyword">Amazon S3</span> に格納されている一致ログは最大 30 日間保持されます。 </p> <p><b>アクションにつながるログファイル</b> </p> <p>一致ログも不一致ログも最大 30 日間、保持されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM レベルのプロファイル（認証済みプロファイル） </p> </td> 
   <td colname="col2"> <p>非アクティブな CRM レベルのプロファイル（顧客 ID）のデフォルトの有効期間（TTL）間隔は 24 か月です。ただし、Audience Manager ユーザーインターフェイスを使用して、1 か月から 5 年間の非アクティブな CRM レベルのプロファイルの TTL 間隔を増減できます。これは、クロスデバイス対応データソースを作成または編集するときに実行できます。</p> <p>詳しくは、<a href="../features/profile-merge-rules/merge-rules-start.md#settings">クロスデバイス対応のデータソースの作成</a>のデータソース設定を参照してください。</p> </td> 
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
   <td colname="col2"> <p>Audience Manager cookie ID（<a href="../reference/ids-in-aam.md">Audience Manager の一意のユーザー ID または AAM UUID</a>）とサードパーティ cookie ID 間の <a href="../features/administration/usage-limits.md#id-mapping-limits">ID マッピング</a>の有効期間は 120 日に制限されます。ID マッピングの有効期限は、Audience Manager ネットワークで Audience Manager cookie が表示されるたびにリセットされます。最新の ID マッピング同期は、関連付けられている <a href="../reference/ids-in-aam.md">Audience Manager の一意のユーザー ID（AAM UUID）</a>が有効である間、保持されます。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>インバウンドデータ </p> </td> 
   <td colname="col2"> <p>これは、FTP で <span class="keyword">Audience Manager</span> に送信される受信データ、または <span class="keyword">Amazon S3</span> ディレクトリに直接送信される受信データです。詳しくは、<a href="../faq/faq-inbound-data-ingestion.md">受信顧客データ取り込みの FAQ</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アウトバウンドデータ </p> </td> 
   <td colname="col2"> <p>これは、<span class="keyword">Audience Manager</span> からサードパーティアクティベーションパートナーに送信されるバッチデータです。保持期間は 8 日です。アウトバウンドデータについて詳しくは、<a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">アウトバウンドバッチ転送</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 特性認定データ保持 {#trait-qual}

特性認定のデータ保持オプションを次の表にまとめます。

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
   <td colname="col2"> <p>特性を削除すると、過去にその特性に絞り込まれたすべてのユーザープロファイルから特性認定データが削除されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>特性上限に到達 </p> </td> 
   <td colname="col2"> <p>ユーザーごとの特性絞り込みの上限を 100,000 件に設定しています。この制限は、認証済みプロファイルとデバイスプロファイルに適用されます。ユーザープロファイルがこの上限に達したら、先入れ先出し方式で古い特性絞り込みから順に削除します。 </p> <p>詳しくは、<a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit">特性絞り込みの制限</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>
