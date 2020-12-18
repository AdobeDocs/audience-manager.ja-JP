---
description: 宛先 URL に追加できるマクロについて説明します。
seo-description: 宛先 URL に追加できるマクロについて説明します。
seo-title: 宛先マクロの定義
solution: Audience Manager
title: 宛先マクロの定義
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
translation-type: ht
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: ht
source-wordcount: '667'
ht-degree: 100%

---


# 宛先マクロの定義 {#destination-macros-defined}

宛先 [!DNL URL] に追加できるマクロについて説明します。

<!-- destination-macros.xml -->

[!DNL URL] の宛先を作成する際には、[!DNL URL] 文字列に次のマクロを挿入することができます。宛先 [!DNL URL] 内での適切なマクロ配置については、データ／宛先パートナーにお問い合わせください。

>[!NOTE]
>
>他に指示がない限り、マクロはオプションです。*斜体*&#x200B;の部分には実際の情報が入ります。

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> マクロ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>必須。 </p> <p>宛先 URL でのマッピングされたセグメント値の位置を定義します。通常、これは<i>セグメント ID</i> ですが、統合コードでもかまいません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>ユーザーの <span class="keyword">Audience Manager</span> ID を宛先 URL に挿入します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p><i> データソース ID</i> は、マクロに渡されるデータソースの識別子に対応します。 </p> <p>このマクロの動作を簡単な例で見てみましょう。ここでは、次の ID と条件を持つ <span class="keyword">Audience Manager</span> パートナーがいるとします。 </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">データソース ID：<code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">内部の顧客 ID：<code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">宣言された ID：パートナーはこれらの値を宣言された ID <code> 1:CustomerABC</code> として渡します。 </li> 
    </ul> <p>これを <code>%dpid_<i>data source id</i>%</code> でおこなうには、<span class="keyword">Audience Manager</span> パートナーは、次のような形式でマクロを設定します。 </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>このマクロは <code> 1</code> を <code> CustomerABC</code> に置き換えます。 </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>GDPR 規制が訪問者に適用されるかどうかを示します。このマクロを使用して、IAB と統合された URL 宛先へ送信されるセグメントに、同意を含めます。詳しくは、<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF 用 Audience Manager プラグイン</a>を参照してください。</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>訪問者がサイトで同意を提供または拒否した場合に収集される同意文字列（IAB ベンダー ID を含む）。このマクロを使用して、IAB と統合された URL 宛先へ送信されるセグメントに、同意文字列を含めます。<code>XXXX</code> を宛先パートナー ID に置き換えます。詳しくは、<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF 用 Audience Manager プラグイン</a>を参照してください。 </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>親 Web ページで使用されているプロトコルを検出し、それを宛先 URL に挿入します。例：<br>
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">Web ページが <b>https</b>://aam_client.com の場合、このマクロは <b>https</b>://url-destination.com に置換されます。 </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">Web ページが <b>http</b>://aam_client.com の場合、このマクロは <b>http</b>://url-destination.com に置換されます。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Experience Cloud</span> ID を宛先 URL に挿入します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">データ収集サーバー（DCS）</span>地域を宛先 URL に挿入します。遅延を最小限に抑えるために、訪問者が <span class="keyword">Audience Manager</span> への HTTP 呼び出しをおこなうと、その呼び出しは最も近い <span class="wintitle">DCS</span> データセンターにリダイレクトされます。これは DNS を通じて実現されます。DNS は訪問者の場所を検出し、呼び出しを適切なデータセンターにリダイレクトすることができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>宛先 URL に乱数を挿入することで、キャッシュバスティング機能を実行します。これにより、ブラウザーはキャッシュしたコンテンツを提供しなくなります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>宛先 URL に UNIX タイムスタンプを挿入して、ブラウザーがキャッシュしたコンテンツを提供できないようにします。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 宛先マクロを使用したキャッシュバスティング {#destination-cache-busting}

`%rnd%` および `%timestamp%` マクロは、[!DNL URL] 文字列に一意の値を挿入して、ブラウザーのキャッシュ操作を防ぎます。

## `%rnd%` および `%timestamp%` を使用したキャッシュバスティング {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

ブラウザーキャッシュは、頻繁に要求されるコンテンツをメモリにキャッシュ（保存）します。ページが読み込まれる際に、リモートサーバーではなくキャッシュから、保存したコンテンツが提供されます。この処理は、データが別の場所からではなくローカルで提供されるので、効率的なダウンロード時間を維持するのに役立ちます。ただし、キャッシュ操作はサーバー呼び出しを必要としないので、個別リクエストの数が人為的に少なくなり、レポートが歪曲されるおそれがあります。

キャッシュバスティングは、ブラウザーがコンテンツを保存および再利用するのを防ぎます。この手法では、乱数またはタイムスタンプを URL 文字列に挿入するコードを使用して、URL をブラウザーに一意のものに見せます。結果として、それぞれの `HTTP` 呼び出しがサーバーに対する別個のリクエストとしてカウントされます。リクエストごとに新しいサーバー呼び出しを強制することにより、レポートの精度を維持し、食い違いを減らします。[!DNL Audience Manager] には、キャッシュバスティング用の 2 つのマクロが用意されています。

* `%rnd%`：URL に乱数を挿入します。
* `%timestamp%`：URL に UNIX 日付／時間を挿入します。

## `%rnd%` と `%timestamp%` の比較 {#compare-rnd-timestamp}

どちらのマクロもキャッシュを防ぎますが、`%rnd%` のほうがより効率的な可能性があります。例えば、`%timestamp%` を使用すると、複数のユーザーがページを同時に表示する場合、同じ日付／時刻値を取得します。結果として、[!DNL URL] は一意でなくなり、複数の呼び出しが 1 回のみカウントされます。しかし、`%rnd%` は、（ユーザーが同じページを同時に表示したとしても）呼び出しごとに一意の数値を生成します。これは、[!DNL URL] 文字列に異なる値が含まれ、個別のものとしてカウントされることを意味します。

>[!MORELIKETHIS]
>
>* [宛先マクロの定義](../../features/destinations/destination-macros.md#destination-macros-defined)