---
description: 対応可能なログファイルを使用すると、広告サーバーのログファイルからメディア信号を取り込んで、Audience Managerで特徴を作成できます。 ピクセルを追加する必要なく、広告サーバーから特性としてインプレッション、クリックおよびコンバージョンを取得します。
keywords: 実行可能なログ， alf, ALF
seo-description: 対応可能なログファイルを使用すると、広告サーバーのログファイルからメディア信号を取り込んで、Audience Managerで特徴を作成できます。 追加ピクセルを使用する必要なく、広告サーバーから特性としてインプレッション、クリックおよびコンバージョンを取得します。
seo-title: 実用的なログファイル
solution: Audience Manager
title: 実用的なログファイル
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: e324a298bf72b223e4ebf5627f3314e1613d3761

---


# 実用的なログファイル {#actionable-log-files}

[!UICONTROL Actionable Log Files] 広告サーバーのログファイルからメディアデータを取り込み、データを使用してAudience Managerで特徴を作成できます。 Capture impressions, clicks, and conversions from ad servers as traits without having to append [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>テキストスタイル（`monospaced text`、*斜体*、括弧 `[ ]` `( )`、その他）コード要素およびオプションを表します。詳しくは、[コードおよびテキスト要素のスタイル規則](../../reference/code-style-elements.md)を参照してください。

## 目的 {#purpose}

[!UICONTROL Actionable Log Files]により、インプレッション数、クリック数およびコンバージョン数を広告サーバーから効率的に取得できます。[!DNL Audience Manager] にキャンペーン属性を送信するために手動でメディアピクセルを埋め込むことなく、この情報をユーザーのセグメント化に使用できます。

## はじめに {#getting-started}

を開始するには、にロ [!UICONTROL Actionable Log Files]グデータをインポートする必要がありま [!DNL Audience Manager]す。 以下のリンクを参照してください。

* For [!UICONTROL Google DCM] logs, see [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *and* contact your [!DNL Audience Manager] consultant.
* その他の広告サーバーログについては、「データとメタデ [ータファイル」を参照し](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) 、コン *サルタントに問い*[!DNL Audience Manager] 合わせます。

If you are already importing log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you.

>[!IMPORTANT]
>
> 2019年の終わりに、新しい広告 [!UICONTROL Actionable Log Files] サーバーの可用性が向上し始めます。 Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

## 実用的なログファイルの使用 {#working-with-actionable-log-files}

With [!UICONTROL Actionable Log Files], the information from ad server logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager] 広告サーバーのログストレージに接続し、ログからの情報を解析し、ログデータを実行可能なシグナルとしてデータ収集サーバーに [送信します](../../reference/system-components/components-data-collection.md#dcs-pcs)。

実用的なシグナルを取得するためには、ルールベースの特性を設定する必要があります。[Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) または[一括管理ツール](../../reference/bulk-management-tools/bulk-create.md)のいずれかを使用して、ルールベースの特性を設定する方法を参照してください。ルールベースの特性で使用できるすべてのキーのリストを参照するには、[実用的なシグナル](../../integration/media-data-integration/actionable-log-files.md#actionable-signals)の節までスクロールしてください。

>[!IMPORTANT]
>
>[ピクセル呼び出し](../../integration/media-data-integration/impression-data-pixels.md)の&#x200B;*代わりに* [!UICONTROL Actionable Log Files] を実装することを強くお勧めします。両方のオプションを使用することは、特性の頻度が多くカウントされるため推奨されません。

## 実用的なシグナル {#actionable-signals}

シグナルは、[!DNL Audience Manager] の[最小データ単位](../../reference/signal-trait-segment.md)です。[!UICONTROL Actionable Log Files] インプレッションイベント、クリックイベント、コンバージョンイベントの広告主、ビジネスユニット、クリエイティブ、キャンペーンの値を広告サーバーログからのシグナルとして取り込むことができます。

この情報をオーディエンスの作成およびセグメント化に使用する場合、自分でルールベースの特性を設定する必要があることに注意してください。

### Google DCMログからの実行可能なシグナル {#dcm-logs-signals}

この表は、[!DNL DCM] ログファイルから取得される実用的なシグナルの一覧です。

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ログファイルのヘッダー名 </th> 
   <th colname="col2" class="entry"> シグナル </th> 
   <th colname="col3" class="entry"> 説明 </th> 
   <th colname="col4" class="entry"> 例Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>コンバージョンイベントでのみ使用されます。 </p> <p>DCM のコンバージョンアクティビティの数値 ID を表します。このフィールドは、DCM のアクティビティ ID とマッピングされます。 </p> <p> <p>ヒント：DCM の複数または特定のコンバージョンアクティビティを取得できます。Create traits using <code> d_conversion = activity ID</code> for each conversion activity from DCM. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>コンバージョンイベントでのみ使用されます。 </p> <p>このフィールドは、DCM のコンバージョン ID にマッピングされます。DCM のユーザーコンバージョンに先行するアクティビティを示します。 </p> <p>使用できる値は次のとおりです。 </p> <p> 
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
   <td colname="col3">インプレッションイベント、クリックイベント、コンバージョンイベントの日付と時刻（UTC タイムゾーン）。1970-01-01 00:00:00 UTCからのマイクロ秒単位で表されます。</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>広告主のデータソースの統合コード。Audience Manager のデータソースとは関係ありません。</p> <p>このフィールドは、DCM の広告主グループ ID にマッピングされます。 </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>事業部門 ID。このフィールドは、DCM の広告主 ID にマッピングされます。 </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>DCM から提供されたキャンペーン ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>DCM から提供されたクリエイティブ ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 売上金額(USD)。-6の累乗。 1.000.000を掛けると、ドル額として表示されます。</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>イベントタイプを示します。 Audience Managerは、DCMログファイル名からイベントタイプを読み取り、実行可能な信号に変換します。 </p> <p>使用できる値は次のとおりです。 </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> インプレッション数 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> をクリックします。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> を設定します。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>DCM データの取得に使用するデータソースの ID。<a href="../../features/manage-datasources.md#create-data-source">データソースの作成方法</a>を参照してください。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

この表で説明されているシグナルは、[!DNL Audience Manager]`HTTP` において、リアルタイムの 呼び出しと同じように取得されます。次の呼び出しの例には、[!DNL DCM] のコンバージョンイベントについての情報が含まれています。必ずしも呼び出しの例にある&#x200B;*すべての*&#x200B;シグナルを呼び出しに含める必要はありません。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

平均的サイズである 2,000,000 行の [!DNL DCM] ログでは、実用的なシグナルから作成されたすべての特性は、ログの処理後 1 時間以内に適合されます。

>[!NOTE] {importance="high"}
>
>[!DNL DCM] ログによって提供されるイベントタイムスタンプは保持され、[!UICONTROL Data Collection Servers]に渡されます。
>
>* [!DNL DCM] ログファイルのデータ行からタイムスタンプが取得できなかった場合、イベントタイムスタンプとして `HTTP` 呼び出しの時刻を使用します。
>* [!DNL DCM] ログファイルのデータ行のタイムスタンプの形式が正しくない場合、その行全体が無視されます。


 <br>

### 汎用広告サーバーログからの対応可能なシグナル {#generic-logs-signals}

まず、広告サーバーログをAmazon S3バケットにドロップする必要があります。 これを達成するには、「オーディエンス最適化レ [ポートのデータファイル」と「対応可能なログファイル」を読み](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) 、コン *サルタントに*[!DNL Audience Manager] お問い合わせください。 次の表に、汎用ログファイルから実行可能なシグナルを示します。

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ログファイルのヘッダー名 </th> 
   <th colname="col2" class="entry"> シグナル </th> 
   <th colname="col3" class="entry"> 説明 </th> 
   <th colname="col4" class="entry"> 例Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>コンバージョンが対応しているかどうかを示します。オプションは以下のとおりです。 </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> インプレッション </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> クリック </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> 属性なしまたは不明 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> インプレッションイベント、クリックイベント、コンバージョンイベントの日付と時刻（UTC タイムゾーン）。その場合は、<code>yyyy-dd-mm hh:mm:ss format.</code> </p></td> 
   <td colname="col4"> <p> <code>2019-30-08 11:23:00</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>広告主のデータソースの統合コード。Note that this field is not related to <a href="../../features/datasources-list-and-settings.md">Audience Manager data sources.</a></p></td> 
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
   <td colname="col3"> <p>ログファイルのキャンペーンID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>ログファイルから取得したクリエイティブID。 </p> </td> 
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
   <td colname="col3"> <p>イベントタイプを示します。 Audience Managerは、ログファイル名からイベントタイプを読み取り、アクション可能なシグナルに変換します。 ログファイル <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">の命名規則を参照してください</a>。 </p> <p>使用できる値は次のとおりです。 </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> インプレッション数 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> をクリックします。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> を設定します。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>ログデータの取得に使用するデータソースのID。 <a href="../../features/manage-datasources.md#create-data-source">データソースの作成方法</a>を参照してください。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

この表で説明されているシグナルは、[!DNL Audience Manager]`HTTP` において、リアルタイムの 呼び出しと同じように取得されます。必ずしも呼び出しの例にある&#x200B;*すべての*&#x200B;シグナルを呼び出しに含める必要はありません。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## ユースケース {#use-cases}

[!UICONTROL Actionable Log Files]を実装するメリットの 1 つは、実用的なシグナルを含んだあらゆる[ルールベースの特性](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)に[最新性と頻度](../../features/segments/recency-and-frequency.md)の制御を適用できることです。これによって、例えば、メディアキャンペーン内で特定のクリエイティブがあるユーザーに対して表示される回数を制限するフリークエンシーキャップを有効にできます。この方 [法については、「インスタントクロスデバイス抑制](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) 」を参照してください。 他にも以下のようなユースケースがあります。

### ユーザーの再ターゲット化

クリエイティブ 123 が表示されたもののクリックまたはコンバージョンが発生しなかったユーザーを再ターゲットし、クリエイティブ 456 を表示するには、以下の手順に従います。

1. クリエイティブが表示されたユーザーを取得する特性を作成します。例えば、特性の名前を [!DNL Creative Trait 123] としたとします。次の特性ルールを使用します。

   `d_creative == 123 AND d_event == imp`

2. クリックまたはコンバージョンをおこなうユーザーを取得する特性を作成します。例えば、この特性の名前を [!DNL Click and Converter] としたとします。次の特性ルールを使用します。

   `d_event == click OR d_event=conv`

3. クリエイティブ 123 が表示されたものの、クリックまたはコンバージョンが発生しなかったユーザーを割り当てるセグメントを作成します。そのセグメントの名前を [!DNL Retarget Users] とし、次のセグメントルールを使用します。

   `Creative Trait 123 AND NOT Click and Converter`

4. セグメント [!DNL Retarget Users] を宛先にマッピングし、クリエイティブ 456 を使用して宛先のユーザーをターゲット化します。

### Audience Optimization レポートまたは Audience Lab で DCM フラッドライトアクティビティを使用

[Floodlight タグ](https://support.google.com/dcm/partner/answer/4293719?hl=en)を使用することで、広告主はユーザーのコンバージョンを追跡できます。[!UICONTROL Actionable Log Files]を使用することで、[!DNL DCM]Audience Optimization レポート[または](../../reporting/audience-optimization-reports/audience-optimization-reports.md) Audience Lab[ で ](../../features/audience-lab/audience-lab.md) コンバージョンを追跡できます。

1. 特性を作成し、広告サーバーログからコンバージョンを取得する次の特性ルールを使用します。

   `d_event == conv AND d_conversion == 123`

   Audience Manager [!UICONTROL UI]で特性を作成する場合は、[!UICONTROL Event Type]として[!UICONTROL Conversion]を選択します。

2. 特性の作成後、[!UICONTROL Audience Optimization Reports]および[!UICONTROL Audience Lab]でコンバージョンのレポートが開始されます。

>[!MORE_LIKE_THIS]
>
>* [DCM データファイルを Audience Manager にインポート](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Audience Optimization レポート](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

