---
description: アクションにつながるログファイルを使用すると、広告サーバーログファイルからメディアシグナルをキャプチャし、Audience Manager で特性を作成することができます。ピクセルを追加することなく、インプレッション、クリック数およびコンバージョンを特性として広告サーバーから取得できるようになります。
keywords: 実用的なログ、alf、ALF
seo-description: アクションにつながるログファイルを使用すると、広告サーバーログファイルからメディアシグナルをキャプチャし、Audience Manager で特性を作成することができます。ピクセルを追加することなく、インプレッション、クリック数およびコンバージョンを特性として広告サーバーから取得できるようになります。
seo-title: アクションにつながるログファイル
solution: Audience Manager
title: アクションにつながるログファイル
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: ログファイル
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: 7c46a246233c3519049197bac824f0ee0db29754
workflow-type: ht
source-wordcount: '1611'
ht-degree: 100%

---

# アクションにつながるログファイル {#actionable-log-files}

[!UICONTROL Actionable Log Files] を使用すれば、広告サーバーログファイルからメディアデータをキャプチャし、Audience Manager でそのデータを使用して特性を作成することができます。[ピクセル](../../integration/media-data-integration/impression-data-pixels.md)を追加することなく、インプレッション、クリック数およびコンバージョンを特性として広告サーバーから取得できるようになります。

>[!NOTE]
>
>テキストスタイル（`monospaced text`、*斜体*、括弧 `[ ]` `( )`、その他）コード要素およびオプションを表します。詳しくは、[コードおよびテキスト要素のスタイル規則](../../reference/code-style-elements.md)を参照してください。

## 目的 {#purpose}

[!UICONTROL Actionable Log Files]により、インプレッション数、クリック数およびコンバージョン数を広告サーバーから効率的に取得できます。[!DNL Audience Manager] にキャンペーン属性を送信するために手動でメディアピクセルを埋め込むことなく、この情報をユーザーのセグメント化に使用できます。

## はじめに {#getting-started}

[!UICONTROL Actionable Log Files] を開始するには、[!DNL Audience Manager] にログデータを読み込む必要があります。以下のリンクは、使用を開始するのに役立ちます。

* [!UICONTROL Google Campaign Manager] ログについては、[Google キャンペーンマネージャーデータファイルを Audience Manager に読み込む](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)を参照した&#x200B;*うえで*、担当の [!DNL Audience Manager] コンサルタントにお問い合わせください。
* [!UICONTROL Google Ad Manager]（旧称 Google DFP）ログについては、[Google Ad Manager データファイルを Audience Manager に読み込む](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md)を参照した&#x200B;*うえで*、担当の [!DNL Audience Manager] コンサルタントにお問い合わせください。
* その他の広告サーバーログについては、[データとメタデータファイル](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)を参照した&#x200B;*うえで*、担当の [!DNL Audience Manager] コンサルタントにお問合せください。

既にログデータを [!DNL Audience Manager] に読み込んでいる場合は、担当の [!DNL Audience Manager] コンサルタントまたは[カスタマーサポート](https://helpx.adobe.com/jp/contact/enterprise-support.ec.html)にお問合せいただき、[!UICONTROL Actionable Log Files] を有効化してもらってください。

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## アクションにつながるログファイルの使用 {#working-with-actionable-log-files}

[!UICONTROL Actionable Log Files]を使用すると、Web サイトでのリアルタイムなインタラクションの場合と同じ方法でコウコクサーバーログの情報を [!DNL Audience Manager] に取り込むことができます。[!DNL Audience Manager] と広告サーバーログストレージを接続してログの情報を解析し、ログデータをアクションにつながるシグナルとしてアドビの[データ収集サーバー](../../reference/system-components/components-data-collection.md#dcs-pcs)に送信します。

アクションにつながるシグナルを取得するためには、ルールベースの特性を設定する必要があります。ルールベースの特性の設定方法については、[Audience Manager ユーザーインターフェイス](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)、または[一括管理ツール](../../reference/bulk-management-tools/bulk-create.md)を参照してください。ルールベースの特性で使用できるすべてのキーのリストを参照するには、[アクションにつながるシグナル](../../integration/media-data-integration/actionable-log-files.md#actionable-signals)の節までスクロールしてください。

>[!IMPORTANT]
>
>[ピクセル呼び出し](../../integration/media-data-integration/impression-data-pixels.md)の&#x200B;*代わりに* [!UICONTROL Actionable Log Files] を実装することを強くお勧めします。両方のオプションを使用することは、特性の頻度が多くカウントされるため推奨されません。

## アクションにつながるシグナル {#actionable-signals}

シグナルは、[!DNL Audience Manager] の[最小データ単位](../../reference/signal-trait-segment.md)です。[!UICONTROL Actionable Log Files]を使用することで、広告サーバーログのシグナルとして、インプレッションイベント、クリックイベント、およびコンバージョンイベントにおける広告主、ビジネスユニット、クリエイティブ、およびキャンペーン値を取得できます。

この情報をオーディエンスの作成およびセグメント化に使用する場合、自分でルールベースの特性を設定する必要があることに注意してください。

### Google Campaign Manager のログのアクションにつながるシグナル {#dcm-logs-signals}

この表は、[!DNL Google Campaign Manager] ログファイルから取得されるアクションにつながるシグナルの一覧です。

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ログファイルのヘッダー名 </th> 
   <th colname="col2" class="entry"> シグナル </th> 
   <th colname="col3" class="entry"> 説明 </th> 
   <th colname="col4" class="entry"> 値の例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>コンバージョンイベントでのみ使用されます。 </p> <p>Google Campaign Manager のコンバージョンアクティビティの数値 ID を表します。このフィールドは、Google Campaign Manager のアクティビティ ID にマッピングされます。 </p> <p> <p>ヒント：Google Campaign Manager の複数または特定のコンバージョンアクティビティを取得できます。Google Campaign Manager の各コンバージョンアクティビティに <code> d_conversion = activity ID</code> を使用して特性を作成します。 </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>コンバージョンイベントでのみ使用されます。 </p> <p>このフィールドは、Google Campaign Manager のコンバージョン ID にマッピングされます。Google Campaign Manager からのユーザーコンバージョンの前のアクティビティを示します。 </p> <p>使用できる値は次のとおりです。 </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code>。クリック後のコンバージョンを示します。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code>。インプレッション後のコンバージョンを示します。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code>。対応なし。先行するアクティビティと対応させることができないコンバージョン。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">インプレッションイベント、クリックイベント、コンバージョンイベントの日付と時刻（UTC タイムゾーン）。1970-01-01 00:00:00 UTC からマイクロ秒単位で表示されます。</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>広告主のデータソースの統合コード。Audience Manager のデータソースとは関係ありません。</p> <p>このフィールドは、Google Campaign Manager の広告主グループ ID にマッピングされます。 </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>事業部門 ID。このフィールドは、Google Campaign Manager の広告主 ID にマッピングされます。 </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Google Campaign Manager から提供されるキャンペーン ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Google Campaign Manager が提供するクリエイティブ ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 売上金額（USD）を -6 の累乗で表します。1.000.000 を乗算すると、ドルの金額として表示されます。</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>イベントタイプを示します。Audience Manager は、Google Campaign Manager ログファイル名からイベントタイプを読み取り、アクションにつながるシグナルに変換します。 </p> <p>使用できる値は次のとおりです。 </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> インプレッション数：<code> d_event = imp</code>。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> クリック数：<code> d_event = click</code>。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> コンバージョン：<code> d_event = conv</code>。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>Google Campaign Manager データの取得に使用するデータソースの ID。<a href="../../features/manage-datasources.md#create-data-source">データソースの作成方法</a>を参照してください。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

この表で説明されているシグナルは、[!DNL Audience Manager] において、リアルタイムの `HTTP` 呼び出しと同じように取得されます。次の呼び出しの例には、[!DNL Google Campaign Manager] のコンバージョンイベントについての情報が含まれています。必ずしも呼び出しの例にある&#x200B;*すべての*&#x200B;シグナルを呼び出しに含める必要はありません。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

平均的サイズである 2,000,000 行の [!DNL Google Campaign Manager] ログでは、アクションにつながるシグナルから作成されたすべての特性は、ログの処理後 1 時間以内に認識されます。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Google Campaign Manager] ログによって提供されるイベントタイムスタンプは保持され、[!UICONTROL Data Collection Servers]に渡されます。
>
>* [!DNL Google Campaign Manager] ログファイルのデータ行からタイムスタンプが取得できなかった場合、イベントタイムスタンプとして `HTTP` 呼び出しの時刻を使用します。
>* [!DNL Google Campaign Manager] ログファイルのデータ行のタイムスタンプの形式が正しくない場合、その行全体が無視されます。


 <br>

### [!DNL Google Ad Manager] ログのアクションにつながるシグナル  {#ad-manager-logs-signals}

この表は、[!DNL Google Ad Manager] ログファイルから取得されるアクションにつながるシグナルの一覧です。


| ログファイルのヘッダー名 | シグナル | 説明 |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | 配信された Ad Manager 行項目の数値 ID。 |
| `OrderId` | `d_orderid` | 配信された行項目とクリエイティブを含む、Ad Manager の注文の数値 ID。 |
| `CreativeId` | `d_creative` | 配信された Ad Manager クリエイティブの数値 ID。 |
| `-` | `d_event` | イベントタイプを示します。Audience Manager は、Ad Manager ログファイル名からイベントタイプを読み取り、アクションにつながるシグナルに変換します。使用できる値は次のとおりです。<br> <ul><li>d_event = imp：インプレッションを示します。</li><li>d_event = click：クリックを示します。</li><li>d_event = conv：コンバージョンとアクティビティを示します。</li></ul> |
| `-` | `d_src` | Ad Manager データの取得に使用するデータソースの ID。[データソースの作成方法](/help/using/features/manage-datasources.md)を参照してください。 |

この表で説明されているシグナルは、Audience Manager において、リアルタイムの HTTP 呼び出しと同じように取得されます。次の呼び出しの例には、Google Ad Manager のコンバージョンイベントに関する情報が含まれています。必ずしも呼び出しの例にあるすべてのシグナルを呼び出しに含める必要はありません。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>[!DNL Google Ad Manager] ログによって提供されるイベントタイムスタンプは保持され、[!UICONTROL Data Collection Servers]に渡されます。
>
>* [!DNL Google Ad Manager] ログファイルのデータ行からタイムスタンプが取得できなかった場合、イベントタイムスタンプとして `HTTP` 呼び出しの時刻を使用します。
>* [!DNL Google Ad Manager] ログファイルのデータ行のタイムスタンプの形式が正しくない場合、その行全体が無視されます。


 <br>

### 汎用広告サーバーログのアクションにつながるシグナル {#generic-logs-signals}

まず、広告サーバーログを Amazon S3 バケットに配置する必要があります。これを達成するには、[Audience Optimization レポートおよびアクションにつながるログファイル用のデータファイル](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)を読んだ&#x200B;*うえで*、[!DNL Audience Manager] コンサルタントにお問い合わせください。この表は、汎用ログファイルから取得されるアクションにつながるシグナルの一覧です。

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ログファイルのヘッダー名 </th> 
   <th colname="col2" class="entry"> シグナル </th> 
   <th colname="col3" class="entry"> 説明 </th> 
   <th colname="col4" class="entry"> 値の例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>コンバージョンが対応しているかどうかを示します。オプションは次のとおりです。 </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> インプレッション </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> クリック </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> 原因不明 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> インプレッションイベント、クリックイベント、コンバージョンイベントの日付と時刻（UTC タイムゾーン）。<code>yyyy-MM-dd HH:mm:ss</code>形式を使用します。 </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>広告主のデータソースの統合コード。このフィールドは、<a href="../../features/datasources-list-and-settings.md">Audience Manager のデータソース</a>とは関係ありません。</p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>事業部門 ID。  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>ログファイルのキャンペーン ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>ログファイルのクリエイティブ ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 獲得やその他のコンバージョン量。データタイプは浮動小数。 </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>イベントタイプを示します。Audience Manager は、ログファイル名からイベントタイプを読み取り、アクションにつながるシグナルに変換します。<a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">ログファイルの命名規則</a>を参照してください。 </p> <p>使用できる値は次のとおりです。 </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> インプレッション数：<code> d_event = imp</code>。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> クリック数：<code> d_event = click</code>。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> コンバージョン：<code> d_event = conv</code>。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>ログデータの取得に使用するデータソースの ID。<a href="../../features/manage-datasources.md#create-data-source">データソースの作成方法</a>を参照してください。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

この表で説明されているシグナルは、[!DNL Audience Manager] において、リアルタイムの `HTTP` 呼び出しと同じように取得されます。必ずしも呼び出しの例にある&#x200B;*すべての*&#x200B;シグナルを呼び出しに含める必要はありません。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Audience Manager ユーザーインターフェイスでのアクションにつながるシグナルの操作 {#actionable-signals-in-ui}

アクションにつながる着信シグナルは、[シグナル検索](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md)インターフェイスで確認できます。

**オーディエンスデータ**（1）／**シグナル**（2）／**検索**（3）に移動し、**アクションにつながるログファイル**（4）フィルターを選択します。

![UI のアクションにつながるシグナル](/help/using/integration/assets/alf-in-signals.png)

アクションにつながるシグナルを使用してルールベースの特性を作成するには、「**アクションにつながるログファイル**」（1）を選択し、特性ルールとして使用するアクションにつながるシグナル（2）を選択して、「**シグナルからの特性の作成**」（3）を押します。

![シグナルからの特性の作成](/help/using/integration/assets/alf-create-trait.png)


## ユースケース {#use-cases}

[!UICONTROL Actionable Log Files]を実装するメリットの 1 つは、アクションにつながるシグナルを含んだあらゆる[ルールベースの特性](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)に[最新性と頻度](../../features/segments/recency-and-frequency.md)の制御を適用できることです。これによって、例えば、メディアキャンペーン内で特定のクリエイティブがあるユーザーに対して表示される回数を制限するフリークエンシーキャップを有効にできます。この方法については、[Instant Cross-Device Suppression](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) を参照してください。他にも以下のようなユースケースがあります。

### ユーザーの再ターゲット化

クリエイティブ 123 が表示されたもののクリックまたはコンバージョンが発生しなかったユーザーを再ターゲットし、クリエイティブ 456 を表示するには、以下の手順に従います。

1. クリエイティブが表示されたユーザーを取得する特性を作成します。例えば、特性の名前を [!DNL Creative Trait 123] としたとします。次の特性ルールを使用します。

   `d_creative == 123 AND d_event == imp`

2. クリックまたはコンバージョンをおこなうユーザーを取得する特性を作成します。例えば、この特性の名前を [!DNL Click and Converter] としたとします。次の特性ルールを使用します。

   `d_event == click OR d_event=conv`

3. クリエイティブ 123 が表示されたものの、クリックまたはコンバージョンが発生しなかったユーザーを割り当てるセグメントを作成します。そのセグメントの名前を [!DNL Retarget Users] とし、次のセグメントルールを使用します。

   `Creative Trait 123 AND NOT Click and Converter`

4. セグメント [!DNL Retarget Users] を宛先にマッピングし、クリエイティブ 456 を使用して宛先のユーザーをターゲット化します。

### Audience Optimization レポートまたは Audience Lab で Google Campaign Manager フラッドライトアクティビティを使用

[Floodlight タグ](https://support.google.com/dcm/partner/answer/4293719?hl=ja)を使用することで、広告主はユーザーのコンバージョンを追跡できます。[!UICONTROL Actionable Log Files]を使用することで、[Audience Optimization レポート](../../reporting/audience-optimization-reports/audience-optimization-reports.md)または [Audience Lab](../../features/audience-lab/audience-lab.md) で [!DNL Google Campaign Manager] コンバージョンを追跡できます。

1. 特性を作成し、広告サーバーログからコンバージョンを取得する次の特性ルールを使用します。

   `d_event == conv AND d_conversion == 123`

   Audience Manager [!UICONTROL UI]で特性を作成する場合は、[!UICONTROL Event Type]として[!UICONTROL Conversion]を選択します。

2. 特性の作成後、[!UICONTROL Audience Optimization Reports]および[!UICONTROL Audience Lab]でコンバージョンのレポートが開始されます。

>[!MORELIKETHIS]
>
>* [Google キャンペーンマネージャーデータファイルを Audience Manager に読み込む](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
* [Audience Optimization レポート](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

