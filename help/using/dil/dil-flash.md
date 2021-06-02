---
description: FLA ファイルから Analytics に送信されたデータを収集し、その情報を Audience Manager で使用します。
seo-description: FLA ファイルから Analytics に送信されたデータを収集し、その情報を Audience Manager で使用します。
seo-title: Flash DIL
solution: Audience Manager
title: FlashDIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL の実装
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 100%

---

# Flash DIL {#flash-dil}

FLA ファイルから Analytics に送信されたデータを収集し、その情報を Audience Manager で使用します。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] は、Audience Manager でビデオ再生データを操作するための [!DNL ActionScript] コードライブラリです。[!DNL Flash DIL] は、Adobe [!UICONTROL AppMeasurement] ライブラリが Analytics に渡す SWF コンテンツをキャプチャすることにより機能します。[!DNL Flash DIL] はデータを独立した [!UICONTROL DIL] JavaScript データ収集モジュールに送信します。この情報は Audience Manager に渡されます。Analytics データ（[!UICONTROL Props]、[!UICONTROL eVars]、イベントなど）は [!DNL FLA] ファイルからキャプチャした後、Audience Manager で特性や未使用シグナルとして使用できます。

## 区切り文字のタイプFlash DIL データ収集  {#requirements}

一般的な実装およびコード関連の要件です。

<!-- 

c_flash_dil_intro.xml

 -->

**実装要件**

[!UICONTROL Flash] データ収集には以下が必要です。

* [!UICONTROL DIL] クラスライブラリ（`dil.swc`）。パートナーソリューションの担当者から [!UICONTROL DIL] クラスライブラリを取得します。

* ページ上の JavaScript [!UICONTROL DIL] データ収集コード。
* [DIL ActionScript ライブラリ](../dil/dil-flash.md#flash-dil-actionscript)（データを収集する Flash オブジェクトに読み込まれたもの）。
* Adobe [!DNL AppMeasurement] [!DNL AS] ライブラリ（バージョン 3.5.2 以降）（データを収集する [!DNL Flash] オブジェクトに読み込まれたもの）。

**AllowScriptAccess を `Always` または`sameDomain`** に設定

SWF ファイルを読み込む HTML コードの `AllowScriptAccess` は、SWF ファイル内からの送信 URL アクセスを実行する機能を制御します。[!UICONTROL Flash DIL] データ統合を設定する場合、Flash `AllowScriptAccess` パラメーターが `always` または `sameDomain` に設定されていることを確認してください。[!UICONTROL Flash DIL] データ収集は、`AllowScriptAccess` が `never` に設定されている場合、機能しません。[スクリプトまたはホスト Web ページへのアクセスの制御](https://helpx.adobe.com/jp/flash/kb/control-access-scripts-host-web.html)を参照してください。

**JS [!UICONTROL DIL] コードの配置**

[!UICONTROL DIL] ファイルよりも前に読み込めるように、JS [!DNL FLA] データ収集モジュールをページ上に配置するようにします。[!UICONTROL DIL] データ収集の準備ができる前に、[!DNL FLA] ファイルが最初に読み込まれると、[!UICONTROL Flash DIL] がそのモジュールに送信する最初のデータシグナルを見つけられない可能性があります。ただし、インスタンス化されれば、[!UICONTROL DIL] データ収集モジュールは、[!UICONTROL Flash DIL] によって渡される後続のすべての SWF ファイルデータをキャプチャします。

## Flash DIL で収集されるデータ {#data-collected}

[!UICONTROL Flash DIL] はページ表示、リンクトラッキング、メディアトラッキング、その他のメディア表示イベントを Adobe [!UICONTROL AppMeasurement] ライブラリからキャプチャします。

<!-- 

r_flash_dil_data_collected.xml

 -->

**ページビューイベント**

`s.trackVars` で別途指定されている場合を除き、[!UICONTROL Flash DIL] は Adobe AppMeasurement から次のデータを収集します。

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**リンクトラッキングイベント**

`s.linkTrackVars` で別途指定されている場合を除き、[!UICONTROL Flash DIL] は Adobe [!UICONTROL AppMeasurement] から次のデータを収集します。

* `pe`（呼び出されたトラックリンクのタイプ）
* `pev1`（リンク URL）
* `pev2`（リンクテキスト）

**メディアトラッキングイベント**

`s.Media.trackVars` で別途指定されている場合を除き、[!UICONTROL Flash DIL] は「ページビューイベント」の節に列挙されているすべてのデータを収集します。

**その他のデータポイント**

デフォルトでは、次のパラメーターからのデータが収集されます。

* `mediaName`（メディア／ビデオ要素名）
* `mediaAdName`（広告名）
* `mediaAdParentName`（広告がネストされているプライマリメディアコンテンツの名前）
* `mediaAdParentPod`（広告が再生されるプライマリコンテンツ内のポッドまたは広告ブレーク）
* `mediaAdParentPodPos`（広告が再生されるポッド内の数値位置。ポッドで複数の広告を再生することもできます）

## Audience Manager の Flash DIL データ {#flash-dil-data}

[!UICONTROL Flash DIL] モジュールは、Adobe AppMeasurement データを Audience Manager の特性および未使用シグナルに変換します。

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props]、[!UICONTROL eVars]、およびイベントは Audience Manager での特性と同様に機能します。特性はキーと値のペアで、セグメントを構築するのに使用されます。例えば、Analytics の `c30=foo` prop は、`c30` がキー（定数）であり、`foo` が値（変数）になります。

**Audience Manager 特性の Analytics 変数とのマッチング**

[!UICONTROL Flash DIL] によって渡された Analytics データを使用するには、キーの値にプレフィックス `c_` が付いた Audience Manager 特性を作成する必要があります。

以下の表に例を示します。

| Analytics データ要素 | Analytics の例 | Audience Manager 特性の場合 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **eVar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**未使用シグナルとしての DIL／Analytics データ**

Audience Manager は、対応する特性がなくても Analytics の [!UICONTROL eVars]、[!UICONTROL Props]、およびイベントを受け入れます。この場合、このデータは、特性の作成には使用できませんが、代わりに[未使用シグナルレポート](../reporting/dynamic-reports/unused-signals.md)に表示されます。この情報を最大限に活用するには、[!UICONTROL Flash DIL] ライブラリによって渡された Analytics データに一致する Audience Manager 特性を作成します。

## Flash DIL ActionScript ライブラリ {#flash-dil-actionscript}

[!DNL Flash] オブジェクトで Analytics データを Audience Manager に送信するためのコード。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* このコードがサポートするパートナーインスタンス（`d.partner`）は、[!DNL Flash] オブジェクトごとに 1 つだけです。
>
>* Adobe [!UICONTROL AppMeasurement] [!DNL AS] ライブラリバージョン 3.5.2 以降が必要です。


```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

>[!MORELIKETHIS]
>
>* [特性](../features/traits/trait-details-page.md)
>* [シグナル、特性、セグメント](../reference/signal-trait-segment.md)
>* [キーと値のペアの解説](../reference/key-value-pairs-explained.md)
>* [キー変数のプレフィックスに関する要件](../features/traits/trait-variable-prefixes.md)

