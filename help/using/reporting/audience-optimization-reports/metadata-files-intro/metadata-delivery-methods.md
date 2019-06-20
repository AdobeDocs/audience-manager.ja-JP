---
description: メタデータファイルを送信または更新するには、メタデータファイルを Audience Manager アカウント用の特別な Amazon S3 ディレクトリに送信します。配信／ディレクトリパス、ファイル処理回数、データ更新については、この節を参照してください。
seo-description: メタデータファイルを送信または更新するには、メタデータファイルを Audience Manager アカウント用の特別な Amazon S3 ディレクトリに送信します。配信／ディレクトリパス、ファイル処理回数、データ更新については、この節を参照してください。
seo-title: メタデータファイルの配信方法
solution: Audience Manager
title: メタデータファイルの配信方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# メタデータファイルの配信方法{#delivery-methods-for-metadata-files}

メタデータファイルを送信または更新するには、メタデータファイルを Audience Manager アカウント用の特別な Amazon S3 ディレクトリに送信します。配信／ディレクトリパス、ファイル処理回数、データ更新については、この節を参照してください。

## 配信パスの構文と例 {#syntax}

データはユーザーごとに Amazon S3 ディレクトリ内の個別の名前空間に保存されます。ファイルパスは以下の構文に従います。なお、*斜体*の部分には実際の情報が入ります。角括弧 `[ ]` はオプションのパラメーターを表します。その他の要素は定数で、変動しません。

**構文：**
<pre><code>…/log_ instore/pid=<i>AAM ID</i>/dpid= <i>d_ src</i>/[meta| status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>子ID</i></code></pre>

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
   <td colname="col1"> <p> <code>dpid=<i> d_src</i></code> </p> </td> 
   <td colname="col2"> <p>イベント呼び出し時に渡されるデータソース ID のキー値ペア。データソース ID は、ファイル内のすべてのコンテンツを、そのコンテンツが属する実際のデータに関連付ける値です。 </p> <p>例えば、ID が 123 で名前が「Advertiser Creative A」であるクリエイティブがあるとします。イベントの呼び出しでは ID しか渡されないので、メタデータファイルに「Advertiser Creative A」を入れる必要があります。キャンペーンとクリエイティブはデータソースに属しています。データソース ID はこれらをまとめるもので、これによりイベント呼び出しで送信される ID にファイルのコンテンツを正確に関連付けることができます。<a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names">イベント呼び出し ID によるファイル名、コンテンツ、配信パスの決定方法</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code>meta</code> は、ファイルのアップロード／ストレージディレクトリです。 </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code>status</code> は、ファイルの処理の成功と失敗に関する情報が格納されるディレクトリのパスです。ファイルが処理されると、<code>yyyymmdd</code> 形式のタイムスタンプのタイトルが付いた <code>.info</code> ファイルが作成されます。ステータスファイルには、JSON オブジェクトのデータが保存されています。詳しくは、<a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md">メタデータファイルのステータスの更新</a>を参照してください。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>yyyymmdd</i>_<i> parent ID</i>_<i> child ID</i></code> </p> </td> 
   <td colname="col2"> <p>ファイル名です。詳しくは、<a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md">メタデータファイルの命名規則</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**サンプルのアップロードおよびステータスパス**

メタデータファイルをアップロードする場合、または[そのステータスを確認する](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md)場合、ファイルのパスは次のようになります。

* アップロードパス：`/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* 処理状態パス：`/log_ingestion/pid=1234/dpid=567/status/20150827.info`。

## ファイル処理の回数と更新 {#processing-times}

メタデータファイルは 1 日 4 回、等間隔で処理されます。

メタデータレコードを更新するには、新しい情報が含まれるファイルを送信します。毎回すべての更新を送信する必要はありません。
