---
description: 送信テンプレートの作成に使用できるマクロの一覧を示します。ファイル名マクロ、ヘッダーマクロ、コンテンツマクロなどがあります。
seo-description: 送信テンプレートの作成に使用できるマクロの一覧を示します。ファイル名マクロ、ヘッダーマクロ、コンテンツマクロなどがあります。
seo-title: 送信テンプレートマクロ
solution: Audience Manager
title: 送信テンプレートマクロ
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: 31366fb83fc9aaeffc6d4a078dc2e07a0fd727a4
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 99%

---


# 送信テンプレートマクロ {#outbound-template-macros}

送信テンプレートの作成に使用できるマクロの一覧を示します。ファイル名マクロ、ヘッダーマクロ、コンテンツマクロなどがあります。

## ファイル名およびファイルヘッダーマクロ {#file-name-header-macros}

次の表は、ファイル名で使用できるマクロと、ヘッダーのフィールドを定義するためのマクロの一覧と説明です。コードのサンプルについては、[送信マクロの例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)を参照してください。

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> マクロ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>非表示の ASCII 文字。コンテンツの行またはセクションの開始を表します。ファイル内のデータ列を区切る場合にも使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>データプロバイダー ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>ユーザー ID キーデータプロバイダー ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> アウトバウンド注文での複数行ヘッダーの作成を許可します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>オーダー／宛先 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>オーダー／宛先 ID のエイリアス。 </p> <p>このエイリアスは管理 UI で設定します。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>送信ファイルを複数の部分に分割することを示します。ファイル名の SPLITNUM セクションに部品番号に置き換え、先頭にゼロを付けて SPLITNUM セクションの文字が 3 文字以上になるようにします。</p>
   <p>SPLITNUM マクロは、&lt;&gt; 文字で囲む必要はありません。</p><p>例：<code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_9999_full_1566906141003.csv</p> 
<p>上記の例の最後の 3 桁（001、002、003）は、SPLITNUM 識別子です。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>同期タイプを表し、以下の値を取ります。 </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>：完全同期。 </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>：増分同期。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>データ転送方法を表し、以下の値を取ります。 </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>このマクロはフィールド間の区切り文字としてタブを挿入します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>10 桁の UTC を示す Unix タイムスタンプ。 </p> <p>Java の日付／タイムスタンプ形式ルールに従って <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> という形式にすることもできます。 </p> </td> 
  </tr>

</tbody> 
</table>

## コンテンツマクロ {#content-macros}

データファイルのコンテンツの書式設定に使用するマクロ。コードのサンプルについては、[送信マクロの例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)を参照してください。

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> マクロ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Inserts a close curly bracket <code>}</code> character. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> データプロバイダー個別ユーザー識別子 </span>。 </p> <p>これは送信ファイルでのデータの宛先となるデータパートナーの ID です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>1 件のデータパートナーに対する複数の ID が含まれるリストを返します。複数の下位部門や、その他の組織グループがある大規模な組織でデータ共有が可能な場合に便利です。このマクロは、これらの下位グループの ID のリストを返します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>データプロバイダー ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>このマクロの出力では、データプロバイダー ID（DPID）が関連する一意のユーザー ID（DPUUID）にマッピングされます。このマクロには、出力を制御するための書式設定文字列が必要です。出力例として次のようなものが挙げられます。 </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p><code> maxMappings </code> 設定により、マクロが返すマッピングの数が決定されます。<code> maxMappings=0 </code> の場合、このマクロは指定された各 DPID のすべてのマッピングを返します。データはタイムスタンプを基準に並べ替えられ（最新のものが最初となります）、最も値が大きいタイムスタンプの結果が最初に返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>マクロを組み合わせると、ユーザーが属し、かつユーザーが削除されたセグメントのリストを表示する条件文が作成されます。いずれかの条件が満たされない場合、またはデータがない場合、空の文字列が返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Adobe Experience Cloud</span> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>開き波括弧 { を挿入します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>廃止されました。使用しないでください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>オーダー／宛先 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>廃止されました。使用しないでください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p><code> 1 </code> を静的な、ハードコーディングされた値として返します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>パートナー ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>オーダー／宛先 ID のエイリアス。 </p> <p>このエイリアスは管理 UI で設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>削除されたセグメントがあれば、そのリストを返します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>セグメントのリストを返します。次のオプションの引数を使用できます。 </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>：セグメント ID。廃止されました。<code> sid </code> を使用します。 </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>：顧客セグメント ID。廃止されました。<code> sid </code> を使用します。 </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>：セグメント ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>：<code> 5 </code> を静的なハードコーディングされた値として返します。これはデータをセグメントデータとして識別する値です。 </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>：廃止されました。使用しないでください。 </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>：セグメントが最後に認識された時点を示す Unix タイムスタンプ。 </li> 
    </ul> <p>この変数は、マクロの後に波括弧で囲みます。例えば、<code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> のように、このコードは結果をパイプ（ | ）で区切ります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p><code> 1 </code> を静的な、ハードコーディングされた値として返します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>同期タイプを表し、以下の値を取ります。 </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>：完全同期。 </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>：増分同期。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>データ転送方法を表し、以下の値を取ります。 </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>このマクロはフィールド間の区切り文字としてタブを挿入します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>特性のリストを返します。次のオプションの引数を使用できます。 </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>：特性タイプを数値 ID で識別します。戻り値： 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code>：DPM 特性（オフライン、インバウンドジョブで転送されたジョブ）を表します。 </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code>：ルールベースの特性（リアルタイム、DCS から転送）を表します。 </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>：特性 ID。 </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>：特性が最後に認識された時点。Unix タイムスタンプです。 </li> 
    </ul> <p>この変数は、マクロの後に波括弧で囲みます。例えば、<code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> のように、このコードは結果をパイプ（ | ）で区切ります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Audience Manager</span> ユーザー ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [送信マクロの例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

