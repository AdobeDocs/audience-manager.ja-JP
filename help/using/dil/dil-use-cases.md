---
description: 特定の DIL ユースケースのコードサンプルおよび説明です。
seo-description: 特定の DIL ユースケースのコードサンプルおよび説明です。
seo-title: DIL のユースケースとコードサンプル
solution: Audience Manager
title: DIL のユースケースとコードサンプル
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL の実装
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 100%

---

# DIL のユースケースとコードサンプル {#dil-use-cases-and-code-samples}

特定の DIL ユースケースのコードサンプルおよび説明です。

<!-- 

c_dil_use_case.xml

 -->

## DIL を使用した Audience Manager へのデータ要素の送信 {#send-data-elements-dil}

ページ要素に関する情報を Audience Manager に送信するオブジェクト変数を作成します。これは、一般的なデータ収集に役に立ち、Analytics 変数でデータを収集する代替手段としても有用です。

<!-- 

c_dil_send_page_objects.xml

 -->

**説明**

[!UICONTROL DIL] を使用してページデータを収集し、Audience Manager に送信する方法の例を以下のコードで示します。これらの例では、フラットリストまたは配列にデータ要素を保持する変数を使用します。変数を[キーと値のペア](../reference/key-value-pairs-explained.md)として渡すことに注意してください。また、キーと値のペアのキーの前に付いている `c_` プレフィックスにも注意してください。これは[必須のプレフィックス](../features/traits/trait-variable-prefixes.md)であり、情報がユーザー定義データであることを明示します。最初の例では、`c_` を手動でキーに付加する必要があります。2 番目の例では、[!UICONTROL DIL] がこれを自動的におこないます。

**値プロパティの一貫性の維持**

データを渡す際には、値プロパティを同じにすることを忘れないでください。例えば、2 つの同一のキーが異なる値を持つ場合、最後のキーと値のペアの値が、それより前の値オブジェクトよりも優先されます。例えば、`color:blue` と `color:red` を渡すと、返される値は red に設定されます（blue が上書きされます）。

**例 1：データをキーと値のペアとして送信**

この基本的な例では、色と価格のデータをキーと値のペアの形式で Audience Manager に送信しています。次のようなコードになります。

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**例 2：データをオブジェクトで送信**

この高度な例では、データをオブジェクトで Audience Manager に送信する方法を示します。このメソッドを扱う場合は、[!UICONTROL DIL] を使用すると、オブジェクトを関数パラメーターとして [!DNL signals()] メソッドに渡すことができます。[!UICONTROL DIL] 次のようなコードになります。

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**例 3：配列でのデータの送信**

この場合、変数 `my_object` は、配列を使用してデータを保持します。この例は、前述の推奨メソッドで渡された情報に基づいて構築されていますが、製品タイプおよびモデルに適応させるためにレイヤーを追加しています。次のようなコードになります。

<pre class="java"><code>
var my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

## 参照 URL のキャプチャ {#capture-referring-url}

参照 URL をキャプチャして Audience Manager に送信します。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>このメソッドは、ユーザーが同じプロトコル（HTTP または HTTPS）のページ間を移動する場合にのみ機能します。例えば、セキュリティで保護されたサイトから、セキュリティで保護された別のサイトに移動する場合、ブラウザーは、参照 URL を保持します。セキュリティで保護されたサイトとセキュリティで保護されていないサイトの間を移動する場合、ブラウザーは、参照 URL を保持しません。この動作は、通常のブラウザー機能であり、[!UICONTROL DIL] で回避することはできません。

**コードサンプル**

次のようなコードになります。

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## 検索エンジンのタイプおよびキーワード検索語句のキャプチャ {#capture-search-engine-types}

検索エンジンのタイプおよびキーワード検索に関する情報を Audience Manager に送信します。

>[!IMPORTANT]
>
>ここでは、最新バージョンの DIL でサポートされていない従来の機能について説明します。

**サポートされている検索エンジン**

デフォルトでは、`DIL.getSearchReferrer` は以下の検索エンジン（各国語版を含む）からの検索を認識します。

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**説明**

サポートされている任意の検索エンジンの検索リファラーを取得する方法の例を以下のコードで示します。ここでは、ユーザーが「homes」という語句を [!DNL Google] Canada（`www.google.ca`）で検索したとしましょう。このコードでは、これらの検索語句をキャプチャして Audience Manager に送信することができます。

**基本コード**

検索リファラーを（`google.com` などから）取得する基本コードは、次のようになります。

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**登録済み検索エンジンのコードサンプル**

ここでは、ユーザーが「homes」という語句を [!DNL Google] Canada（`www.google.ca`）で検索したとしましょう。コードで、検索エンジン（`c_se`）および検索語句（`c_st`）に、必須の `c_` プレフィックスが付加されていることに注意してください。`c_` は[必須のプレフィックス](../features/traits/trait-variable-prefixes.md)であり、これらが Audience Manager に対する顧客定義変数であることを明示するためのものです。

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

**未登録検索エンジンのコードサンプル**

ここでは、ユーザーが「homes」という語句を `dogpile.com` から検索したとしましょう。[!DNL Dogpile] はデフォルトではサポートされていないので、この検索エンジンを認識し検索語句を Audience Manager に返すように DIL を設定します。次のようなコードになります。

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## キーと値の他のキーへのマッピング {#map-key-values}

キーと値のペアの値を別のキーに関連付けます。

<!-- 

c_dil_map_keys.xml

 -->

**説明**

キーと値のペアでは、キーに付加された `c_` プレフィックスで、シグナルが顧客定義データとして識別されます。顧客定義データは、イベント呼び出し時のデータで渡された特定のサイト上のターゲティングに使用されます。ただし、この情報を Audience Manager アカウントのすべてのプロパティで使用可能にしたい場合があります。これをおこなうには、`c_` キーと値のペアの値をプラットフォームレベルのキーにマッピングします。プラットフォームレベルのキーには `d_` プレフィックスが付加されており、そのシグナルがアカウントのすべてのプロパティでターゲティングに使用できるようになります。

例として、特定のサイトから郵便番号データを収集し、それをすべての Audience Manager プロパティに対してターゲット設定するとします。郵便番号をプラットフォームレベルで使用できるようにするには、以下に示すように、顧客定義郵便番号キー（例：`c_zip`）をプラットフォーム定義キーにマッピングします。

**コードサンプル**

次のようなコードになります。

```java
var adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

## Google Tag Manager（GTM）での DIL とのやり取り {#traffic-dil-gtm}

GTM タグを使用して DIL を設定および提供します。

<!-- 

t_dil_google_tagmanager.xml

 -->

この手順は、[!DNL Google Tag Manager] マネージャーのアカウントと操作に関する知識があり、Audience Manager の `dil.js` ファイルを持っていることを前提としています。

GTM で `dil.js` ファイルを配信するには：

1. 新しいコンテナを作成するか、既存のコンテナを開きます。
1. 新しいタグをコンテナに追加します。
1. タグを開いて編集し、次の作業をおこないます。

   * タグの名前を設定します。
   * **[!UICONTROL Custom HTML Tag]** ドロップダウンリストから「**[!UICONTROL Tag Type]**」を選択します。
   * HTML フィールドで、[!UICONTROL DIL] コード（ライブラリとカスタムコード）をスクリプトタグ `<script>DIL code</script>` の内側に配置します。
   * 「**[!UICONTROL Save]**」をクリックします。

1. コンテナを公開します。
1. コンテナタグコードを生成し、自分のインベントリに配置します。

>[!MORELIKETHIS]
>
>* [Google タグマネージャーヘルプセンター](https://support.google.com/tagmanager#topic=3441530)
>* [シグナル](../dil/dil-instance-methods.md#signals)
* [キー変数のプレフィックスに関する要件](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

