---
description: 実用的なログファイルを使用すると、Google DCM ログファイルからメディアデータをキャプチャし、Audience Manager でそのデータを使用して特性を作成することができます。ピクセル呼び出しを使用することなく、インプレッション、クリック数およびコンバージョンを特徴として広告サーバーから取得できるようになります。
keywords: 実用的なログ
seo-description: 実用的なログファイルを使用すると、Google DCM ログファイルからメディアデータをキャプチャし、Audience Manager でそのデータを使用して特性を作成することができます。ピクセル呼び出しを使用することなく、インプレッション、クリック数およびコンバージョンを特徴として広告サーバーから取得できるようになります。
seo-title: 実用的なログファイル
solution: Audience Manager
title: 実用的なログファイル
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# 実用的なログファイル {#actionable-log-files}

[!UICONTROL Actionable Log Files]を使用すると、[!DNL Google DCM] ログファイルからメディアデータをキャプチャし、Audience Manager でそのデータを使用して特性を作成することができます。ピクセル呼び出しを使用することなく、インプレッション、クリック数およびコンバージョンを特徴として広告サーバーから取得できるようになります。

>[!NOTE]
>
>テキストスタイル（`monospaced text`、*斜体*、括弧 `[ ]` `( )`、その他）コード要素およびオプションを表します。詳しくは、[コードおよびテキスト要素のスタイル規則](../../reference/code-style-elements.md)を参照してください。

## 目的 {#purpose}

[!UICONTROL Actionable Log Files]により、インプレッション数、クリック数およびコンバージョン数を広告サーバーから効率的に取得できます。[!DNL Audience Manager] にキャンペーン属性を送信するために手動でメディアピクセルを埋め込むことなく、この情報をユーザーのセグメント化に使用できます。

## はじめに {#getting-started}

[!UICONTROL Actionable Log Files]および [Audience Optimization レポート](../../reporting/audience-optimization-reports/audience-optimization-reports.md)の使用を開始するには、DCM ログデータを [!DNL Audience Manager] に読み込む必要があります。[DCM データファイルを Audience Manager にインポート](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)を参照した&#x200B;*うえで*、担当の [!DNL Audience Manager] コンサルタントにお問い合わせください。

If you are already importing [!UICONTROL DCM] log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you.

>[!NOTE] {importance="high"}
>
>[!UICONTROL Actionable Log Files] は、[!DNL Google DCM] ログファイルでのみ使用できます。

## 実用的なログファイルの使用 {#working-with-actionable-log-files}

[!UICONTROL Actionable Log Files]を使用すると、Web サイトでのリアルタイムなインタラクションの場合と同じ方法で [!DNL DCM] ログの情報を [!DNL Audience Manager] に取り込むことができます。[!DNL Audience Manager]は、[!DNL Google Cloud] ストレージと接続し、[!DNL DCM] ログの情報を解析し、ログデータを実用的なシグナルとしてアドビの[データ収集サーバー](../../reference/system-components/components-data-collection.md#dcs-pcs)に送信します。

実用的なシグナルを取得するためには、ルールベースの特性を設定する必要があります。[Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) または[一括管理ツール](../../reference/bulk-management-tools/bulk-create.md)のいずれかを使用して、ルールベースの特性を設定する方法を参照してください。ルールベースの特性で使用できるすべてのキーのリストを参照するには、[実用的なシグナル](../../integration/media-data-integration/actionable-log-files.md#actionable-signals)の節までスクロールしてください。

平均的サイズである 2,000,000 行の [!DNL DCM] ログでは、実用的なシグナルから作成されたすべての特性は、ログの処理後 1 時間以内に適合されます。

>[!IMPORTANT] {importance="high"}
>
>[ピクセル呼び出し](../../integration/media-data-integration/impression-data-pixels.md)の&#x200B;*代わりに* [!UICONTROL Actionable Log Files] を実装することを強くお勧めします。両方のオプションを使用することは、特性の頻度が多くカウントされるため推奨されません。

## 実用的なシグナル {#actionable-signals}

シグナルは、[!DNL Audience Manager] の[最小データ単位](../../reference/signal-trait-segment.md)です。[!UICONTROL Actionable Log Files]を使用することで、[!DNL DCM] ログのシグナルとして、インプレッションイベント、クリックイベント、およびコンバージョンイベントにおける広告主、ビジネスユニット、クリエイティブ、およびキャンペーン値を取得できます。

この情報をオーディエンスの作成およびセグメント化に使用する場合、自分でルールベースの特性を設定する必要があることに注意してください。この表は、[!DNL DCM] ログファイルから取得される実用的なシグナルの一覧です。

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> シグナル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> 例 Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_event</code> </p> </td> 
   <td colname="col2"> <p>DCM のイベントのタイプを示します。 </p> <p>使用できる値は次のとおりです。 </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code>d_event = imp</code>。インプレッションを示します。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code>d_event = click</code>。クリックを示します。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code>d_event = conv</code>。コンバージョンを示します。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp、click、conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col2"> <p>コンバージョンイベントでのみ使用されます。 </p> <p>DCM のコンバージョンアクティビティの数値 ID を表します。このフィールドは、DCM のアクティビティ ID とマッピングされます。 </p> <p> <p>ヒント：DCM の複数または特定のコンバージョンアクティビティを取得できます。DCM の各コンバージョンアクティビティに対して、<code>d_conversion = activity ID</code> を使用して特性を作成します。 </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversionType</code> </p> </td> 
   <td colname="col2"> <p>コンバージョンイベントでのみ使用されます。 </p> <p>このフィールドは、DCM のコンバージョン ID にマッピングされます。DCM のユーザーコンバージョンに先行するアクティビティを示します。 </p> <p>使用できる値は次のとおりです。 </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code>1</code>。クリック後のコンバージョンを示します。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code>2</code>。インプレッション後のコンバージョンを示します。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code>0</code>。対応なし。先行するアクティビティと対応させることができないコンバージョン。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0、1、2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col2"> <p>広告主 ID。</p> <p>広告主のデータソースの統合コード。これはAudience Managerデータソースとは関係ありません。</p> <p>このフィールドは、DCM の広告主グループ ID にマッピングされます。 </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col2"> <p>事業部門 ID。このフィールドは、DCM の広告主 ID にマッピングされます。 </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col2"> <p>DCM から提供されたキャンペーン ID。 </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col2"> <p>DCM から提供されたクリエイティブ ID。 </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col2"> <p>DCM データの取得に使用するデータソースの ID。<a href="../../features/manage-datasources.md#create-data-source">データソースの作成方法</a>を参照してください。 </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

この表で説明されているシグナルは、[!DNL Audience Manager]`HTTP` において、リアルタイムの 呼び出しと同じように取得されます。次の呼び出しの例には、[!DNL DCM] のコンバージョンイベントについての情報が含まれています。必ずしも呼び出しの例にある&#x200B;*すべての*&#x200B;シグナルを呼び出しに含める必要はありません。

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance="high"}
>
>[!DNL DCM] ログによって提供されるイベントタイムスタンプは保持され、[!UICONTROL Data Collection Servers]に渡されます。
>
>* [!DNL DCM] ログファイルのデータ行からタイムスタンプが取得できなかった場合、イベントタイムスタンプとして `HTTP` 呼び出しの時刻を使用します。
>* [!DNL DCM] ログファイルのデータ行のタイムスタンプの形式が正しくない場合、その行全体が無視されます。


## ユースケース {#use-cases}

[!UICONTROL Actionable Log Files]を実装するメリットの 1 つは、実用的なシグナルを含んだあらゆる[ルールベースの特性](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)に[最新性と頻度](../../features/segments/recency-and-frequency.md)の制御を適用できることです。これによって、例えば、メディアキャンペーン内で特定のクリエイティブがあるユーザーに対して表示される回数を制限するフリークエンシーキャップを有効にできます。他にも以下のようなユースケースがあります。

### ユーザーの再ターゲット化

クリエイティブ 123 が表示されたもののクリックまたはコンバージョンが発生しなかったユーザーを再ターゲットし、クリエイティブ 456 を表示するには、以下の手順に従います。

1. クリエイティブが表示されたユーザーを取得する特性を作成します。例えば、特性の名前を [!DNL Creative Trait 123] としたとします。次の特性ルールを使用します。

   `d_creative == 123 AND d_event == imp`

1. クリックまたはコンバージョンをおこなうユーザーを取得する特性を作成します。例えば、この特性の名前を [!DNL Click and Converter] としたとします。次の特性ルールを使用します。

   `d_event == click OR d_event=conv`

1. クリエイティブ 123 が表示されたものの、クリックまたはコンバージョンが発生しなかったユーザーを割り当てるセグメントを作成します。そのセグメントの名前を [!DNL Retarget Users] とし、次のセグメントルールを使用します。

   `Creative Trait 123 AND NOT Click and Converter`

1. セグメント [!DNL Retarget Users] を宛先にマッピングし、クリエイティブ 456 を使用して宛先のユーザーをターゲット化します。

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

