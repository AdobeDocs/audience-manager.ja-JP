---
description: 受信する特性データファイルの形式を整える際に従うべき必須フィールド、構文、ルールについて説明します。
seo-description: 受信する特性データファイルの形式を整える際に従うべき必須フィールド、構文、ルールについて説明します。
seo-title: 受信データファイルコンテンツ：構文、無効な文字、変数、例
solution: Audience Manager
title: 受信データファイルコンテンツ：構文、無効な文字、変数、例
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 82%

---


# 受信データファイルコンテンツ：構文、無効な文字、変数、例 {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

受信する特性データファイルの形式を整える際に従うべき必須フィールド、構文、ルールについて説明します。

## ファイルコンテンツの構文 {#file-content-syntax}

受信データファイルのフィールドは、以下の順序でなければなりません。この例では、各要素を視覚的に区切るために`<``>`記号が追加されています。実際のデータファイルでこれを使用する必要はありません。

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

使用可能なその他のファイルコンテンツ形式については、[カスタムパートナー統合](/help/using/integration/sending-audience-data/custom-partner-integrations.md)を参照してください。

>[!NOTE]
>
>受信データファイルで送信する各ユーザー ID について、処理できる行数の上限は 200 行です。例えば、あるユーザー ID について 300 行が送信された場合、最初の 200 行は保持されますが、残りの 100 行は破棄されます。以下の例では、ユーザー ID 1 とユーザー ID 2 のそれぞれについて送信されている行が 3 行なので、問題はありません。1 行に含まれる特性やキーと値のペアの数には、制限はありません。
>
>
```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## 定義済みのファイル変数 {#file-variables-defined}

次の表は、形式が適切に設定された受信データファイルで使用される変数の一覧と定義です。*斜体*&#x200B;の部分には実際の情報が入ります。

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>ユーザー ID は次のいずれかに該当します。 </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B"><span class="keyword">Audience Manager</span> により割り当てられた一意のユーザー ID（<a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>）。 </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">CRM システムで割り当てられた一意のユーザー ID（<a href="../../../reference/ids-in-aam.md">Audience Manager の DPUUID</a>）。 </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">モバイル Android または iOS デバイス ID（モバイルオペレーティングシステムで表示される、元のままの形式）。 </li> 
     </ul> </p> <p>モバイル ID については、以下の点にも注意してください。 </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA 形式：ID は大文字でなければなりません。また、ハッシュしてはいけません。例：<code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android 形式：ID は小文字でなければなりません。また、ハッシュしてはいけません。例：<code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>ユーザー ID と特性 ID は 1 つのタブを区切り文字として区切ります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> 特性 ID。受信データファイルには<i>転送された特性のみ</i>を入れるようにしてください。受信データ転送では、他の特性タイプは処理されません。 </p> <p> <p>注意：特性 ID を確認するには、すべての特性の詳細を返す GET メソッドを使用します。詳しくは、<a href="../../../api/rest-api-main/api-traits.md">特性 API メソッド</a>を参照してください。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 形式 [!UICONTROL Trait IDs] {#formatting-trait-ids}

The following table describes the prefixes that identify [!UICONTROL trait] names or IDs in an inbound data file. 例については[サンプルファイル](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples)を参照してください。

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> プレフィックス </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p><code> d_sid </code> というプレフィックスは、ID が <span class="keyword">Audience Manager</span> の特性 ID であることを表します。これはユーザーインターフェイスに表示される ID と同じです。特性 ID は API <code> GET </code> メソッドを使用して返すこともできます。詳しくは、<a href="../../../api/rest-api-main/api-traits.md">特性 API メソッド</a>を参照してください。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>データに <code> d_unsid </code> というプレフィックスを付けると、ユーザーがその特性から削除されます。<code> d_unsid </code> というプレフィックスは、<code> overwrite </code> ファイルでは無視されます。 </p> <p><code> d_unsid= </code> というプレフィックスは、ID が <span class="keyword">Audience Manager</span> の特性 ID であることを表します。これはユーザーインターフェイスに表示される ID と同じです。特性 ID は API <code> GET </code> メソッドを使用して返すこともできます。詳しくは、<a href="../../../api/rest-api-main/api-traits.md">特性 API メソッド</a>を参照してください。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules">特性ルール</a>を使用すると、特性認定の条件を設定できます。特性ルールを <code> ic == trait ID </code> と書式設定した場合、特性を簡単なコンマ区切りのリストで送信できます。 </p> <p>例えば、次の 3 つの特性ルールを作成したとします。 </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>これらの特性は <code> ic </code> キーに関連付けられます。これにより、データファイルでより簡単な特性リストを作成できます。また、<code> ic </code> というプレフィックスを使用する必要はありません。その結果、データファイルの内容は次のようになります。 </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>キーと値のペア </p> </td> 
   <td colname="col2"> <p>特性データは英数字の文字列を使用するキーと値のペアとして書式設定できます。キーと値のペアの書式設定には次のように複数の方法があります。 </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code>、<code> "gender"=m </code>、<code> model = "pickup truck" </code>、<code> product = tablet </code> は、いずれも正しく書式設定されたキーと値のペアの例です。 </p> </td> 
  </tr>
 </tbody>
</table>

## とキーと値のペアに無効な文字 [!UICONTROL Trait IDs]が含ま [!UICONTROL User IDs] れています {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] は数字のみで構成されます。 We ask that you include *only[!UICONTROL onboarded traits]* in inbound data files. We do not process any other [!UICONTROL trait] types in the inbound data transfer.

### [!UICONTROL User IDs]

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID Type </th> 
   <th colname="col2" class="entry"> 要件 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p>DPUUID では、エンコードされたコロン（ <code> %3A </code> ）やエンコードされていないコロン（ : ）を使用しないでください。<i></i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>モバイル iOS（IDFA）または Android デバイス ID </p> </td> 
   <td colname="col2"> <p>モバイルデバイス ID は次の形式を厳密に遵守していなければなりません。 </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA 形式：ID は大文字でなければなりません。また、ハッシュしてはいけません。例：<code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android 形式：ID は小文字でなければなりません。また、ハッシュしてはいけません。例：<code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### キーと値のペア

キーと値のペアで、値の名前が正しく書式設定されていない場合も、問題が発生します。キーと値のペアの値を作成する場合、または値の名前を設定する場合は、以下のルールに従ってください。

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文字 </th> 
   <th colname="col2" class="entry"> 要件 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>引用符（"） </p> </td> 
   <td colname="col2"> <p>引用符は、キーと値のペアのキーと値の部分に使用できます。例えば、次のようにできます。 </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ダッシュ（-） </p> </td> 
   <td colname="col2"> <p>キーの先頭にあるダッシュは無視されます。例えば、「<code> -product = camera </code>」は「<code> product = camera </code>」と解釈されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>キーと値のペアでは、空の値の代わりに <i></i><code> TAB </code> を使用しないでください。<code> TAB </code> は受信データファイルで変数を区切る場合にのみ使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>キーや値に改行文字やタブ文字（<code> \n, \t </code>）は使用しないでください。 </p> </td> 
  </tr>
 </tbody>
</table>

## データファイルの例 {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> データファイル形式 </th> 
   <th colname="col2" class="entry"> 説明と例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_sid </code> または <code> d_unsid </code> を使用 </p> </td> 
   <td colname="col2"> <p>このデータファイルは、特性 24、26、27 について認定され、特性 28、29 から削除されたユーザーを示しています。 </p> <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>注意：  <p>d_unsid を使用する代わりに、次の構文を使用してユーザープロファイルから特性を削除することもできます。 </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> ic== </code> を使用 </p> </td> 
   <td colname="col2"> <p>これらの特性は、<code> ic </code> というプレフィックスで特性ルールに追加されています。そのため、次のように、コンマ区切りのデータファイルに追加することができます。タブは UUID と特性 ID を区切ります。<code> ic </code> というプレフィックスはファイルでは必要ありません。 </p> <p><b>数値 ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>文字列 ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>キーと値のペアを使用 </p> </td> 
   <td colname="col2"> このファイルデータは、キーと値のペアを使用して、データを <span class="keyword">Audience Manager</span> に渡します。 <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

他の例が必要な場合は、サンプルデータファイルを[ダウンロードします](assets/ftp_dpm_1234_1445374061.overwrite)。ダウンロードファイルの拡張子は `.overwrite` です。これは普通のテキストエディターで開くことができます。

## 例の一覧 {#examples-matrix}

The chart below shows examples of the correct way to format your Inbound files, depending on the [type of IDs](../../../reference/ids-in-aam.md) and the method by which you want to add [!UICONTROL traits] to profiles.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID タイプ／操作 </th> 
   <th colname="col2" class="entry"> d_sid を使用して特性をユーザープロファイルに追加する </th> 
   <th colname="col3" class="entry"> d_unsid を使用して特性をユーザープロファイルから削除する </th> 
   <th colname="col4" class="entry"> キーと値のペアを送信して特性をユーザープロファイルに追加する </th> 
   <th colname="col5" class="entry"> ic プレフィックスを使用して特性をユーザープロファイルに追加する </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> 例 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> 例 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> 例 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> 例 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Android デバイス用の Google 広告 ID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> 例 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> 例 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> 例 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> 例 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>iOS デバイス用の Apple IDFA </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9">例 9</a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> 例 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> 例 11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> 例 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>独自の CRM ID（DPUUID） </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> 例 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> 例 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> 例 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> 例 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 例 1 {#example-1}

の [!UICONTROL trait IDs] 資格情報 [!UICONTROL trait] を送信するために使用し [!DNL Audience Manager][!DNL UUIDs]ます。

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### 例 2 {#example-2}

の [!UICONTROL trait IDs] 欠格情報を送信するために使用 [!UICONTROL trait] し [!DNL Audience Manager][!DNL UUIDs]ます。

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

 または

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

 または

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### 例 3 {#example-3}

Send in key-value pairs to add [!UICONTROL trait] qualification information for [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

 または

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### 例 4 {#example-4}

プレフィックスを使用して、の `ic` 資格情報を送信 [!UICONTROL trait][!DNL Audience Manager][!DNL UUIDs]します。

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

 または

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### 例 5 {#example-5}

デバイス [!UICONTROL trait IDs] の [!UICONTROL trait] 資格情報を送信するために使用し [!DNL Android] ます。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 例 6 {#example-6}

デバイス [!UICONTROL trait IDs] の [!UICONTROL trait] 欠格情報を送信するために使用し [!DNL Android] ます。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

 または

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

 または

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### 例 7 {#example-7}

Send in key-value pairs to add [!UICONTROL trait] qualification information for [!DNL Android] devices.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

 または

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### 例 8 {#example-8}

Use the `ic` prefix to send [!UICONTROL trait] qualification information for [!DNL Android] devices.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

 または

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### 例 9 {#example-9}

デバイス [!UICONTROL trait IDs] の [!UICONTROL trait] 資格情報を送信するために使用し [!DNL iOS] ます。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 例 10 {#example-10}

デバイス [!UICONTROL trait IDs] の [!UICONTROL trait] 欠格情報を送信するために使用し [!DNL iOS] ます。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

 または

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

 または

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### 例 11 {#example-11}

Send in key-value pairs to add [!UICONTROL trait] qualification information for [!DNL iOS] devices.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

 または

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### 例 12 {#example-12}

Use the `ic` prefix to send [!UICONTROL trait] qualification information for [!DNL iOS] devices.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

 または

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### 例 13 {#example-13}

の資格情報 [!UICONTROL trait IDs] を送信するために使用し [!UICONTROL trait][!DNL DPUUIDs]ます。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 例 14 {#example-14}

の [!UICONTROL trait IDs] 欠格情報の送信に使用し [!UICONTROL trait][!DNL DPUUIDs]ます。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

 または

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

 または

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### 例 15 {#example-15}

Send in key-value pairs to add [!UICONTROL trait] qualification information for [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

 または

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### 例 16 {#example-16}

Use the `ic` prefix to send [!UICONTROL trait] qualification information for [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

 または

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [特性ビルダー](../../../features/traits/about-trait-builder.md)

