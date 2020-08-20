---
description: 宣言された ID の機能、セットアップ手順、コード例、変数について説明します。
keywords: id sync
seo-description: 宣言された ID の機能、セットアップ手順、コード例、変数について説明します。
seo-title: 宣言された ID
solution: Audience Manager
title: 宣言された ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
translation-type: tm+mt
source-git-commit: 29708d5fc528ac9da08f4c5a7f2bcaa11b240d8b
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 80%

---


# [!UICONTROL Declared IDs] {#declared-ids}

How [!UICONTROL declared IDs] work, set up procedures, code examples, and variables.

## [!UICONTROL Declared ID] ターゲット設定 {#declared-id-targeting}

Exchange and synchronize user IDs with [!DNL Audience Manager] from devices or browsers that do not use or accept persistent storage mechanisms, such as third-party [!DNL cookies].

## ター [!UICONTROL Declared ID] ゲティングの目的 {#declared-id-targeting-purpose}

Some browsers, and most mobile devices, do not accept third-party [!DNL cookies]. そのため、サイト訪問者に関する情報の保持や永続的 ID の割り当てが難しくなります。To resolve this issue, [!DNL Audience Manager] uses [!UICONTROL DIL] to let you pass in [!UICONTROL declared IDs] on an event call. また、[!UICONTROL declared ID]は、[!DNL Experience Cloud] のすべてのソリューションで同じユーザーに適用される汎用 ID としても機能できます。ID のターゲティング／マッチング処理を次の表で説明します。

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
   <td colname="col2"> <p>機能させるには、ページに <span class="wintitle">DIL</span> と <a href="https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html" format="https" scope="external">Adobe Experience Platform ID サービス</a>コードが必要です。<span class="wintitle">DIL</span> では、<code> setVisitorID </code> 関数で<span class="wintitle">宣言された ID</span> を <span class="keyword">Adobe Experience Platform ID サービス</span>から取得して <span class="keyword">Audience Manager</span> に渡します。 </p> </td> 
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

まず最初に、データ収集に使用するサイトのすべてのページに [!DNL Experience Cloud] ID サービスと [!UICONTROL DIL] を設定する必要があります。[DIL create](../dil/dil-class-overview/dil-create.md#dil-create) および[宣言された ID 変数](../features/declared-ids.md#declared-id-variables)を参照してください。

## オプトアウト呼び出し {#opt-out-calls}

[!UICONTROL declared ID] の処理では、サイト訪問者の環境設定に従って、 によるターゲティングを Web サイトでオプトアウトすることができます。[!DNL Audience Manager]When [!DNL Audience Manager] receives an opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the error code 171, with the message `Encountered opt out tag`, instead of the [!DNL Audience Manager] user ID.

* [!DNL Audience Manager] は、内でオプトアウトを受け渡すこと [!UICONTROL declared ID] ができ [!DNL Audience Manager][!UICONTROL UUID][!DNL URL]ます。
* オプトア [!UICONTROL declared ID] ウトは、パートナーごとに [!UICONTROL Profile Cache Server] ([!UICONTROL PCS])に保存されます。 [!UICONTROL declared IDs] を使用したプラットフォームレベルのオプトアウトはありません。Additionally, [!DNL Audience Manager] opts the user out from that particular region on the edge (the opt-out does not cross [!DNL DCS] regions).

データ収集のオプトアウトについて詳しくは、[データのプライバシー](../overview/data-security-and-privacy/data-privacy.md)を参照してください。

## [!UICONTROL Declared ID] オプトアウトの例 {#opt-out-examples}

`d_cid` および `d_cid_ic` のキー値ペアを使用して、[!UICONTROL declared ID] のオプトアウトリクエストをおこなうことができます。`d_dpid` や `d_dpuuid` などの従来のパラメーターはまだ機能しますが、既に非推奨（廃止予定）となっています。詳しくは、[DPID と DPUUID に代わる CID](../reference/cid.md) を参照してください。以下の例で、*斜体*&#x200B;の部分には実際の情報が入ります。

### オプトアウト(お [!UICONTROL CID] よび [!UICONTROL CID_IC]

説明と構文については、[宣言された ID の URL 変数および構文](../features/declared-ids.md#variables-and-syntax)を参照してください。

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> オプトアウト方法 </th> 
   <th colname="col2" class="entry"> コードサンプル </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>データプロバイダー ID およびユーザー ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>統合コードおよびユーザー ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>複数の <code> d_cid </code> および <code> d_cid_ic </code> のキー値ペア </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### オプトアウト( [!UICONTROL DPID]、 [!UICONTROL DPUUID]および [!UICONTROL UUID] （廃止）

これらの方法はまだ機能しますが、既に非推奨（廃止予定）となっています。この情報は、従来手法の参考などのために提供するものです。従来のオプトアウト方法は次のとおりです。

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> オプトアウト（廃止予定） </th> 
   <th colname="col2" class="entry"> コードサンプル </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> のみ </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>パートナーレベルのオプトアウト </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>パートナーレベルのオプトアウトは、この <code> dpid </code> + <code> dpuuid </code> ペアの AAM UUID への最新マッピングに対して保存されます。既存のマッピングがなければ、Audience Manager は、リクエストの Cookie に AAM UUID が含まれているかどうかを確認し、含まれていれば、それを使用してオプトアウトを保存します。含まれていなければ、Audience Manager は新規の AAM UUID を生成し、それについてオプトアウトを保存します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> および明示的な <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> が常に優先します。<code> dpid </code> + <code> dpuuid </code> の組み合わせが別の AAM UUID にマッピングされていても、オプトアウトは、リクエスト（<code> d_uuid </code>）で渡された AAM UUID に保存されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 変数と構文 [!UICONTROL Declared IDs] {#variables-and-syntax}

以下の表に、[!DNL Audience Manager] でデータプロバイダー ID およびユーザー ID または統合コード（使用する場合）を渡すキー値ペアを示します。なお、*斜体*&#x200B;の部分には実際の情報が入ります。読みやすくするために、スペースが追加されています。

それぞれのキー値ペアでは、以下がおこなわれます。

* キーとそれに関連する値が `=` 記号で区切られます。
* 非表示[!DNL ASCII]文字`%01`で値が区切られます。

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>データプロバイダー ID とそれに関連する一意のユーザー ID が単一のキー値ペアとして含まれています。<code> d_cid </code> は、（非推奨と見なされるが、まだサポートされている）<code> d_dpid </code> および <code> d_dpuuid </code> に代わるものです。詳しくは、<a href="../reference/cid.md">DPID と DPUUID に代わる CID</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>統合コードとそれに関連する一意のユーザー ID が単一のキー値ペアとして含まれています。<code> d_cid_ic </code> は、（廃止予定だが、まだサポートされている）<code> d_dpid </code> および <code> d_dpuuid </code> に代わるものです。詳しくは、<a href="../reference/cid.md">DPID と DPUUID に代わる CID</a> を参照してください。 </p> </td> 
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
   <td colname="col1"> <p>データプロバイダー ID およびユーザー ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>統合コードおよびユーザー ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>複数の <code> d_cid </code> および <code> d_cid_ic </code> のキー値ペア </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] 変数 {#declared-id-variables}

Describes the configuration variables used to pass [!UICONTROL declared IDs] through [!UICONTROL DIL] to [!DNL Audience Manager.]

## [!UICONTROL DIL] を使用し [!DNL Adobe Experience Platform Identity Service] てパス [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

[Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を使用する場合、非推奨（廃止予定）の `dpid` 変数と `dpuuid` 変数を使用して [!UICONTROL declared IDs] を渡す必要はありません。代わりに、`visitorService` 関数に依存する現在のバージョンの [!UICONTROL DIL] を使用して、[!UICONTROL Adobe Experience Platform Identity Service] の `setCustomerIDs` 関数から [!UICONTROL declared IDs] を取得します。詳しくは、[顧客 ID と認証状態](https://docs.adobe.com/content/help/ja-JP/id-service/using/reference/authenticated-state.html)を参照してください。次のように、`DIL.create` で `visitorService` を呼び出します。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

キー値ペア `namespace` で、`MCORG` は [!DNL Experience Cloud] の組織 ID です。この ID がわからない場合、[!DNL Experience Cloud] ダッシュボードの「[!UICONTROL Administration]」セクションで確認できます。このダッシュボードを表示するには、管理者権限が必要です。[管理：コアサービス](https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/core-services.html)も参照してください。

## 非推奨（廃止予定）の関数 {#deprecated-functions}

[!UICONTROL DIL] の最新バージョン（6.2 以降）では、これらのキー値ペアを使用して [!UICONTROL declared IDs] を渡す必要はありません。これは、[!UICONTROL DIL] が上記のコードサンプルのように `visitorService` 関数を使用しているためです。この関数は [!UICONTROL Adobe Experience Platform Identity Service] から [!UICONTROL declared IDs] を取得します。ここでは、これらの変数を、履歴やレガシーを示す目的で参照しています。以下のコードは、`DIL.create` を設定して [!UICONTROL Visitor ID Service] から [!UICONTROL declared ID] を取得する方法の例を示しています。次の表は、`declaredId` オブジェクトで使用されるレガシー変数の一覧です。

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

### [!UICONTROL DPID] および [!UICONTROL DPUUID]

[!DNL Audience Manager] は結合された `DPID` と `DPUUID` を、システム内の対応するユーザー ID と比較して照合します。If an ID does not exist, [!DNL Audience Manager] creates a new user ID and synchronizes it to the `DPID/DPUUID` combination. Once [!DNL Audience Manager] matches or creates a user ID (the `UUID`) it returns that ID in the [!DNL JSON] response to the [!DNL cookie] in the client&#39;s domain (first-party [!DNL cookie]) or other local storage.

[!UICONTROL DIL] v6.1 以前を使用している場合には、この関数を呼び出します。新しいバージョンでは [!DNL Adobe Experience Platform Identity Service] から [!UICONTROL declared IDs] を取得するので、この関数は非推奨（廃止予定）となっています。

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>You need to programmatically develop the code that supplies the ID values for the `d_dpuuid` and `d_dpid` keys.

### Pass In IDs After [!UICONTROL DIL] Instantiates

>[!NOTE]
>
>異なる `declaredID` の組み合わせで [!DNL API] 呼び出しをおこなう場合、この新しい組み合わせはその呼び出しでしか使用されません。その後の通常のイベント呼び出しでは、元の `DIL.create` `declaredID` の組み合わせが使用されます。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## リクエストとレスポンスの例 {#request-response-examples}

The request sends a data provider and user ID to [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

次のレスポンスでは、Audience Manager ID（`UUID` など）が返され、ページドメインのファーストパーティ Cookie に書き込まれます。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## ターゲティングからの除外 {#do-not-target}

[!UICONTROL declared ID] の処理では、サイト訪問者の環境設定に従って、 によるターゲティングを Web サイトでオプトアウトすることができます。[!DNL Audience Manager]When [!DNL Audience Manager] receives an opt-out request, the [!DNL DCS] returns an empty [!DNL JSON] object instead of the [!DNL Audience Manager] user ID.

>[!MORELIKETHIS]
>
>* [DPID と DPUUID に代わる CID](../reference/cid.md)

