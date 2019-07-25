---
description: Audience Marketplace データ購入者は、広告インプレッション数 1,000 回あたりのコスト（CPM）単位の価格で、データフィードに含まれる特性を使用して提供されたすべての広告インプレッション数をレポートすることに同意します。CPM 使用は、毎月 5 日を期限とし、前月のデータが含まれます。定額サブスクリプション購入者は、使用をレポートする必要はありません。
seo-description: Audience Marketplace データ購入者は、広告インプレッション数 1,000 回あたりのコスト（CPM）単位の価格で、データフィードに含まれる特性を使用して提供されたすべての広告インプレッション数をレポートすることに同意します。CPM 使用は、毎月 5 日を期限とし、前月のデータが含まれます。定額サブスクリプション購入者は、使用をレポートする必要はありません。
seo-title: データフィードバイヤーに対する請求
solution: Audience Manager
title: データフィードバイヤーに対する請求
topic: DIL API
uuid: d7236667-282b-4160-9909-579721af4016
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# データフィードバイヤーに対する請求 {#billing-for-data-feed-buyers}

Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions ([!DNL CPM]) basis. [!DNL CPM] 使用は、毎月 5 日を期限とし、前月のデータが含まれます。定額サブスクリプション購入者は、使用をレポートする必要はありません。

## CPM の使用状況の報告方法 {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] データ購入者は、広告インプレッション数 1,000 回あたりのコスト（）単位の価格で、データフィードに含まれる特性を使用して提供されたすべての広告インプレッション数をレポートすることに同意します。[!DNL CPM][!DNL CPM] の使用状況は毎月 5 日を期限とし、前月のデータが含まれます。定額サブスクリプション購入者は、使用をレポートする必要はありません。

[!UICONTROL Audience Marketplace] には、使用状況をレポート [!DNL CPM] する2つの方法があります。

* **セグメントレベルのレポート**[!DNL CPM]：こちらが推奨される の使用状況のレポート方法です。When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts, based on the algorithms described in [Cost Attribution for CPM Data Feeds](#cost-attribution).
* **データフィードレベルのレポート**[!DNL CPM]：この方法では、[ データフィードのコスト配分](#cost-attribution)で説明しているアルゴリズムに基づいて、データフィードごとに CPM 使用状況を個別にレポートする必要があります。ただし、この方法はセグメントレベルのレポートに比べて煩雑であり、エラーが生じやすくなります。

## セグメントレベルでの CPM 使用状況のレポート {#segment-level-report}

「[!UICONTROL Segment Usage]」タブには、セグメントがマッピング先の宛先ごとにグループ化されて表示され、セグメントレベルでの使用状況をレポートすることができます。

After reporting [!DNL CPM] usage at segment level, [!UICONTROL Audience Marketplace] automatically assigns the corresponding data feeds the correct usage, based on the [Cost Attribution for CPM Data Feeds](#cost-attribution).

To report [!DNL CPM] usage at segment level:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
2. **[!UICONTROL Segment Usage]** タブを選択します。
3. セグメントの使用量を入力します。使用状況をレポートする必要があるセグメントが一部に限られている場合は、「[!UICONTROL Search]」ボックスを使用して、セグメントをフィルタリングできます。
4. **[!UICONTROL Edit Segments Usage]**&#x200B;をクリックします。
5. Enter the [!DNL CPM] usage amount in the [!UICONTROL Usage] column.
6. 入力が完了したら「**[!UICONTROL Save]**」をクリックして、確認ダイアログで内容を確認します。
   ![confirm-segment-usage](assets/confirm-segment-usage.png)
7. **[!UICONTROL Confirm]**&#x200B;をクリックします。

## データフィードレベルでの CPM 使用状況のレポート {#feed-level-report}

Data feed-level reporting is a more tedious and prone to error process, since you must individually calculate [!DNL CPM] usage for each data feed. 代わりに、[セグメントレベルでの CPM 使用状況のレポート](#segment-level-report)をお勧めします。

To report [!DNL CPM] usage at segment level:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
2. **[!UICONTROL Feed Usage]** タブを選択します。
3. 「[!UICONTROL Search]」ボックスを使用してデータフィードをフィルタリングし、使用量をレポートするデータフィードを見つけます。
4. **[!UICONTROL Edit Feeds Usage]**&#x200B;をクリックします。
5. Calculate the [!DNL CPM] usage for each data feed based on the [Cost Attribution for CPM Data Feeds](#cost-attribution), and enter it in the [!UICONTROL Usage] column.
6. 入力が完了したら「**[!UICONTROL Save]**」をクリックして、確認ダイアログで内容を確認します。

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. **[!UICONTROL Confirm]**&#x200B;をクリックします。

## 一括レポート

[!DNL CPM] レポートの使用中にエラーとオーバーヘッドを軽減するには、バルクレポートオプションを使用して、データフィードおよびセグメントを含む [!DNL CSV] ファイルをダウンロードし、使用状況に記入してアップロードします [!DNL Audience Manager]。一括レポートは、フィードの使用量およびセグメントの使用量の両方に使用できます。

To update [!DNL CPM] usage in bulk:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
1. Select the **[!UICONTROL Feed Usage]** or **[!UICONTROL Segment Usage]** tab, depending on the type of reporting that you want to update.
1. Click **[!UICONTROL Edit Feeds Usage]** or **[!UICONTROL Edit Segments Usage]**.
1. Click **[!UICONTROL download the current usage]** to make sure you use a valid CSV file.
1. ダウンロードしたファイルをコンピューター上で開き、使用状況レポートに入力します。
1. Click **[!UICONTROL Choose a CSV file]** to upload the updated usage report.

   ![usage-report-csv](assets/usage-report-csv.png)

1. ファイルはアップロード後すぐに [!DNL Audience Manager] により検証され、エラーが検出された場合はメッセージが表示されます。

### 一括レポートの検証エラー

| エラーメッセージ | 説明 | 対策 |
| ------------- | -------------| -----|
| Invalid Input | [!DNL Audience Manager][!DNL CSV] で、列の不足や列タイトルの変更など、 ファイルスキーマの変更が検出されました。 | テーブルの構造は変更しないでください。 |
| Not Found | For [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. | For [!UICONTROL Segment Level Reporting], check the validity of the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], check the validity of the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. |
| Duplicate Records Found | [!DNL Audience Manager] で、インプレッションの値が異なる重複したレコードが検出されました。 | レポートをチェックして、同じデータフィードまたはセグメントについて複数の使用量の値をレポートしていないか確認してください。 |
| Values Not Supported | [!DNL Audience Manager] で、[!DNL Audience Manager] 列に数字以外の値が検出されました。 | レポートをチェックして、[!DNL Audience Manager] 列に数値のみを入力していることを確認してください。 |
| Headers for Mandatory Fields Missing | [!DNL Audience Manager] で、必須フィールドのテーブルヘッダーが不足していることが検出されました。For [!UICONTROL Segment Level Reporting], the mandatory fields are: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. For [!UICONTROL Feed Level Reporting], the mandatory fields are: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | レポートをチェックして、テーブルヘッダーが変更されていないことを確認してください。 |

>[!NOTE]
>[!DNL CSV] 使用状況レポートから行を削除しても、既存の使用状況レポートには影響しません。[!DNL Audience Manager] では、レポートに含まれているフィールドのみが処理されます。

## [!DNL CPM] レポートのベストプラクティス

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommendations </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>常にインプレッションの合計数をレポートする</b> </p> </td> 
   <td colname="col2"> <p>CPM インプレッションの合計数の場合： </p>
   <p> 小数を使用せずに、インプレッションの合計数をレポートします。Audience Managerは、レポートの合計数に基づいてCPMを自動的に計算します。</p><p>1,234,567 個のインプレッションをレポートする場合は、この数字をそのままレポートしてください。インプレッションの合計数を 1,000 で割って、CPM を算出する必要はありません。</p><p>Adobe TargetやAnalyticsの宛先などのツールを使用してWebまたはアプリコンテンツ（コンテンツの最適化）を最適化するために使用される特性は、CPMプランの使用の合計には貢献しません。データプロバイダーは通常、定額プランを使用してコンテンツ最適化による報酬を得ています。</p><p>詳しくは、<a href="#cost-attribution">CPM データフィードのコスト配分</a>を参照してください。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>毎月の報告期限を順守する</b> </p> </td> 
   <td colname="col2"> <p>レポートシステムは、毎月 5 日にクローズします。この日までに CPM の使用状況を報告できなかった場合、その分を翌月のレポートに追加しなければなりません。例えば、10 月に 1000 件のインプレッションを使用して、10 月分の締切までに報告できず、11 月には 1000 件のインプレッションを使用したとします。この場合、10 月と 11 月の合計（2000）を、12 月 1 日から 5 日までの間に報告します。</p><p><b>ヒント</b>:今月の最初の月と5日目の間のCPM使用量は、常に報告してください。</p><p>CPM の使用状況の報告締切日は翌月 5 日ですが、推奨はされていません。各月5日より前にCPMの使用を報告すると、Audience Managerの時間がデータのチェックおよび処理に費やされます。</p> </td>
  </tr> 
 </tbody> 
</table>

## CPM データフィードのコスト配分 {#cost-attribution}

[!UICONTROL Audience Marketplace] では、ユーザーがセグメントごとに各月のインプレッションの量を自己申告する必要があります。We recommend reporting [!DNL CPM] usage at segment level, so that cost attribution is done automatically.

<!-- marketplace_cpm_billing.xml -->

### 請求の概要 {#billing-summary}

You must submit [!DNL CPM] data feed impression amounts between the 1st and the 5th days of each calendar month. これを適切におこなうために、[セグメントレベルでの CPM 使用状況のレポート](#segment-level-report)をお勧めします。

>[!TIP]
>When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts.

Should you need to [!UICONTROL Report CPM Usage at Data Feed Level], you must individually compile all impressions delivered for each feed in the previous calendar month, and report them according to the billing allocation described in this article.

After you report [!DNL CPM] number for the previous calendar month, [!DNL Adobe] will do the following:

* Create an invoice and bill you based on the [!DNL CPM] rate for each subscribed data feed.
* Pay data providers (sellers) fees owed based on your reported [!DNL CPM] use.

>[!IMPORTANT]
>
>バイヤーとして報告するインプレッションの合計は、真実かつ正確でなければなりません。インプレッションの合計を毎月 5 日までに報告しない場合、報告されていない分の月の合計は翌月に報告しなければなりません。

## 特性認定ルールに基づくフィードレベルでのインプレッションの配分 {#assign-impressions}

[!UICONTROL Activation] ユースケースでは、[セグメントビルダー](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74)で対応するデータフィードの特性を使用してセグメントを作成し、宛先にマッピングすることができます。The Boolean operators [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT] let you set the conditions for trait and segment qualification.

[データフィードレベルで CPM 使用状況をレポートする](#feed-level-report)場合は、特性の認定ルールで使用する [!DNL Boolean] 演算子に従い、各データフィードにインプレッションを比例配分する必要があります。次の表は、ブール演算ルールまたは特性タイプによりインプレッションを適切に配分する方法を示しています。

>[!TIP]
>[セグメントレベルでの CPM 使用状況のレポート](#segment-level-report)では、Audience Manager により、データフィードレベルでのレポートが自動でおこなわれます。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ルール認定のロジックまたはタイプ </th> 
   <th colname="col2" class="entry"> 請求配分 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> AND</span> </p> </td> 
   <td colname="col2"> <p>配信されたインプレッション合計の 100％を、ブール演算子 <span class="wintitle">AND</span> 条件を使用するルールベースのセグメントのすべてのプロバイダー特性に適用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OR</span> </p> </td> 
   <td colname="col2"> <p>ブールOR条件を使用するルールベースのセグメントのすべてのプロバイダー特性に、配信されたインプレッションの合計の重み付き割り当てを適用します。重み付け配分は次の数式で計算します。</p><p><code>(特性の母性集団 / セグメント母集団) * インプレッション数 * CPM のコスト</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle">NOT</span> </p> </td> 
   <td colname="col2"> <p>配信されたインプレッション合計の 100％を、ブール演算子 <span class="wintitle">NOT</span> 条件を使用するルールベースのセグメントのすべてのプロバイダー特性に適用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アルゴリズムセグメント </p> </td> 
   <td colname="col2"> <p>配信されたインプレッション合計の 100％を、アルゴリズム特性を含むセグメントのすべてのプロバイダーフィードに適用します。 </p> </td> 
  </tr>
 </tbody>
</table>

## 請求の例 {#billing-examples}

The examples below are meant to illustrate how [!DNL CPM] usage allocation is done at data feed level.

>[!MPORTANT]
>この方法の代わりに、処理が自動でおこなわれる[セグメントレベルでの CPM 使用状況のレポート](#segment-level-report)をお勧めします。

次のシナリオを考えてみましょう。

![請求例](assets/billing-examples.png)

### ケース 1：AND 認定ルールを使用するセグメント

このセグメントには、別々のデータプロバイダーからの特性が 3 件あります。セグメント認定は [!UICONTROL AND] 条件に基づいているので、訪問者がセグメントの対象として認定されるには、3 つすべてのフィードからの特性を適合する必要があります。

![](assets/billing-segment-and.png)

[!UICONTROL AND] 条件を使用する場合、月内に受け取ったインプレッションの 100％を、3 つすべてのデータプロバイダーに割り当てる必要があります。[!UICONTROL Audience Marketplace > Payables] このセクションでは、1,000,000インプレッションの各プロバイダーにクレジットを与えます。

この例は、[!DNL Boolean][!UICONTROL NOT] 演算子を使用するセグメント、またはアルゴリズム特性を含むセグメントに該当します。

### ケース 2：OR 認定ルールを使用するセグメント

このセグメントには、別々のデータプロバイダーからの特性が 3 件あります。セグメント認定は [!UICONTROL OR] 条件に基づいているので、訪問者がセグメントの対象として認定されるには、3 つのフィードのうち少なくとも 1 つからの特性を適合する必要があります。

認定は [!UICONTROL OR] 条件に基づいているので、どちらの特性がインプレッションに対応しているかは判別できません。As a result, in the [!UICONTROL Audience Marketplace > Payables] section you credit each provider with a weighted allocation of the total impressions, based on trait population.

![billing-segment-or](assets/billing-segment-or.png)

>[!MORE_LIKE_THIS]
>
>* [定額データフィードに関する請求およびインプレッションの割り当て](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)


## 定額データフィードに関する請求およびインプレッションの割り当て {#billing-flat-fee}

定額料金のデータフィードでは、サブスクリプションの開始日や使用するインプレッションの数にかかわらず、毎月一定額が請求されます。1 ヶ月未満の使用または未使用期間について、費用は日割り計算されません。CPM 請求と同様に、アドビは、請求書を生成し、登録されたデータフィードに対して定額料金で毎月請求します。

例えば、月の半ばで特定の特性を有効にするとします。この場合、購読を開始した時点や特定の特性を有効にした時点にかかわらず、月額の全額が請求されます。