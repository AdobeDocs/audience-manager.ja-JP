---
description: インスタンスレベルの DIL API を使用すると、Audience Manager オブジェクトをプログラムで作成し操作することができます。インスタンスレベルのメソッドは、クラスレベルのメソッドで実現している API 機能を強化したものです。
keywords: 特性の作成;特性の作成
seo-description: インスタンスレベルの DIL API を使用すると、Audience Manager オブジェクトをプログラムで作成し操作することができます。インスタンスレベルのメソッドは、クラスレベルのメソッドで実現している API 機能を強化したものです。
seo-title: インスタンスレベルの DIL メソッド
solution: Audience Manager
title: インスタンスレベルの DIL メソッド
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# インスタンスレベルの DIL メソッド{#instance-level-dil-methods}

インスタンスレベルの [!UICONTROL DIL] API を使用すると、Audience Manager オブジェクトをプログラムで作成し操作することができます。インスタンスレベルのメソッドは、クラスレベルのメソッドで実現している API 機能を強化したものです。

## Getting started with Instance-level DIL Methods {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

インスタンスレベルの [!UICONTROL DIL] API を操作する場合：

* アクセスにはパートナー名およびコンテナ名前空間 ID（NSID）が必要になります。担当の Audience Manager アカウントマネージャーにご連絡のうえ、これらの情報を入手してください。
* サンプルとして提示された API ドキュメント内のすべての&#x200B;*斜体*&#x200B;テキストを、使用するメソッドで必要となる値、ID、または他の変数に置き換えてください。

<!-- 

c_instance_start.xml

 -->

## シグナル {#signals}

保留中のリクエストのクエリ文字列に顧客レベルおよびプラットフォームレベルのマッピングを追加します。

<!-- 

r_dil_signals.xml

 -->

**関数シグネチャ：**`signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 他の API 呼び出しをこのメソッドに連結することができます。
>* Adobe Experience Cloud JavaScript ライブラリがページ上にある場合、`submit()` は、Cloud での Cookie の設定後にリクエストを送信します。


**予約済みリクエストキー**

次のリクエストキーは予約されているので、このメソッドで上書きすることはできません。

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**パラメーター**

| 名前 | タイプ | 説明 |
|---|---|---|
| `obj` | オブジェクト | プラットフォームレベルのマッピングのキーと値のペアを表すオブジェクト。パラメーターには、オブジェクトのプロパティ値として文字列と配列を使用できます。 |
| `prefix` | 文字列 | オプションです。各オブジェクトキーの先頭に付加される文字列値（元の値は置き換えられます）。 |
| `return` | DIL.api | 現在の DIL インスタンスの API オブジェクトを返します。 |

**応答**

現在の [!UICONTROL DIL] インスタンスの API オブジェクトを返します。

**サンプルコード**

<pre><code>var dataB= DIL. create（{
パートナー:'<i>PartnerName</i>'
containerNSID: <i>containerNSID</i> }）;

//Method1var 
obj={key1:1， key2:2};
DataLib. api. signatures（obj，'c_'）. submit（）;

//Method2DataB. 
api. signatures（{c_ zdid:54321}）. submit（）;

//Method3//will 
send'c_ key= a&amp; c_ key=2&amp; c_ key=3'to Audience Manager 
var obj={key:['a'，'b'，'c']};
DataLib. api. signatures（obj，'c_'）. submit（）;</code>
</pre>

>[!MORE_LIKE_THIS]
>
>* [キー変数名の要件](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

保留中の要求のクエリ文字列に、SID を追加します。

<!-- 

r_dil_traits.xml

 -->

**関数シグネチャ：**`traits:function (sids){}`

>[!NOTE]
>
>他の API 呼び出しをこのメソッドに連結することができます。

**パラメーター**

| 名前 | タイプ | 説明 |
|---|---|---|
| `sids` | 配列 | 特性セグメント ID の配列。 |

**応答**

現在の [!UICONTROL DIL] インスタンスの API オブジェクトを返します。

**サンプルコード**

<pre><code>var PartnerObject= DIL. create（{
パートナー:'<i>パートナー名</i>'、
containerNSID: <i>NSID</i> }）;
PartnerObject. api. tranits（<i>[123，456，789]</i>）;</code>
</pre>

## logs {#logs}

保留中の要求のログファイルにデータを追加します。

<!-- 

r_dil_logs.xml

 -->

**関数シグネチャ：**`logs: function {key1:value1, key2:value2}`

**応答**

現在の [!UICONTROL DIL] インスタンスの API オブジェクトを返します。

**サンプルコード**

<pre><code>var PartnerObject= DIL. create（{
パートナー:'<i>パートナー</i>'，
containerNSID: <i>NSID</i> }）;
PartnerObject. api. logs（{
file:'dil. js'，
message:"This is the first request'}）;</code>
</pre>

## submit {#submit}

[!UICONTROL DIL] インスタンスの保留中のデータすべてを Audience Manager に送信します。

<!-- 

r_dil_submit.xml

 -->

**関数シグネチャ：**`submit: function () {}`

>[!NOTE]
>
>他の API 呼び出しをこのメソッドに連結することができます。また、[!UICONTROL DIL] はエンコードされたデータを宛先 Cookie に書き込みます。例えば、空白は `%20` としてコード化され、セミコロンは `%3B` としてコード化されます。

**応答**

現在の [!UICONTROL DIL] インスタンスの API オブジェクトを返します。

**サンプルコード**

<pre><code>var dataB= DIL. create（{
パートナー:<i>'PartnerName</i>'、
containerNSID: <i>containerNSID</i> }）;

DataLib. api. tranits（[<i>123,456，789</i>]）. 
logs（{
file:'dil. js'，
message:"This is the first request'}）. 
signs（{
c_ zdid: <i>1111</i> 
d_ dma:'<i>default</i>'}）. 
submit（）;</code>
</pre>

>[!MORE_LIKE_THIS]
>
>* [キー変数のプレフィックスに関する要件](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

デフォルトのターゲットパブリッシングのコールバック後に実行される関数です。

<!-- 

r_dil_after_result.xml

 -->

**関数シグネチャ：**`afterResult: function (fn) {}`

>[!NOTE]
>
>他の API 呼び出しをこのメソッドに連結することができます。

**パラメーター**

| 名前 | タイプ | 説明 |
|---|---|---|
| `fn` | 関数 | 宛先パブリッシングを処理するデフォルトのコールバックにより JSON が処理された後に実行する関数。 |

**応答**

現在の [!UICONTROL DIL] インスタンスの API オブジェクトを返します。

**サンプルコード**

<pre><code>var dataB= DIL. create（{
パートナー:<i>'PartnerName</i>'、
containerNSID: <i>containerNSID</i> }）;

DataB. api. signatures（{
c_ zdid: <i>54321</i> 
d_ dma:'<i>default</i>'}）. 
afterResult（function（json）{
//Doサーバーから返されたJSONデータを使用して何かします。 
}).submit();
</code></pre>

## clearData {#cleardata}

保留中の要求内のすべてのデータをクリアします。

<!-- 

r_dil_clear_data.xml

 -->

**関数シグネチャ：**`clearData: function () {}`

>[!NOTE]
>
>他の API 呼び出しをこのメソッドに連結することができます。

**応答**

現在の [!UICONTROL DIL] インスタンスの API オブジェクトを返します。

**サンプルコード**

<pre><code>var dataB= DIL. create（{
パートナー:<i>'PartnerName</i>'、
containerNSID: <i>containerNSID</i> }）;

DataLib. api. tranits（[<i>123,456，789</i>]）. logs（{
file:'dil. js'
message:"This is the first request'}）. 
signs（{
c_ zdid: <i>1111</i> 
d_ dma:'<i>default</i>'}）;

//Reset保留中のデータDataLib. 
clearData（）;</code>
</pre>

## customQueryParams {#customqueryparams}

データ収集サーバーによって明示的に定義されていないカスタムクエリパラメーターを保留中の要求に追加します。

<!-- 

r_dil_custom_query_params.xml

 -->

**関数シグネチャ：**`customQueryParams: function (obj) {}`

>[!NOTE]
>
>他の API 呼び出しをこのメソッドに連結することができます。

**予約済みリクエストキー**

次のリクエストキーは予約されているので、このメソッドで上書きすることはできません。

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**応答**

現在の DIL インスタンスの API オブジェクトを返します。

**サンプルコード**

<pre><code>var PartnerObject= DIL. create（{
パートナー:'<i>パートナー</i>'，
containerNSID: <i>NSID</i> }）;
PartnerObject. api. customQueryParams（{
nid:54231，
ntype:'default'}）;</code>
</pre>

## getContainerNSID {#getcontainernsid}

[!UICONTROL DIL] インスタンスのコンテナの NSID の値を返します。デバッグおよびトラブルシューティングに役立ちます。

<!-- 

r_dil_get_container_nsid.xml

 -->

**関数シグネチャ：**`dil.api.getContainerNSID: function () {}`

**サンプルコード**

<pre><code>var dataB= DIL. create（{
パートナー:<i>'PartnerName</i>'、
containerNSID: <i>containerNSID</i> }）;

//Verifycontainer nSID 
var nsid= DataB. api. getContainerNSID（）;</code>
</pre>

## getEventLog {#geteventlog}

時系列にソートされたイベントログデータを文字列の配列として返します。デバッグおよびトラブルシューティングに役立ちます。

<!-- 

r_dil_get_event_log.xml

 -->

**関数シグネチャ：**`dil.api.getEventLog: function () {}`

**サンプルコード**

<pre><code>var dataB= DIL. create（{
パートナー:<i>'PartnerName</i>'、
containerNSID: <i>containerNSID</i> }）;

DataLib. api. tranits（[<i>123，456，789</i>]）. logs（{
file:'dil. js'，
message:"This is the first request'}）;. signatures（{
c_ zdid: <i>1111</i> 
d_ dma:'<i>default</i>'}）;. submit（）;

//Checklog for messages 
var log= DataB. api. getEventLog（）;
if（log&amp;&amp; log. length）{
alert（log. join（'\ n'））;
} else{
alert（'no log messages'）;
}</code>
</pre>

## getPartner {#getpartner}

[!UICONTROL DIL] インスタンスのパートナー名を返します。デバッグおよびトラブルシューティングに役立ちます。

<!-- 

r_dil_get_partner.xml

 -->

**関数シグネチャ：**`dil.api.getPartner: function () {}`

**サンプルコード**

<pre><code>var dataB= DIL. create（{
パートナー:'<i>PartnerName</i>'
containerNSID: <i>containerNSID</i> }）;

//Verifythe partner name 
var partner= DataB. api. getPartner（）;</code>
</pre>

## getState {#getstate}

[!UICONTROL DIL] インスタンスの現在の状態を返します。デバッグおよびトラブルシューティングに役立ちます。

<!-- 

r_dil_get_state.xml

 -->

**関数シグネチャ：**`dil.api.getState: function () {}`

**サンプルコード**

<pre><code>var dataB= DIL. create（{
パートナー:<i>'PartnerName</i>'、
containerNSID: <i>containerNSID</i> }）;

DataLib. api. tranits（[<i>123，456，789</i>]）. logs（{
file:'dil. js'，
message:"This is the first request'}）;. signatures（{
c. zdid: <i>1111</i> 
d_ dma:'<i>default</i>'}）;. submit（）;

var state= DataB. api. getState（）;

/*オブジェクトの状態state={
PendingRequest:{<i>pending data for call to server</i>}，
otherRequestInfo:{
firingQueue:[]，
起動:[]，
発光:false、
エラー:[]，
ReservedKeys:{
sid:true，
pdata:true，
logdata:true，
callback:true，
postCallbackFn:true，
useImageRequest:true，
}，
firstRequestHasSDED:false、
num_ of_ jsonp_ responses:0，
num_ of_ jsonp_ errors:0，
num_ of_ img_ response:0，
num_ of_ img_ errors:0
}，
DestinationPublishingInfo:{
THROTTLE_ START:3000，
ThrottleTimerSet:false、
id:"destination_ publishing_ iframe_'+ partner+'_'+ containerNSID，
url:（定数. isTips?'https://':'https://fast.')+ partner+'.demdex.net/dest3.html?d_nsid='
+ containerNSID+'#'+ encodeURIComponent（document. location. href），
iframe:null、
IFrameHasLoaded:false、
sendingMessages:false、
メッセージ:[]，
messageSendingInterval:定数. POST_ MESSAGE_ ENABLED?15: 100, 
               //Recommend 100ms for IE 6 &amp; 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

データパートナー同士、または Audience Manager とユーザー ID を交換および同期するための 2 つの関数で構成されています。

<!-- 

r_dil_idsync.xml

 -->

**関数シグネチャ：**

[!UICONTROL DIL] のバージョン 2.10 および 3.1 以降で使用できます。

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> コード </th> 
   <th colname="col2" class="entry"> ユーザー ID の同期 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>複数のデータパートナーと Audience Manager の間で実行されます。例えば、パートナー x がこれを使用してユーザー ID をパートナー y と同期し、Audience Manager に送信します。 </p> <p> <p><b>重要：</b>このメソッドは廃止されました。Experience Cloud ID サービスインスタンスの <code>idSyncByURL</code> メソッドを使用してください。 </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>ユーザー ID が既に判明していて、それを Audience Manager に送信する場合に使用します。 </p> <p> <p><b>重要：</b>このメソッドは廃止されました。Experience Cloud ID サービスインスタンスの <code>idSyncByDataSource</code> メソッドを使用してください。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync の要素**

`idSync` は次の要素で構成されます。

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名前 </th> 
   <th colname="col2" class="entry"> タイプ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> 文字列 </td> 
   <td colname="col3"> <p>Audience Manager によって割り当てられたデータプロバイダー ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 文字列 </td> 
   <td colname="col3"> <p>ユーザーに関するデータプロバイダーの一意の ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> 数値 </td> 
   <td colname="col3"> <p><i>（オプション）</i> Cookie の有効期限を設定します。整数である必要があります。デフォルトは、20,160 分（14 日）です。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> 文字列 </td> 
   <td colname="col3"> <p>リンク先 URL。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**マクロ**

`idSync` では次のマクロを使用できます。

* **`%TIMESTAMP%`**：タイムスタンプを生成します（ミリ秒単位）。キャッシュバスティングに使用されます。
* **`%DID%`**：ユーザーの Audience Manager ID を挿入します。
* **`%HTTP_PROTO%`**：ページプロトコルを設定します（`http` または `https`）。

**応答**

これらの関数は、成功した場合、`Successfully queued` を返します。そうでない場合、エラーメッセージを返します。

**サンプルコード**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">//によって、localInstance. api. idSync（{
dpid:"23"、//は文字列である必要があります
url:'//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net%2Fbs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D'，
minutesToLive:20160//（オプション）、デフォルトは20160分（14日）}です。</code>
</pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">//Fire'https:/https:'+'//dpm.demdex.net/ibs:dpid=&lt; dpid&gt;&amp; dpuuid=&lt; dpuuid&gt;'dextInstance. 
api. AAMSync（{
dpid:"23"、//は文字列である必要があります
dpuuid:'98765'，//は文字列である必要があります
minutesToLive:20160//（オプション）、デフォルトは20160分（14日）}です。</code>
</pre>

>[!MORE_LIKE_THIS]
>
>* [Experience Cloud ID サービスの同期関数](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

JSON を受信するコールバックを保留中の要求に追加します。

<!-- 

r_dil_result.xml

 -->

**関数シグネチャ：**`result: function (callback) {}`

このコールバックにより、宛先パブリッシングを処理するデフォルトのコールバックが置き換えられます。

>[!NOTE]
>
>他の API 呼び出しをこのメソッドに連結することができます。

**パラメーター**

| 名前 | タイプ | 説明 |
|---|---|---|
| `callback` | 関数 | JSONP コールバックで実行される JavaScript 関数。 |

**応答**

現在の [!UICONTROL DIL] インスタンスの API オブジェクトを返します。

**サンプルコード**

<pre><code>var dataB= DIL. create（{
パートナー:<i>'PartnerName</i>'、
containerNSID: <i>containerNSID</i> }）;

DataB. api. tranits（[<i>123，456，789</i>]）. result（function（json）{
//Doサーバーから返されるJSONデータを含むことがあります。 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` は、Akamaiの呼び出し方法 [!UICONTROL DIL] を制御するbooleanパラメーター [!UICONTROL Data Collection Servers (DCS)] です。

<!-- 

dil-secure-data-collection.xml

 -->

* `secureDataCollection= true`（デフォルト）の場合、[!UICONTROL DIL] は常に、セキュリティで保護された HTTPS 呼び出しをおこないます。

* `secureDataCollection= false` の場合、[!UICONTROL DIL] は、ページで設定されているセキュリティプロトコルに従って、HTTP か HTTPS のどちらかの呼び出しをおこないます。

>[!IMPORTANT]
>
>visitorAPI.js と `secureDataCollection= false` を同じページで使用する場合は、[!UICONTROL DIL] と設定します。次のコードサンプルを参照してください。

<pre><code class="js">var delolInstance= DIL. create（{
…
secureDataCollection:false}）;</code>
</pre>

>[!MORE_LIKE_THIS]
>
>* [DIL create](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` は、ブラウザーから他のドメインのリソースを要求する方法を制御するための true または false のブール型パラメーターです。

<!-- 

dil-use-cors-only.xml

 -->

**概要**

`useCORSOnly` のデフォルト値は false です。false の場合、ブラウザーは CORS または JSONP でリソースチェックを実行します。ただし、[!UICONTROL DIL] は常に、最初に CORS を使用してリソースを要求しようとします。CORS をサポートしていない古いブラウザーでは、JSONP に切り替わります。ブラウザーで必ず CORS のみを使用するように指定する必要がある場合（サイトに厳しいセキュリティ要件がある場合など）は、`useCORSOnly:true` を設定します。

**コードサンプル**

<pre><code class="js">var delolInstance= DIL. create（{
…
useCorsOnly:true}）;</code>
</pre>

>[!IMPORTANT]
>
>* サイト訪問者のブラウザーが CORS をサポートしていることが確実な場合にのみ `useCORSOnly: true` を設定することをお勧めします。
>* `useCORSOnly: true` の場合、[!UICONTROL DIL] は Internet Explorer 9 またはそれ以前のバージョンからは ID 呼び出しをおこないません。
>



>[!MORE_LIKE_THIS]
>
>* [DIL create](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Experience Cloud ID サービス：UseCORSOnly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Experience Cloud ID サービスでの CORS のサポート](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

要求のタイプをスクリプト（`<src>`）から画像（`<img>`）に変更します。

<!-- 

r_dil_use_image_request.xml

 -->

**関数シグネチャ：**`useImageRequest: function () {}`

>[!NOTE]
>
>他の API 呼び出しをこのメソッドに連結することができます。

**応答**

現在の [!UICONTROL DIL] インスタンスの API オブジェクトを返します。

**サンプルコード**

<pre><code>var dataB= DIL. create（{
パートナー:<i>'PartnerName</i>'、
containerNSID: <i>containerNSID</i> }）;

DataB. api. tranits（[<i>123，456，789</i>]）. useImageRequest（）. submit（）;</code>
</pre>

