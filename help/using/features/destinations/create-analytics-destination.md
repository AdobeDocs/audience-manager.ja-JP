---
description: オーディエンス分析では、Audience Manager のセグメントを Analytics に送信できます。この機能を使用するには、Analytics の宛先を作成して、Audience Manager でセグメントをその宛先にマッピングします。
seo-description: オーディエンス分析では、Audience Manager のセグメントを Analytics に送信できます。この機能を使用するには、Analytics の宛先を作成して、Audience Manager でセグメントをその宛先にマッピングします。
seo-title: Analytics の宛先の設定
solution: Audience Manager
title: Analytics の宛先の設定
translation-type: tm+mt
source-git-commit: 3179b9007e102f7031cc4cc9e0da64f77cfa3eeb

---


# Analytics の宛先の設定

## 要件 {#requirements}

[オーディエンス分析](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/)を参照してください。

## Analytics のデフォルトの宛先と新規の宛先

| Analytics の宛先のタイプ | 説明 |
|---|---|
| デフォルト | このデフォルトの宛先は「Adobe Analytics」という名前になっていますが、編集することができます。マッピングされたレポートスイート ID が Audience Manager の特性およびセグメントのフォルダーストレージに表示されます。<br>アカウントに含まれる場合、Audience Managerは自動的に1つの宛先を作成します。 <br> <ul><li>[オーディエンス分析](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/)のドキュメントで説明している要件を満たしている。</li><li>Analytics に[レポートスイート](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html)がある。</li><li>[レポートスイートを組織にマッピングしてある](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)。</li></ul> |
| 新規 | Analytics の宛先を新規作成するには、Audience Data／Destinations／Create New Destination を選択し、以下で説明している各セクションの手順に従います。 |

## 手順 1：基本情報の提供

このセクションには、Analytics の宛先の作成プロセスを開始するフィールドとオプションが含まれています。このセクションを完了するには：

1. 「**Basic Information**」をクリックして、コントロールを表示します。
2. 宛先の名前を入力します。略語や特殊文字は使用しないでください。
3. *（オプション）*宛先の説明を入力します。簡潔な説明が、宛先を定義するのに効果的です。
4. *（オプション）*「**Platform**」リストをデフォルトの「**All**」のままにしておきます。現時点では、このオプションは機能しません。今後追加される可能性のある機能をサポートするために設計されています。
5. 「**Category**」リストで「**Adobe Experience Cloud**」を選択します。
6. 「**Type**」リストで「**Adobe Analytics**」を選択します。
7. 「**Save**」をクリックして「Configuration」セクションに移動するか、「**Data Export Controls**」をクリックして書き出しコントロールを宛先に適用します。

>[!NOTE]
>
>For an Analytics destination, the **Auto-fill Destination Mappping** check box and **Segment ID** option are selected by default. これらの設定を変更することはできません。

![basicinformation](assets/basicinformation.png)

## 手順 2：データ書き出しコントロールの設定

このセクションには、[データ書き出しコントロール](/help/using/features/data-export-controls.md)を Analytics の宛先に適用するオプションが含まれています。データ書き出しコントロールを使用しない場合は、この手順を省略してください。このセクションを完了するには：

1. 「**Data Export Controls**」をクリックして、コントロールを表示します。
2. 宛先に適用するデータ書き出しコントロールに対応するラベルを選択します（詳しくは [宛先へのデータ書き出しラベルの追加](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) ). Analytics の宛先の場合は、PII のチェックボックスがデフォルトで選択されています。
3. 「**Save**」をクリックします。

![exportcontrols](assets/exportControls.png)

## 手順 3：レポートスイートのマッピング

「Configuration」セクションでは、サーバー側転送が有効になっている Analytics レポートスイートが一覧表示されます。Analytics の宛先が複数ある場合は、それらの宛先に割り当てられたレポートスイートは相互に排他的で、Audience Manager によって実行されます。このセクションを完了するには：

1. 「**Configuration**」をクリックして、コントロールを表示します。
2. セグメントの送信先となるレポートスイートを 1 つ以上選択します。
3. 「**Save**」をクリックします。

![レポートスイート](assets/reportSuites.png)

## 手順 4：セグメントマッピング

このセクションには、セグメントを自動的にまたは手動でマッピングできるオプションが用意されています。

| マッピングオプション | 説明 |
|---|---|
| Automatically map all current and future segments | デフォルトで選択されています。訪問者が資格を満たすすべてのセグメントが、ヒットごとに Analytics に送信されます。<br>訪問者が1回のヒットで150を超えるAudience Managerセグメントに属する場合、150番目の最新のセグメントのみがAnalyticsに送信され、残りのリストは切り捨てられます。セグメントリストが切り捨てられたことを示す追加フラグが Analytics に送信されます。このアクションで、Audiences Name ディメンションに「Audience limit reached」と表示され、Audiences ID ディメンションに「1」と表示されます。詳しくは、[FAQ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) を参照してください。<br>また、このオプションはセグメントビルダーで [の宛先の可用性にも影響](/help/using/features/segments/segment-builder.md)します。For example, if a segment is mapped automatically to an Analytics destination, that destination is not available for selection in the [destination mappings](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) section of Segment Builder. Analytics の宛先がグレー表示され、宛先ブラウザーの「Type」列に「Analytics」と表示されます。 |
| Manually map segments | このオプションを選択すると、Analytics に送信するセグメントを選択できる検索および参照コントロールが表示されます。<br>セグメントを検索するには: <br> <ol><li>セグメント名またはセグメント ID を検索フィールドに入力します。</li><li>Click <b>Add.</b></li><li>セグメントの検索と追加を続けるか、「<b>Done</b>」をクリックします。</li></ol><br>セグメントを参照するには: <ol><li>「<b>Browse all segments</b>」をクリックします。使用可能なセグメントのリストが表示されます。</li><li>このリストから、使用するセグメントのチェックボックスを選択し、「<b>Add selected segments</b>」をクリックします。</li><li>Add Mappings ウィンドウの「<b>Save</b>」をクリックします。ベータリリースの間は、マッピング、開始日、終了日を変更することはできません。</li><li>セグメントの参照と追加を続けるか、「<b>Done</b>」をクリックします。</li></ol> |

![mapsegments](assets/mapSegments.png)

## 次の手順

宛先を作成して保存したら、そのデータを Analytics で扱うことができます。ただし、選択したレポートスイートでデータが使用可能になるまで、数時間かかることがあります。詳しくは、[Analytics でのオーディエンスデータの使用](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html)を参照してください。



