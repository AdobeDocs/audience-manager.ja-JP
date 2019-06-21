---
description: 宣言済み ID の機能、セットアップ手順、コード例、変数について説明します。
keywords: id同期
seo-description: 宣言済み ID の機能、セットアップ手順、コード例、変数について説明します。
seo-title: 宣言済み ID
solution: Audience Manager
title: 宣言済み ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# 宣言済み ID {#declared-ids}

宣言済み ID の機能、セットアップ手順、コード例、変数について説明します。

## 宣言済み ID のターゲティング {#declared-id-targeting}

サードパーティ Cookie のような持続的ストレージメカニズムを使用しないデバイスやブラウザーで、Audience Manager とのユーザー ID の交換および同期をおこないます。

<!-- declared_id_about.xml -->

## 宣言済み ID のターゲティングの目的 {#declared-id-targeting-purpose}

一部のブラウザーやほとんどのモバイルデバイスでは、サードパーティ Cookie を許可していません。そのため、サイト訪問者に関する情報の保持や永続的 ID の割り当てが難しくなります。To resolve this issue, Audience Manager uses [!UICONTROL DIL] to let you pass in [!UICONTROL declared IDs] on an event call. Also, a [!UICONTROL declared ID] can act as a universal ID that applies to the same user across all the solutions in the [!DNL Experience Cloud]. ID のターゲティング／マッチング処理を次の表で説明します。

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 処理 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>イベント呼び出し</b> </td> 
   <td colname="col2"> <p>機能するには、ページに <span class="wintitle">DIL</span> と <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external">Experience Cloud ID サービス</a>コードが必要です。<span class="wintitle"></span><span class="wintitle"></span>DIL では、<code>setVisitorID</code> 関数で宣言された ID を Experience Cloud ID サービスから取得して <span class="keyword">Audience Manager</span> に渡します。<span class="keyword"></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID のマッチング</b> </td> 
   <td colname="col2"> <p>Audience Manager は、クライアントおよび訪問者 ID を、システム内の対応する ID と照合します。一致する ID が存在しなければ、Audience Manager は、新規 ID を作成してクライアントおよび訪問者 ID に関連付けます。 </p> <p> <p>注意：ID が複数の Audience Manager ID にマッピングされている場合は、最新のマッピングが使用されます。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID の返送</b> </td> 
   <td colname="col2"> <p>Audience Manager は、同期した ID をクライアントドメインまたはアプリケーションのファーストパーティ Cookie （または他のアドレス可能なストレージ領域）に書き込みます。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>後続のイベント呼び出し</b> </td>
   <td colname="col2"> <p>追加のイベント呼び出しでクライアントのドメインから Audience Manager ID を読み取って Audience Manager に送信します。 </p> </td>
  </tr> 
 </tbody>
</table>

まず最初に、データ収集に使用するサイトのすべてのページに [!DNL Experience Cloud][!UICONTROL DIL] ID サービスと を設定する必要があります。[DIL create](../dil/dil-class-overview/dil-create.md#dil-create) および[宣言済み ID 変数](../features/declared-ids.md#declared-id-variables)を参照してください。

## オプトアウト呼び出し {#opt-out-calls}

[!UICONTROL declared ID] このプロセスは、WebサイトによるAudience Managerのターゲット設定をオプトアウトするためのサイト訪問者の環境設定に適しています。When Audience Manager receives an opt-out request, the [!DNL JSON] returned by the [!UICONTROL DCS] contains the error code 171, with the message &quot;Encountered opt out tag&quot;, instead of the Audience Manager user ID.

* Audience Manager can pass in a [!UICONTROL declared ID] opt-out alongside an Audience Manager [!UICONTROL UUID] in the [!DNL URL].
* [!UICONTROL declared ID] オプトアウトは[!パートナーごとのUACROLプロファイルキャッシュサーブレット（[!UICONTROL PCS]）。There is no platform-level opt-out using [!UICONTROL declared IDs]. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross [!UICONTROL DCS] regions).

See [Data Privacy](../overview/data-security-and-privacy/data-privacy.md) for more information about opting-out of data collection.

## 宣言済み ID のオプトアウトの例 {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. `d_dpid` や `d_dpuuid` などの従来のパラメーターはまだ機能しますが、既に廃止されています。詳しくは、 [従来の DPID と DPUUID に代わる CID](../reference/cid.md) を参照してください。以下の例で、*斜体*の部分には実際の情報が入ります。

### CID および CID_IC を使用したオプトアウト

説明と構文については、[宣言済み ID の URL 変数および構文](../features/declared-ids.md#variables-and-syntax)を参照してください。

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> オプトアウト方法 </th> 
   <th colname="col2" class="entry"> コードサンプル </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>データプロバイダー ID およびユーザー ID </p> </td> 
   <td colname="col2"> <p> <code> https:// <i> domain name </i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>統合コードおよびユーザー ID </p> </td> 
   <td colname="col2"> <p> <code> https:// <i> domain name </i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>複数の <code>d_cid</code> および <code>d_cid_ic</code> キー値ペア </p> </td> 
   <td colname="col2"> <p> <code> https:// <i> domain name </i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### DPID、DPUUID、UUID を使用したオプトアウト（廃止済み）

これらの方法はまだ機能しますが、既に廃止されています。この情報は、従来手法の参考などのために提供するものです。従来のオプトアウト方法は次のとおりです。

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> オプトアウト方法（廃止） </th> 
   <th colname="col2" class="entry"> コードサンプル </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> のみ </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=AAM<i></i>ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>パートナーレベルのオプトアウト </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid=user ID&amp; d_ dpid= data provider ID </code> </p> <p>パートナーレベルのオプトアウトは、この <code>dpid</code> + <code>dpuuid</code> ペアの AAM UUID への最新マッピングに対して保存されます。既存のマッピングがなければ、Audience Manager は、要求の Cookie に AAM UUID が含まれているかどうかを確認し、含まれていれば、それを使用してオプトアウトを保存します。含まれていなければ、Audience Manager は新規の AAM UUID を生成し、それについてオプトアウトを保存します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> + <code>d_dpid</code> および明示的な <code>d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>user ID&amp; d_ dpuuid= data providerのuser ID&amp;<i>d_ dppid= data provider ID</i></code> </p> <p> <code>d_uuid</code> が常に優先します。<code>dpid</code> + <code>dpuuid</code> の組み合わせが別の AAM UUID にマッピングされていても、オプトアウトは、要求（<code>d_uuid</code>）で渡された AAM UUID に保存されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 宣言済み ID の 変数および構文 {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

以下の表に、[!DNL Audience Manager] でデータプロバイダー ID およびユーザー ID または統合コード（使用する場合）を渡すキーと値のペアを示します。なお、*斜体*の部分には実際の情報が入ります。読みやすくするために、スペースが追加されています。

それぞれのキー値ペアでは、以下がおこなわれます。

* `=` シンボルは、キーと関連する値を区切ります。
* The non-printing [!DNL ASCII] character `%01` separates the values.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid = <i> data provider ID </i> %01 <i> user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>データプロバイダー ID とそれに関連する一意のユーザー ID が単一のキー値ペアとして含まれています。<code>d_cid</code> は <code>d_dpid</code> および <code>d_dpuuid</code> に代わるものです。d_dpid と d_dpuuid は廃止済みと見なされますが、まだサポートされています。詳しくは、 <a href="../reference/cid.md">従来の DPID と DPUUID に代わる CID</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic = <i> integration code </i> %01 <i> user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>統合コードとそれに関連する一意のユーザー ID が単一のキー値ペアとして含まれています。<code>d_cid_ic</code> は <code>d_dpid</code> および <code>d_dpuuid</code> に代わるものです。d_dpid と d_dpuuid は既に廃止されていますが、まだサポートされています。詳しくは、 <a href="../reference/cid.md">従来の DPID と DPUUID に代わる CID</a> を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## サンプルイベント呼び出し {#sample-event-calls}

これらのキー値ペアとその必須構文を仮定すると、イベント呼び出しは以下のようにおこないます。

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> イベント呼び出しに含まれるもの </th> 
   <th colname="col2" class="entry"> コードサンプル </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>データプロバイダー ID およびユーザー ID </p> </td> 
   <td colname="col2"> <p> <code> https:// <i> domain name </i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>統合コードおよびユーザー ID </p> </td> 
   <td colname="col2"> <p> <code> https:// <i> domain name </i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>複数の <code>d_cid</code> および <code>d_cid_ic</code> キー値ペア </p> </td> 
   <td colname="col2"> <p> <code> https:// <i> domain name </i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [DPID と DPUUID に代わる CID](../reference/cid.md)


## 宣言済み ID 変数 {#declared-id-variables}

Describes the configuration variables used to pass declared IDs through [!UICONTROL DIL] to [!DNL Audience Manager.]

## DIL は Experience Cloud ID サービスを使用して宣言済み ID を渡す {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

[Experience Cloud IDサービス](https://marketing.adobe.com/resources/help/en_US/mcvid/)で使用する場合、廃止 [!UICONTROL declared IDs]`dpid``dpuuid` および変数で渡す必要はなくなりました。Instead, the current versions of [!UICONTROL DIL] rely on the `visitorService` function to get the [!UICONTROL declared IDs] from the `setCustomerIDs` function in the [!UICONTROL Experience Cloud ID Service]. 詳しくは、[顧客 ID と認証の状態](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)を参照してください。次のように、`DIL.create` で `visitorService` を呼び出します。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

キーと値のペア `namespace` で、`MCORG` は [!DNL Experience Cloud] の組織 ID です。この ID がわからない場合、[!UICONTROL Administration] ダッシュボードの「[!DNL Experience Cloud]」セクションで確認できます。このダッシュボードを表示するには、管理者権限が必要です。[管理：コアサービス](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html)も参照してください。

## 非推奨の関数 {#deprecated-functions}

With the latest versions of [!UICONTROL DIL] (6.2+), you don&#39;t need to use these key-value pairs to pass in [!UICONTROL declared IDs]. That&#39;s because [!UICONTROL DIL] now relies on the `visitorService` function shown in the code sample above. This function gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service]. ここでは、これらの変数を、履歴やレガシーを示す目的で参照しています。See the code below for an example of how to configure `DIL.create` to get a [!UICONTROL declared ID] from the [!UICONTROL Visitor ID Service].
次の表は、`declaredId` オブジェクトで使用されるレガシー変数の一覧です。

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名前 </th> 
   <th colname="col2" class="entry"> タイプ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> 文字列 </td> 
   <td colname="col3"> <p>Audience Manager によって割り当てられたデータパートナー ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 文字列 </td> 
   <td colname="col3"> <p>ユーザーに関するデータプロバイダーの一意の ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` および `DPUUID`

Audience Manager は結合された `DPID` と `DPUUID` を、システム内の対応するユーザー ID と比較して照合します。存在しない ID がある場合、Audience Manager は新しいユーザー ID を作成し、`DPID/DPUUID` の組み合わせと同期します。Audience Manager がユーザー ID（`UUID`）を照合または作成すると、その ID が レスポンスでクライアントのドメインの Cookie（ファーストパーティの Cookie）またはその他のローカルストレージの Cookie に返されます。[!DNL JSON]

Call this function when you&#39;re using [!UICONTROL DIL] v6.1 or earlier. However, this function has been deprecated in favor of the new version that gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service].

<pre class="js"><code>DIL. create（{
パートナー:「パートナー名」、
declarId:{
dpuuid: <i>dpuuid</i>、
DPID: <i>dpid</i> 
}
}）;</code>
</pre>

>[!NOTE]
>
>なお、`d_dpuuid` および `d_dpid` キーの ID 値を設定するコードをプログラムにより開発する必要があります。

### DIL のインスタンス化の後に ID を渡す

>[!NOTE]
>
>If you make an [!DNL API] call with a different `declaredID` combination, the new combination will be used for that call only. その後の通常のイベント呼び出しでは、元の `DIL.create` `declaredID` の組み合わせが使用されます。

<pre class="js"><code>DIL. getDIL（'partner name'）. api. signations（{…}）. declarId（{
dpuuid:<i>dpuuid</i> 
dpid:<i>dpid</i> }）. 
submit（）;</code>
</pre>

## リクエストとレスポンスの例 {#request-response-examples}

次のリクエストはデータプロバイダー ID とユーザー ID を Audience Manager に送信します。

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

The response returns the Audience Manager ID (e.g., `UUID`) which is written to a first-party cookie in the page domain.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## ターゲティングからの除外 {#do-not-target}

[!UICONTROL declared ID] このプロセスは、WebサイトによるAudience Managerのターゲット設定をオプトアウトするためのサイト訪問者の環境設定に適しています。When Audience Manager receives an opt-out request, the [!UICONTROL DCS] returns an empty [!DNL JSON] object instead of the Audience Manager user ID.