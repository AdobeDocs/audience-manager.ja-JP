---
description: メタデータファイルを送信または更新するには、メタデータファイルを Audience Manager アカウント用の特別な Amazon S3 ディレクトリに送信します。配信／ディレクトリパス、ファイル処理回数、データ更新については、この節を参照してください。
seo-description: メタデータファイルを送信または更新するには、メタデータファイルを Audience Manager アカウント用の特別な Amazon S3 ディレクトリに送信します。配信／ディレクトリパス、ファイル処理回数、データ更新については、この節を参照してください。
seo-title: メタデータファイルの配信方法
solution: Audience Manager
title: メタデータファイルの配信方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: ht
source-git-commit: 1ff46970470eae4bc30760468013d994c976e549

---


# メタデータファイルの配信方法{#delivery-methods-for-metadata-files}

メタデータファイルを送信または更新するには、メタデータファイルを Audience Manager アカウント用の特別な Amazon S3 ディレクトリに送信します。配信／ディレクトリパス、ファイル処理回数、データ更新については、この節を参照してください。

## 配信パスの構文と例{#syntax}

データはユーザーごとに Amazon S3 ディレクトリ内の個別の名前空間に保存されます。ファイルパスは以下の構文に従います。なお、*斜体*&#x200B;の部分には実際の情報が入ります。角括弧 `[ ]` はオプションのパラメーターを表します。その他の要素は定数で、変動しません。

**構文：**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

ファイル配信パスのこれらの各要素を次の表で定義します。

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファイルパラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>ストレージのディレクトリパスの先頭。セットアップがすべて完了したら、完全パスが与えられます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> の顧客 ID のキー値ペア。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>イベント呼び出し時に渡されるデータソース ID のキー値ペア。データソース ID は、ファイル内のすべてのコンテンツを、そのコンテンツが属する実際のデータに関連付ける値です。 </p> <p>例えば、ID が 123 で名前が「Advertiser Creative A」であるクリエイティブがあるとします。イベントの呼び出しでは ID しか渡されないので、メタデータファイルに「Advertiser Creative A」を入れる必要があります。キャンペーンとクリエイティブはデータソースに属しています。データソース ID はこれらをまとめるもので、これによりイベント呼び出しで送信される ID にファイルのコンテンツを正確に関連付けることができます。<a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names">イベント呼び出し ID によるファイル名、コンテンツ、配信パスの決定方法</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>yyyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>ファイル名です。詳しくは、<a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md">メタデータファイルの命名規則</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## ファイル処理の回数と更新 {#processing-times}

メタデータファイルは 1 日 4 回、等間隔で処理されます。

メタデータレコードを更新するには、新しい情報が含まれるファイルを送信します。毎回すべての更新を送信する必要はありません。
