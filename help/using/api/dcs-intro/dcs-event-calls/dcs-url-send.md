---
description: DCS への /event 呼び出しの実行については、ここから始めてください。この節では、呼び出しの構文、パラメーター、形式、要求例について説明します。
seo-description: DCS への /event 呼び出しの実行については、ここから始めてください。この節では、呼び出しの構文、パラメーター、形式、要求例について説明します。
seo-title: DCS へのデータ送信
solution: Audience Manager
title: DCS へのデータ送信
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
translation-type: ht
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: ht
source-wordcount: '421'
ht-degree: 100%

---


# DCS へのデータ送信 {#send-data-to-the-dcs}

[!DNL DCS] への `/event` 呼び出しの実行については、ここから始めてください。この節では、呼び出しの構文、パラメーター、形式、要求例について説明します。

>[!NOTE]
>
>コードと例の&#x200B;*斜体*&#x200B;の部分は変数のプレースホルダーです。この方法で [!DNL DCS] にデータを送信する際には、プレースホルダーを実際の値に置き換えてください。

## 呼び出しの構文 {#dcs-call-syntax}

`URL` にデータを送信する基本的な [!DNL DCS] 文字列の構文は次のとおりです。

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>[!DNL DCS] メソッドを使用して `POST` にデータを送信することもできます。呼び出し構文については、[DCS API メソッド](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)で説明されています。

## 呼び出しパラメーター {#dcs-call-parameters}

単純な [!DNL DCS] 呼び出しの基本的な構成要素を次の表で定義します。

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> コンポーネント </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>この部分には次の情報が含まれています。 </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9"><span class="keyword">Audience Manager</span> から割り当てられたドメインエイリアス（例：<code> my_domain.demdex.net</code>）。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">宛先のドメイン（常に <code> demdex.net</code>）。<a href="../../../reference/demdex-calls.md">Demdex ドメインの呼び出しについて</a>を参照してください。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>この部分は次の働きをします。 </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">呼び出しをイベント呼び出しとして識別する。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198"><span class="wintitle">DCS</span> に送信するデータを含んだ URL 文字列の開始を定義する。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>キーと値のペアに含まれている一意の識別子。 </p> <p>これらのキーと値のペアでは、<span class="wintitle">DCS</span> に送信するデータのタイプを識別する特定のプレフィックスを使用します。詳しくは、<a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md">DCS API 呼び出しでサポートされる属性</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>キーと値のペアのキーで定義されるセットに属する変数値。 </p> <p>値を扱う際は次の点に留意してください。 </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">文字列データを二重引用符で囲みます（例：<code> age="41 to 55"</code>）。 </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">1 つの値で複数のキーを渡すことができます（例：<i><code>key</i>=<i>val1,val2,val3</i></code></i>）。 </li> 
     </ul> </p> <p><a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md">DCS 呼び出しでのキーと値のペアの形式</a>を参照してください。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>オプションの応答パラメーターです。 </p> <p> これらはどれも <span class="wintitle">DCS</span> へのデータ送信には不要です。ただし、<span class="wintitle">DCS</span> からの応答が必要な場合は、要求に <code> d_rtbd=json</code> を含める必要があります。 </p> <p><a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes">定義済みの d_ キーと値のペア</a>を参照してください。 </p> </td> 
  </tr>
 </tbody>
</table>

## サンプル呼び出し {#dcs-sample-call}

この例では架空の企業 [!DNL Acme, Inc.] 社が 呼び出しを通じて [!DNL DCS] にデータを送信しています。[!DNL HTTP]この呼び出しにはオプションパラメーター `d_dst=1`、`d_rtbd=json`、`d_cb=callback` が含まれています。これらのパラメーターは、[!DNL Acme] 社がコールバック関数で [!DNL JSON] から [!DNL DCS] 応答を受信しようとしていることを示しています。なお、これは例にすぎません。このコードを他の用途にそのまま使用しないでください。

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 次の手順 {#dcs-next-steps}

これで [!DNL DCS] へのデータ送信の方法がわかったので、今度は、DCS からの応答データを取得してその情報を解析する方法を見てみましょう。[DCS からのデータ受信](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)を参照してください。

>[!MORELIKETHIS]
>
>* [キーと値のペアの解説](../../../reference/key-value-pairs-explained.md)

