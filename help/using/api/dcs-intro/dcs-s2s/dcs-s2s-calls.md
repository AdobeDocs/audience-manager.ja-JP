---
seo-title: サーバー間 DCS API 呼び出しの実行
solution: Audience Manager
title: サーバー間 DCS API 呼び出しの実行
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# サーバー間 DCS API 呼び出しの実行 {#making-server-to-server-dcs-api-calls}

呼び出しには、地域 DCS サーバーのホスト名とユーザー ID が必要です。必要なユーザー ID と地域 ID がない場合は、[DCS応答](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) および [エクスペリエンスクラウドからのユーザーIDおよび地域の取得](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md)を参照してください。ユーザー ID と地域 ID が用意できたら、DCS へのサーバー間呼び出しをおこなえます。構文と例については、この節を参照してください。

>[!NOTE]
>
>コードと例の*斜体*の部分は変数のプレースホルダーです。[!UICONTROL DCS] へのサーバー間呼び出しをおこなう際には、プレースホルダーを実際の値に置き換えます。

## 呼び出しの構文と例 {#call-syntax-example}

[!UICONTROL DCS] にデータを送信する基本的なサーバー間要求の構文は次のとおりです。

<pre><code>「ホスト:<i>domain alias</i>. demdex. net""https://DCS<i>hostname.demdex.net/event?d_rtbd=json&amp;d_jsonv=1&amp;d_uuid=user</i><i>ID</i>.</code>
</pre>

呼び出しのサンプルは次の例のようになります。

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## 呼び出しパラメーター {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> <i>domain alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>この部分には次の情報が含まれています。 </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Your domain alias assigned by <span class="keyword"> Audience Manager</span> (e.g., <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">The destination domain, which is always <i><code> demdex.net</code></i>. <a href="../../../reference/demdex-calls.md">Demdex ドメインの呼び出しについて</a>を参照してください。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>地域 <span class="wintitle">DCS</span> サーバーの名前を示す HTTP ヘッダーホストパラメーター。ホスト名は地域 ID に関連付けられています。だからこそ、このタイプの呼び出しをおこなうのにホスト名が必要になるのです。<a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地域 ID、場所、ホスト名</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>この部分は次の働きをします。 </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">呼び出しをイベント呼び出しとして識別する。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">DCS に送信するデータを含んだ URL 文字列の開始を定義する。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid=<i> Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> ユーザー ID 値をキー値ペアで表すための一意のユーザー ID キーです。 </p> <p><code><i>Audience Manager</i> ユーザー ID を渡す場合は、</code><span class="keyword">d_uuid</span> を使用します。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i> Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Experience Cloud</span> ユーザー ID 値をキー値ペアで表すための一意のユーザー ID キーです。詳しくは、<a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie">ID サービス Cookie からのユーザー ID の取得</a>を参照してください。 </p> <p><i>Experience Cloud<code> ID サービスから取得した </code></i>Experience Cloud<span class="keyword"> ID を渡す場合は、</span><span class="keyword">d_mid</span> を使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i> callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>オプションの応答パラメーターです。 </p> <p> これらはどれも <span class="wintitle">DCS</span> へのデータ送信には不要です。ただし、<span class="wintitle">DCS</span> からの応答が必要な場合は、要求に <i><code>d_rtbd=json</code> を含める必要があります。</i> </p> </td> 
  </tr> 
 </tbody> 
</table>

## レスポンスのサンプル {#sample-response}

[DCS からのデータ受信](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)を参照してください。
