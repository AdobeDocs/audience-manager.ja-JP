---
description: レポートに関するよくある質問および問題点。
seo-description: レポートに関するよくある質問および問題点。
seo-title: レポートに関するよくある質問
solution: Audience Manager
title: レポートに関するよくある質問
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
feature: レポートリファレンス
exl-id: 1e6531b2-bb39-4056-9d5e-164f50955f99
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 100%

---

# レポートに関するよくある質問 {#reporting-faq}

レポートに関するよくある質問および問題点。

<br> 

<!-- 

faq_reports.xml

 -->

**新しく転送された特性について、[!UICONTROL Trait Graph]に想定より小さい値や 0 が表示されることがあるのはなぜですか？**

場合によっては、特性をアップロードした後、[!UICONTROL Trait Graph]に結果が表示されなかったり、想定より小さい数字が表示されることがあります。この状況は、受け取るデータの量が大きすぎて、受信処理ジョブで当日のレポート期限までにこの情報の収集を完了できない場合に発生します。

その結果、このデータがレポートシステムに送信されるのが遅れ、1 日（[!UICONTROL Trait Graph]のプロットに使用するレポート間隔）の間表示されなくなります。ただし、次の日の[トレンド](../reporting/trend-reports.md#trend-report-overview)レポートまたは[一般レポート](../reporting/general-reports.md#general-reports-overview)では、このデータを 7 日、14 日、30 日および 60 日のレポート間隔で表示できます。

<br> 

**[!UICONTROL Overlap]レポートで一部のセグメントが欠落しています。どこにありますか？**

必要な計算量を少なくするために、これらのレポートでは統計的な重要性が低いデータを結果から省略しています。セグメントは欠落しているのではなく、有意義な結果や、ターゲットにできるユーザーの便利なプールが得られないため省略されています。以下のページも参照してください。

* [レポートおよびデータのサンプリング方法](../reporting/report-sampling.md)
* [重複レポートと汎用レポートでのユニークユーザーのカウント](../reporting/unique-user-counts.md)

<br> 

**電子メールマーケティングキャンペーンを実行する場合に、リダイレクトされたユーザーがそのキャンペーンから来ているか、他のソースから来ているかをどのように判別すればよいですか？**

キャンペーン固有のクエリ文字列を、監視対象のサイトセクションの URL に追加します。次に、この変数をキャプチャするための特性ルールを設定します。例えば、URL が `www.test123.com/electronics?campaign=123` のような形でキャンペーン ID を渡す場合、`h_referer = 'campaign=123'` のような形式のヘッダーを検索する特性ルールを使用して、`h_referer` 変数からデータをキャプチャするための特性ルールを作成します。

<br> 

**リアルタイムカウントと合計セグメント母集団カウントにはどのような違いがありますか？**

* **リアルタイム：**&#x200B;セグメントの一部であり、設定された期間にプロパティでアクティブであるユニークユーザーの数（[!DNL Audience Manager] はそのユーザーについて特定の期間アクティビティを記録している必要があります）。

* **合計セグメント母集団：**&#x200B;現在当該のセグメントに分類されているすべてのユーザーの合計。

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**1 つの特性だけで構成されているセグメントがあります。レポート指標を見ると、カウントが一致しません。これはなぜですか？**

[セグメントビルダーにおける特性およびセグメント母集団データ](../features/segments/segment-builder-data.md)を参照してください。

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**ファイルを受信し、受信レシートには正常に処理されたレコードの数が多いことが示されていますが、レポートでは少ない数が示されています。なぜでしょうか？**

バックエンドで、転送されたデータは AAM でアクティブなユーザー（ユーザーは過去 120 日以内に [!DNL DCS] アクティビティをおこなっている）に対してのみ添付されます。そのため、[!DNL Audience Manager] で期限切れになっているユーザーのデータを転送すると、[!UICONTROL Inbound]レシートから一定数のユーザーレコードが転送されたことが通知される場合がありますが、これらのユーザーに最近のアクティビティがない場合、このデータは[!UICONTROL User Profile Store]に到達した時点で破棄されます。

<br> 

**デバイス間で転送された特性の特性ユニーク数が、転送されたレコード数より多いのはなぜですか？**

顧客 ID をキーとするデバイス間のデータプロバイダーのファイルを転送すると、Audience Manager は参照を実行し、転送された顧客 ID のそれぞれに関連付けられたすべてのデバイス ID を取得します。Audience Manager はその後、転送された特性を、顧客 ID に関連付けられているデバイス ID に割り当てます。

例えば、100 件のレコードが転送されたとします。AAM は通常、この顧客 ID のそれぞれに 3 件のデバイス ID を関連付けます。その結果、転送された特性には 300 件のデバイス ID が割り当てられます。

1 件のデバイス間顧客 ID に複数のデバイス ID を関連付けることができる理由は 2 つあります。

* ユーザーが複数のコンピューターやブラウザーから同じデバイス間アカウントにログインしている。
* ユーザーが Cookie を消去している。注意：ユーザーが「破棄」して 120 日間使用されなかった Cookie は削除されます。

<br> 

**オンボードされた特性の [!UICONTROL Total Trait Realizations] が常に「0」となるのはなぜですか？**

[!UICONTROL Total Trait Realizations] はページの読み込みに対応します。[!UICONTROL Total Trait Realizations]は、特定の特性がリアルタイムで実行された回数を提供します。この数字は、ルールベースの特性についてのみ計算されます。オンボードされた特性には、常に [!UICONTROL Total Trait Realizations] は「0」として表示されます。

<br> 

**特性を作成したところ、[!UICONTROL Trait Graph] に表示された[!UICONTROL Unique Trait Realizations]の数が[!UICONTROL Total Trait Population]よりも大きくなりました。これは正常でしょうか？**

このような状況が発生するのは、[!UICONTROL Unique Trait Realizations] がリアルタイム指標であるのに対し、[!UICONTROL Total Trait Population] を計算するためのレポートジョブはリアルタイムではないからです。[!UICONTROL Total Trait Population] は、数日間は [!UICONTROL Unique Trait Realizations] よりも大きくなります。
