---
description: 実用的なログファイルを使用すると、Google DCM ログファイルからメディアデータをキャプチャし、Audience Manager でそのデータを使用して特性を作成することができます。ピクセル呼び出しを使用することなく、インプレッション、クリック数およびコンバージョンを特徴として広告サーバーから取得できるようになります。
keywords: 実用的なログ
seo-description: 実用的なログファイルを使用すると、Google DCM ログファイルからメディアデータをキャプチャし、Audience Manager でそのデータを使用して特性を作成することができます。ピクセル呼び出しを使用することなく、インプレッション、クリック数およびコンバージョンを特徴として広告サーバーから取得できるようになります。
seo-title: 実用的なログファイル
solution: Audience Manager
title: 実用的なログファイル
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 実用的なログファイル {#actionable-log-files}

[!UICONTROL Actionable Log Files] では、ログファイルから [!DNL Google DCM] メディアデータをキャプチャし、データを使用してAudience Managerで特性を作成できます。ピクセル呼び出しを使用することなく、インプレッション、クリック数およびコンバージョンを特徴として広告サーバーから取得できるようになります。

>[!NOTE]
>
>テキストスタイル（`monospaced text`斜体 * *、括弧 `[ ]` `( )`、その他）コード要素およびオプションを表します。詳しくは、[コードおよびテキスト要素のスタイル規則](../../reference/code-style-elements.md)を参照してください。

## 目的 {#purpose}

[!UICONTROL Actionable Log Files] 広告サーバーからのインプレッション、クリック、コンバージョンのキャプチャを合理化できます。[!DNL Audience Manager] にキャンペーン属性を送信するために手動でメディアピクセルを埋め込むことなく、この情報をユーザーのセグメント化に使用できます。

## はじめに {#getting-started}

[!UICONTROL Actionable Log Files][オーディエンスの最適化レポート](../../reporting/audience-optimization-reports/audience-optimization-reports.md)を使用するには、DCMログデータをインポートする必要 [!DNL Audience Manager]があります。[DCM データファイルを Audience Manager にインポート](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)を参照した*うえで*、担当の[!DNL Audience Manager] コンサルタントにお問い合わせください。

If you are already importing [!UICONTROL DCM] log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you.

>[!NOTE] {importance=&quot;high&quot;}
>
>[!UICONTROL Actionable Log Files] はログファイルで [!DNL Google DCM] のみ使用できます。

## 実用的なログファイルの使用 {#working-with-actionable-log-files}

With [!UICONTROL Actionable Log Files], the information from [!DNL DCM] logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager][!DNL Google Cloud][!DNL DCM] と ストレージを接続して ログの情報を解析し、ログデータを実用的なシグナルとしてアドビの[データ収集サーバー](../../reference/system-components/components-data-collection.md#dcs-pcs)に送信します。

実用的なシグナルを取得するためには、ルールベースの特性を設定する必要があります。[Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) または[一括管理ツール](../../reference/bulk-management-tools/bulk-create.md)のいずれかを使用して、ルールベースの特性を設定する方法を参照してください。ルールベースの特性で使用できるすべてのキーのリストを参照するには、[実用的なシグナル](../../integration/media-data-integration/actionable-log-files.md#actionable-signals)の節までスクロールしてください。

平均的サイズである 2,000,000 行の [!DNL DCM] ログでは、実用的なシグナルから作成されたすべての特性は、ログの処理後 1 時間以内に適合されます。

>[!IMPORTANT] {importance=&quot;high&quot;}
>
>We recommend implementing [!UICONTROL Actionable Log Files] *instead of*  [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). 両方のオプションを使用することは、特性の頻度が多くカウントされるため推奨されません。

## 実用的なシグナル {#actionable-signals}

シグナルは、[!DNL Audience Manager] の[最小データ単位](../../reference/signal-trait-segment.md)です。[!UICONTROL Actionable Log Files] インプレッションイベント、クリックイベント、インプレッションイベントの広告主、ビジネスユニット、クリエイティブおよびキャンペーンの各値を、ログから [!DNL DCM] のシグナルとして取り込むことができます。

この情報をオーディエンスの作成およびセグメント化に使用する場合、自分でルールベースの特性を設定する必要があることに注意してください。この表は、[!DNL DCM] ログファイルから取得される実用的なシグナルの一覧です。

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> シグナル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> 値の例 </th> 
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
   <td colname="col2"> <p>広告主 ID。このフィールドは、DCM の広告主グループ ID にマッピングされます。 </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col2"> <p>ビジネスユニット ID。このフィールドは、DCM の広告主 ID にマッピングされます。 </p> </td> 
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

この表で説明されているシグナルは、[!DNL Audience Manager]`HTTP` において、リアルタイムの 呼び出しと同じように取得されます。次の呼び出しの例には、[!DNL DCM] のコンバージョンイベントについての情報が含まれています。必ずしも呼び出しの例にある*すべての*シグナルを呼び出しに含める必要はありません。

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance=&quot;high&quot;}
>
>[!DNL DCM] ログに指定されているイベントタイムスタンプが使用され [!UICONTROL Data Collection Servers]、渡されます。
>
>* If a timestamp isn&#39;t available for a data row in the [!DNL DCM] log file, we use the time of the `HTTP` call as the event timestamp.
>* [!DNL DCM] ログファイルのデータ行のタイムスタンプの形式が正しくない場合、その行全体が無視されます。


## ユースケース {#use-cases}

One benefit of implementing [!UICONTROL Actionable Log Files] is the option to apply [recency and frequency](../../features/segments/recency-and-frequency.md) controls to any [rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) that contain actionable signals. これによって、例えば、メディアキャンペーン内で特定のクリエイティブがあるユーザーに対して表示される回数を制限するフリークエンシーキャップを有効にできます。他にも以下のようなユースケースがあります。

### ユーザーの再ターゲット化

クリエイティブ 123 が表示されたもののクリックまたはコンバージョンが発生しなかったユーザーを再ターゲットし、クリエイティブ 456 を表示するには、以下の手順に従います。

1. クリエイティブが表示されたユーザーを取得する特性を作成します。Let&#39;s say you name the trait [!DNL Creative Trait 123]. 次の特性ルールを使用します。

   `d_creative == 123 AND d_event == imp`

1. クリックまたはコンバージョンをおこなうユーザーを取得する特性を作成します。[!DNL Click and Converter]ここに名前を付けるとします。次の特性ルールを使用します。

   `d_event == click OR d_event=conv`

1. クリエイティブ 123 が表示されたものの、クリックまたはコンバージョンが発生しなかったユーザーを割り当てるセグメントを作成します。Name it [!DNL Retarget Users] and use the segment rule:

   `Creative Trait 123 AND NOT Click and Converter`

1. Map the segment [!DNL Retarget Users] to a destination and target users in the destination with creative 456.

### オーディエンスの最適化レポートまたはオーディエンスラボで DCM フラッドライトアクティビティを使用

[Floodlight タグ](https://support.google.com/dcm/partner/answer/4293719?hl=en)を使用することで、広告主はユーザーのコンバージョンを追跡できます。With [!UICONTROL Actionable Log Files], you can track the [!DNL DCM] conversions in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md) or in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. 特性を作成し、広告サーバーログからコンバージョンを取得する次の特性ルールを使用します。

   `d_event == conv AND d_conversion == 123`

   When creating the trait in the Audience Manager [!UICONTROL UI], select [!UICONTROL Conversion] as the [!UICONTROL Event Type].

2. Once you have created the trait, the conversion will begin to be reported against in the [!UICONTROL Audience Optimization Reports] and in [!UICONTROL Audience Lab].

>[!MORE_LIKE_THIS]
>
>* [DCM データファイルを Audience Manager にインポート](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [オーディエンスの最適化レポート](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

