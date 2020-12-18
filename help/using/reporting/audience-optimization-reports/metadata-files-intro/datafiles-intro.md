---
description: データファイルにはインプレッション、クリックまたはコンバージョンのデータが含まれます。形式が正しい場合は、このデータを Audience Manager に読み込み、Audience Optimization レポートおよびアクションにつながるログファイルで使用できます。データファイルの形式を、この節で説明した仕様に合わせてください。
seo-description: データファイルにはインプレッション、クリックまたはコンバージョンのデータが含まれます。形式が正しい場合は、このデータを Audience Manager に読み込み、Audience Optimization レポートおよびアクションにつながるログファイルで使用できます。データファイルの形式を、この節で説明した仕様に合わせてください。
seo-title: Audience Optimization レポートおよびアクションにつながるログファイル用のデータファイル
solution: Audience Manager
title: Audience Optimization レポートおよびアクションにつながるログファイル用のデータファイル
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: log files
translation-type: ht
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: ht
source-wordcount: '1042'
ht-degree: 100%

---


# Audience Optimization レポートおよびアクションにつながるログファイル用のデータファイル {#data-files-for-audience-optimization-reports}

データファイルにはインプレッション、クリックまたはコンバージョンのデータが含まれます。形式が正しい場合は、このデータを Audience Manager に読み込み、[Audience Optimization レポート](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)で表示し、[アクションにつながるログファイル](/help/using/integration/media-data-integration/actionable-log-files.md)からデータを使用して特性を作成できます。データファイルの形式を、この節で説明した仕様に合わせてください。

## 概要 {#overview}

適切な名前と形式のデータファイルを使用すると、インプレッション、クリック、コンバージョンのいずれかのデータを [Audience Optimization レポート](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)にインポートできます。これは、[!DNL Audience Manager] と統合されていないパートナーのデータを同レポートスイートで扱う場合に役に立ちます。このプロセスには、インプレッション、クリック、コンバージョンのデータごとに別個のファイルが必要です。これらのイベントを単一のファイルに混在させないでください。

データファイルには、メタデータファイルが付いている必要があります。メタデータファイルには、データファイルの情報に対応するレポートメニューラベルが人間に判読できる形で記載されています。詳しくは、[メタデータファイルの概要とマッピング](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)を参照してください。

## データファイルの命名規則 {#naming-conventions}

適格なデータファイル名の構造を次の構文で定義します。なお、*斜体*&#x200B;の部分にはファイルコンテンツの実際の情報が入ります。

**構文：** <pre><i>event type</i>_<i>yyyymmdd</i></code></pre>

ファイル名の場合：

* イベントタイプは、ファイルにインプレッション、クリック、コンバージョンのどれが格納されているかを示します。イベントタイプごとに別個のファイルを作成します。
* アンダースコアは、イベントタイプと年月日タイムスタンプの区切りになります。
* アップロードする前に、gzip を使用してファイルを圧縮し、`.gz` ファイル拡張子を付けて保存します。

これらの要件を前提として、コンテンツに応じてデータファイルに次のように名前を付けます。

* インプレッションデータ： <pre>impressions_<i>yyyymmdd</i>.gz</code></pre>
* クリックデータ： <pre>clicks_<i>yyyymmdd</i>.gz</code></pre>
* コンバージョンデータ： <pre>conversions_<i>yyyymmdd</i>.gz</code></pre>

## データファイルのコンテンツ形式 {#content-format}

適格なデータファイルのコンテンツ構造を次の構文で定義します。なお、*斜体*&#x200B;の部分には実際のデータファイル内のラベルが入ります。

**構文：** <pre><i>header label 1</i> | <i>header label 2</i> ... <i>header label n</i> | <i>version</i></code></pre>

ファイルコンテンツの場合：

* ヘッダーラベルは、以下の表に示す順序で出現する必要があります。インプレッションとクリックは、同じラベルを使用します。コンバージョンファイルには追加のヘッダーが含まれています。
* 特定の列のデータがない場合は、そのフィールドに `-1` を入力します。

* ファイルの末尾はバージョン番号である&#x200B;*必要があり*&#x200B;ます。現在のバージョンは 1.1 です。
* ファイルヘッダーとコンテンツを非印字 ASCII 文字 001 で区切ります。ASCII 001 を使用できない場合は、ヘッダーとデータをタブ文字で区切ります。これらは非印字文字なので、上記の構文例では、表示のためだけにパイプ「`"|"`」を使用しています。

**フィールドラベル**

次の表では、データファイルの列ヘッダーを列挙し説明します。ヘッダーは大文字と小文字の区別があり、この表での順序どおりに出現する必要があります。他に指示がない限り、すべてのデータタイプは整数（INT）です。

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ラベル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Time-Stamp </p> </td> 
   <td colname="col2"> <p>インプレッションイベント、クリックイベント、コンバージョンイベントの日付と時刻（UTC タイムゾーン）。<code> yyyy-MM-dd HH:mm:ss</code>形式を使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>サイト訪問者の ID。<span class="term"> データプロバイダー一意のユーザー ID</span> または DPUUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>広告主のデータソース ID または統合コード。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>事業部門 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
   <td colname="col2"> <p>キャンペーン ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>クリエイティブ ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site-ID </p> </td> 
   <td colname="col2"> <p>サイト ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> 広告サーバーから割り当てられたプレースメント ID（数値）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>広告掲載申込 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>戦術 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical-ID </p> </td> 
   <td colname="col2"> <p>垂直産業部門の ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantity </p> </td> 
   <td colname="col2"> <p> コンバージョンイベントで販売された商品の数。 </p> <p> <i>コンバージョンデータファイルの場合のみ。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Revenue </p> </td> 
   <td colname="col2"> <p>獲得やその他のコンバージョン量。データタイプは浮動小数。 </p> <p> <i>コンバージョンデータファイルの場合のみ。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Other-Data </p> </td> 
   <td colname="col2"> <p>コンバージョンランディングページの URL。データタイプは文字列。 </p> <p> <i>コンバージョンデータファイルの場合のみ。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>コンバージョンタイプ。コンバージョンが対応しているかどうかを示します。オプションは次のとおりです。 </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>：インプレッション </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>：クリック </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>：原因不明 </li> 
    </ul> <p> <i>コンバージョンデータファイルの場合のみ。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>バージョン </p> </td> 
   <td colname="col2"> <p>インプレッション、クリック、コンバージョンのデータファイルの行ごとに末尾に出現する必須のバージョン番号。現在のバージョンは 1.1 です。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## データファイルの配信方法 {#delivery-methods}

インプレッション、クリック、コンバージョンのデータファイルは、[!DNL Audience Manager] アカウントの Amazon S3 ディレクトリにアップロードします。配信／ディレクトリパス、ファイル処理回数、データ更新については、この節を参照してください。

>[!IMPORTANT]
>
> 使い始めるには、Audience Manager のコンサルタントまたはカスタマーケアに連絡して、お使いのデータファイル用に [!DNL Amazon S3]ディレクトリを設定するよう依頼します。

**配信パスの構文と例**

データはユーザーごとに [!DNL Amazon S3] ディレクトリ内の個別の名前空間に保存されます。ファイルパスは以下の構文に従います。なお、*斜体*&#x200B;の部分には実際の情報が入ります。他の要素は定数またはキーで、変わりません。

**構文：** <pre>.../log_ingestion/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/ <i>file type</i>_<i>yyyymmdd</i></code></pre>

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
   <td colname="col2"> <p>このキー値ペアは、<span class="keyword">Audience Manager</span> の顧客 ID を含みます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>イベント呼び出し時に渡されるデータソース ID のキー値ペア。この情報で、データがどこから得られたかが特定され、そのデータが、対応するメタデータファイルに関連付けられます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> データファイルの上位ディレクトリ。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>格納されているデータの種類を示すファイルタイプ名と配信タイムスタンプ。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**アップロードパスとファイル名のサンプル**

ファイルをアップロードすると、パスは次のようになります。

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**ファイル処理の回数と更新**

データファイルは 1 日 4 回定期的に処理されます。

データを更新するには、当日のインプレッション、クリック、コンバージョンをすべて格納したファイルを送信します。この場合、1 日は当日の午前 0 時から翌日の午前 0 時までの 24 時間になります。ベストプラクティスとして、世界標準時（UTC）で時刻を定義するとよいでしょう。

## 次の手順 {#next-steps}

メタデータファイルの命名と作成の要件を確認します。作業を開始するには、[メタデータファイルの概要とマッピング](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)を参照してください。
