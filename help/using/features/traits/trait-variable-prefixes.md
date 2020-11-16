---
description: ここでは、特性ルールを作成する際にキー変数に付ける必要があるプレフィックスについて説明します。
seo-description: ここでは、特性ルールを作成する際にキー変数に付ける必要があるプレフィックスについて説明します。
seo-title: キー変数のプレフィックスに関する要件
solution: Audience Manager
title: キー変数のプレフィックスに関する要件
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
translation-type: tm+mt
source-git-commit: 1c0d40082cd0753a9b4326aae764eb74aefb8be4
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 100%

---


# キー変数のプレフィックスに関する要件 {#prefix-requirements-for-key-variables}

ここでは、特性ルールを作成する際にキー変数に付ける必要があるプレフィックスについて説明します。

<!-- r_tb_variable_prefixes.xml -->

## キー変数のプレフィックスの目的

[!UICONTROL Trait Builder]ルールを作成する場合、推奨されるプレフィックスをキー変数の先頭に付加する必要があります。これらのプレフィックスは渡されたデータの種類を判別するためのもので、[!DNL Audience Manager] 内での名前空間の競合を防ぐことができます。一般的に、変数には任意の名前を指定できます。ただし、キー変数の名前がイベント呼び出しの変数名と一致しない場合、ルールのデータは処理されません。

## キー変数のプレフィックス

次の表は、[!UICONTROL Trait Builder]で使用される一般的なプレフィックスのリストです。

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> キー変数のプレフィックス </th> 
   <th colname="col2" class="entry"> 表している変数 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>顧客特有。これは独自のプロパティから送信されるキーデータです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> レベル。このデータは <span class="keyword">Audience Manager</span> エコシステム内で共通です。より包括的なリストについては、<a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md">DCS API 呼び出しでサポートされている属性</a>を参照してください。</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p><a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html">HTTP ヘッダー</a>の情報が格納されています。<code> referer</code>、<code> IP</code>、<code> accept-language</code> などのヘッダーパラメーターがあります。 </p> <p> <p>注意：9.0 より前のバージョンの DIL を使用しているお客様の場合、Safari ブラウザーでは <code> h_referer</code> シグナルを使用したデータ収集は機能しません。<a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external">ITP 2.0</a> の導入により、Safari ブラウザーでは、demdex.net ドメインをトラッカーとして分類する可能性があり、データ収集要求のリファラーを切り詰めて、完全な URL ではなく要求元のみ含まれるようにします。最新バージョンの DIL については、<a href="../../dil/dil-overview.md#get-implement-dil-code">DIL コードの取得と実装</a>を参照してください。<p>このプレフィックスを使用するシグナルは、<a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">シグナル検索</a>では表示されません。</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p><span class="wintitle">データ収集サーバー</span>ではプライベートパラメーターを渡すことができます。基本的に、<code> p_</code> で始まるパラメーターは特性の評価に使用されますが、下流でログに記録されることはなく、保存もされません。 </p> <p>例：<code> /event?p_age=23</code> であり、特性が <code> YoungPeople = p_age &lt; 25</code> である場合、この特性は認識されますが、キーと値のペア <code> p_age=23</code> はリクエストの後で破棄され、ログには記録されません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [基本情報の概要](../../features/traits/create-onboarded-rule-based-traits.md)
>* [特性ルールの管理](../../features/traits/manage-trait-rules.md#managing-trait-rules)

