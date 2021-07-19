---
description: メディアデータを Audience Manager に送信する方法の 1 つとして、広告サーバーのマクロを使用してキャンペーン属性を Audience Manager に送信できます。
seo-description: メディアデータを Audience Manager に送信する方法の 1 つとして、広告サーバーのマクロを使用してキャンペーン属性を Audience Manager に送信できます。
seo-title: ピクセル呼び出しを使用したキャンペーンのインプレッションデータのキャプチャ
solution: Audience Manager
title: ピクセル呼び出しを使用したキャンペーンのインプレッションデータのキャプチャ
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign との統合
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 100%

---

# ピクセル呼び出しを使用したキャンペーンのインプレッションデータのキャプチャ{#capturing-campaign-impression-data-via-pixel-calls}

メディアデータを Audience Manager に送信する方法の 1 つとして、広告サーバーのマクロを使用してキャンペーン属性を Audience Manager に送信できます。

この方法は「クリエイティブのピクセリング」とも呼ばれています。これらのデータポイントは、サードパーティの広告サーバーマクロにより動的に [!DNL Audience Manager] ピクセルコードに挿入されます。これらのマクロは、キャンペーンの主要なレポート属性に基づいてすべてのインプレッションとクリックのマッピングとレポートに使用されます。データの集計により、キャンペーンのパフォーマンスを一元的に把握し、カスタムコンバージョンパスを特定することができます。また、顧客はコンバージョンにつながる広告サーバーイベントの順序を改善することができます。

## イベント呼び出しの構文

>[!NOTE]
>
>テキストスタイル（`monospaced text`、*斜体*、括弧 `[ ]` `( )`、その他）コード要素とオプションを示します。詳しくは、[コードおよびテキスト要素のスタイル規則](../../reference/code-style-elements.md)を参照してください。

イベント呼び出しはインプレッションデータとコンバージョンデータを収集し、[!DNL Audience Manager] [データ収集サーバー](/help/using/reference/system-components/components-data-collection.md)（[!DNL DCS]）に送信します。この処理では、呼び出しをクリエイティブに配置するサードパーティの広告サーバーを使用して、コードに挿入される内容が制御されます。このサードパーティの広告サーバー（[!DNL DFA] など）は、このコードを各広告インプレッション内に配置できます。さらに、広告呼び出しでは、広告タブの外部にある公開者データへのアクセスに、[!DNL JavaScript] やフレームバスティング技法は使用していません。

イベント呼び出しは、次の構文を使用するキーと値のペアで構成されています。

```
http://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

このキーと値のペアでは、値変数は広告サーバーにより挿入された ID またはマクロです。広告タグが読み込まれると、`%macro%` は対応する必須の値に置き換えられます。この呼び出しでは、応答は返されません。

## サポートされているキーと値のペア {#supported-key-value-pairs}

インプレッションイベント呼び出しでは、キーと値のペアとして構成されているデータを受け付けます。次の表は、これらの変数を格納するキーの一覧と説明です。これらのうち多くは、[Audience Optimization レポート](../../reporting/audience-optimization-reports/audience-optimization-reports.md)でデータのキャプチャと分析をおこなう場合に必要になります。

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> キー </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>広告サーバーから割り当てられた広告グループ ID（数値）。 </p> <p>オプションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>広告主のデータソース ID または統合コード。 </p> <p><span class="wintitle">Audience Optimization</span> レポートの場合は必須。 </p> <p>オプションです。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>ビジネスユニットのデータソース ID または統合コード。 </p> <p><span class="wintitle">Audience Optimization</span> レポートの場合は必須。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>キャッシュバスティング値。<span class="keyword">Audience Manager</span> は、大部分のブラウザーとプロキシで受け入れられるキャッシュ制御ヘッダーを自動的に送信します。キャッシュバスティングを追加で実行する場合は、このパラメーターをイベント呼び出しに入れ、その後にランダムな文字列を追加します。 </p> <p> オプションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>広告サーバーから割り当てられたキャンペーン ID（数値）。 </p> <p><span class="wintitle">Audience Optimization</span> レポートの場合は必須。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>このコンテキストでは、<code> d_cid </code> は、キーと値のペアをインスタンス化し、モバイルデバイスタイプを個人ユーザー ID に関連付けられるようにします。固定 ID により、モバイルデバイスタイプが決定されます。値（ユーザー ID）は変わることがあります。キーと値のペアを <code> %01 </code>（非表示の制御文字）で区切ります。このパラメーターでは、次のキーを指定できます。 </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: Android（GAID）デバイスを表します。例えば、<code> d_cid = 20914 %01 1234 </code> は、ユーザー 1234 が Android デバイスに関連付けられていることを表します。 </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: iOS（IDFA）デバイスを表します。例えば、<code> d_cid = 20915 %01 5678 </code> は、ユーザー 5678 が iOS デバイスに関連付けられていることを表します。 </li> 
    </ul> <p>オプションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>広告サーバーから割り当てられたクリエイティブ ID（数値）。 </p> <p><span class="wintitle">Audience Optimization</span> レポートの場合は必須。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>イベント呼び出しをインプレッションイベントとして識別します。 </p> <p>必須。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>広告サーバーから割り当てられたプレースメント ID（数値）。 </p> <p> オプションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>広告サーバーから割り当てられたサイト ID（数値）。 </p> <p><span class="wintitle">Audience Optimization</span> レポートの場合は必須。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>メタデータの提供元となるプラットフォームのデータソース ID または統合コード（DFA、Atlas、GBM、Media Math など）。 </p> <p><span class="wintitle">Audience Optimization</span> レポートの場合は必須。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF 用の Audience Manager プラグイン</a>に関連しています。</p> <p><code>gdpr</code>  には、0（GDPR 適用対象外）または 1（GDPR 適用対象）を使用できます。</p> <p>デフォルト値は 0 です。</p><p>オプションです。</p><p><code>gdpr=1</code> の場合、データを正常に処理するには、<code>gdpr_consent</code> パラメーターに IAB TC 同意パラメーターを含める必要があります。そうしないと、すべてのデータが削除されます。</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF 用の Audience Manager プラグイン</a>に関連しています。</p><p> <code>gdpr=1</code> の場合、<code>${gdpr_consent_XXXX}</code> は <code>gdpr_consent</code> 文字列とベンダー ID に置き換えられます（<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external">IAB 仕様</a>を参照）。</p> <p>デフォルト値は 0 です。</p><p>オプションです。</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>クライアントドメイン専用の正確な URL については、Adobe Audience Manager コンサルタントまたはアカウントリードにお問い合わせください。

## 追加機能 - [!DNL Audience Optimization Reports] {#additional-functionality-aor}

ピクセル呼び出しを使用して、[Audience Optimization](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md) レポートを強化できます。ピクセルを使用してレポートに出力する場合は、[メタデータファイルの概要とマッピング](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)を参照してください。

>[!MORELIKETHIS]
>
>* [Audience Optimization レポートのデータおよびメタデータファイル](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

