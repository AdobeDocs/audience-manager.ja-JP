---
description: DIL.modules 名前空間のメソッドについて説明します。これらのモジュールを使用すると、データの収集や Audience Manager オブジェクトの操作をプログラムでおこなうことができます。
seo-description: DIL.modules 名前空間のメソッドについて説明します。これらのモジュールを使用すると、データの収集や Audience Manager オブジェクトの操作をプログラムでおこなうことができます。
seo-title: DIL モジュール
solution: Audience Manager
title: DIL モジュール
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL の実装
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 100%

---

# DIL モジュール {#dil-modules}

`DIL.modules` 名前空間のメソッドについて説明します。これらのモジュールを使用すると、データの収集や Audience Manager オブジェクトの操作をプログラムでおこなうことができます。

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

[!UICONTROL DIL] と連携して、[!DNL Analytics] のタグ要素（変数、prop、eVar など）をAudience Manager に送信します。データをコンマ区切りリストで返します。バージョン 2.6 で使用できます。

**関数シグネチャ：**`DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>このコードは、ページ上で `s.t();` 関数よりも&#x200B;*前*&#x200B;に配置する必要があります。

<!-- 

r_dil_sc_init.xml

 -->

**パラメーター**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名前 </th> 
   <th colname="col2" class="entry"> のタイプ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> 文字列 </td> 
   <td colname="col3"> <p>非列挙型の <span class="keyword">Analytics</span> 変数（<code> pageName </code>、<code> channel </code>、<code> campaign </code>、<code> product </code> など）が格納されている、文字列の配列。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> オブジェクト </td> 
   <td colname="col3"> <p>prop や eVar のような列挙型の <span class="keyword">Analytics</span> 変数（<code> prop1 </code>、<code> prop2 </code>、<code> evar3 </code>、<code> evar4 </code> など）が格納されている、オブジェクトの配列。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> 整数 </td> 
   <td colname="col3"> <p>繰り返されている名前を何個返すかを表します。例えば、2 つの prop または evar を返すには、<code> maxIndex:2 </code> を設定します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> オブジェクト </td> 
   <td colname="col3"> <p><span class="keyword">Analytics</span> オブジェクトを表すオブジェクト。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> オブジェクト </td> 
   <td colname="col3"> <p><span class="wintitle">DIL</span> を表すオブジェクト。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> オブジェクト </td> 
   <td colname="col3"> <p>追加のオプション。 </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>他に何も指定しない場合、ピリオドはデフォルトのアンダースコア（ _ ）に置き換えられます。 </p> <p>例えば、<code> s.contextData = {abc.def = '123'} </code> は、イベント呼び出しクエリ文字列では <code> c_contextData_abc_def=123 </code> となります。 </p> <p>このオプションは <span class="wintitle">DIL</span> バージョン 5.0 以降でのみ使用できます。 </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>例えば、<code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> を実行すると、この文字列の配列がコンテキストデータのデータ収集から除外されます。このオプションでは、個人識別情報（PII）は対象外となります。 </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**siteCatalyst.init によりキャプチャされるデータ**

この関数は、次の [!DNL Analytics] プロパティの詳細を返します。

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar`（1～250）
* `prop`（1～75）
* `pe`
* `pev1`
* `pev2`
* `pev3`

**サンプルコード**

このコードにより、[!DNL Analytics] イベント（prop、eVar など）の値が存在する場合に、これらのイベントのコンマ区切りのリストが作成されます。

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

監視対象の [!DNL Analytics] データポイントを、前述の追加の関数を使用せずに追跡するには、次のように `siteCatalyst.init` を単独で呼び出します。

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

`GA.submitUniversalAnalytics();` 関数は、Google [!DNL Universal Analytics]のデータを Audience Manager に送信します。 この [!UICONTROL DIL] 関数は、`analytics.js`（Google [!DNL Universal Analytics]の最新コードライブラリ）と連携するように設計されています。

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] では、Google の `analytics.js` コードライブラリの状況把握や管理をおこないません。 Google が [!UICONTROL DIL] の新バージョンをリリースした場合は、`analytics.js` データ収集がまだ機能するかどうかを確認してください。
>
>* 従来の Google アナリティクストラッキングコード（`ga.js` や `dc.js` など）をまだ利用している場合は、`GA.submitUniversalAnalytics();` を使用できません。 代わりに [GA.init](../dil/dil-modules.md#ga-init) を参照してください。
>



**関数シグネチャ：**`DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**プロパティ**

`GA.submitUniversalAnalytics();` 関数は次のプロパティを受け取ります。

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> プロパティ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Google Analytics</span> のインスタンスを表すグローバル変数。<span class="keyword"> Google Analytics </span> コードをカスタマイズしている場合を除き、これは通常デフォルトで <code> ga </code> になっています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">DIL</span> のインスタンスを表す変数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>（オプション）</i> <code> analytics.js </code> ライブラリでは、内部プロパティは短縮された変数 <code> 'b' </code> です。この変数には <span class="keyword">Google Analytics</span>データが格納されます。 </p> <p>Google が内部変数の名前を変更しない限り、設定する必要がないので、このプロパティはオプションになっています。例えば、短縮されたこの変数が <code> 'a' </code> に変わった場合は、<code> GA.submitUniversalAnalytics(); </code> を次のように呼び出します。 </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**例**

[!DNL Google Analytics] および `ga` を呼び出す前に、まず [!UICONTROL DIL]の `GA.submitUniversalAnalytics();` オブジェクトを必ず定義してください。次のようなコードになります。

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

`GA.init()` 関数は、レガシー／廃止予定バージョンの [!DNL Google Analytics]から Audience Manager にデータを送信します。

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` は、従来の Google アナリティクストラッキングコードである `ga.js` または `dc.js` とのみ使用できます。Google [!UICONTROL DIL]の最新のコードライブラリである `analytics.js` を使用している場合、この [!DNL Universal Analytics] 関数は呼び出せません。[!DNL Audience Manager] を利用している場合に [!UICONTROL DIL] および [!DNL Universal Analytics] を使用するには、[GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics) を参照してください。

**関数シグネチャ：**`DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**パラメーター**

| 名前 | のタイプ | 説明 |
|---|---|---|
| `_gaq` | 配列 | GA コマンドが格納されている配列。 |
| `dilInstance` | オブジェクト | DIL インスタンスが格納されているオブジェクト。 |
| `trackVars` | オブジェクト | *（オプション）*`names` プロパティで構成されるオブジェクト。このプロパティは、追跡する GA コマンド名の配列です。 |

**サポートされている GA 関数呼び出し**

デフォルトでは、`GA.init` は次の関数からのデータをキャプチャします。

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL は GA データのキーを作成する**

Audience Manager はデータをキーと値のペアで受け取りますが、GA は項目を配列で処理します。GA のデータを操作するために、[!UICONTROL DIL] は自動的にキーと値のペアを作成し、`c_ <key name>` のようなキーを生成します。また、GA 配列の項目は所定の順序で配置されます。そのため、すべてのパラメーターをその順序で指定する必要があります。パラメーターにデータがない場合でも同様です。[!UICONTROL DIL] は次の GA メソッドのキーをマッピングします。

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**サンプルコード**

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 
```

監視対象のすべての GA 指標を、前述の追加の関数を使用せずに追跡するには、次のように `GA.init` を単独で呼び出します。

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**サンプルのイベント呼び出し**

Audience Manager の URL イベント呼び出しは次のようになります。

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analyticsトラッキングコード](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Web アップグレードの完了：ga.js/dc.js から analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [サイトへの analytics.js の追加](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [ga オブジェクトメソッドリファレンス](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

