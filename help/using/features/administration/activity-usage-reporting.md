---
description: アクティビティの使用状況レポートは、Audience Managerインスタンスのアクティビティの使用状況を表示および追跡するのに役立ちます。これにより、実際の使用状況と契約上の取り組みを比較できます。
keywords: activity, usage, reporting, commitment
seo-description: アクティビティの使用状況レポートは、Audience Managerインスタンスのアクティビティの使用状況を表示および追跡するのに役立ちます。これにより、実際の使用状況と契約上の取り組みを比較できます。
seo-title: アクティビティ使用状況レポート
solution: Audience Manager
title: アクティビティ使用状況レポート
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 7a3914af8fb225508f57724a75fe2547aac3f241

---


# アクティビティ使用状況レポート

## 概要 {#overview}

は、Audience Manager [!UICONTROL Activity Usage Report] インスタンスのアクティビティの使用状況を表示および追跡するのに役立ち、アクティビティの使用状況と契約上のコミットメントとの比較方法を明確に把握できます。

また、記録管理とカスタム分析のた [!UICONTROL Activity Usage Report] めに、必要に応じていつでもをダウンロードできます。

## 注意点 {#considerations}

この機能 [!UICONTROL Activity Usage Report] は、管理者権限を持つすべてのAudience Managerユーザーが使 [用できます](edit-account-settings.md)。

> [!IMPORTANT]
>
> に、Audience Manager [!UICONTROL Activity Usage Report] インスタンスのアクティビティの使用状況の統計が表示されます。 アクティビティの使用に関する請求に関するお問い合わせは、アドビの担当者にお問い合わせください。

## ユースケース {#use-cases}

の主な使用例は次の2つです [!UICONTROL Activity Usage Report]。

* **アクティビティ使用率に対する実際のインスタンスアクティビティ使用量の追跡**:ほとんどのお客様は、Audience Managerインスタンスごとに毎月のアクティビティのコミットメントを見積もっており、その後、すべてのインスタンスで年間のアクティビティのコミットメントに累積されます。 このレポートは請求レポートではありませんが、コミットされたアクティビティの使用を超過しているかどうかに関する有用なガイダンスを提供できます。
* **実装の変更の検証**:Analyticsサーバー側転送の設定、Targetサーバーコールの設定の変更など、実装を最近更新した場合、このレポートは、新しいアクティビティの量が予想されるアクティビティの量と一致しているかどうかを確認するのに役立ちます。

## アクティビティの使用状況レポートの使用 {#using}

To see the [!UICONTROL Activity Usage Report], log in to your Audience Manager account, and go to **[!UICONTROL Administration]**>**[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

次に、フィルターを **[!UICONTROL Reporting Interval]**使用して、レポートを生成する時間間隔を選択します。 30日、60日、90日、またはカスタムの日付範囲を選択できます。

レポートが読み込まれると、選択した期間の内訳を [!UICONTROL Activities] 確認できます。

[!UICONTROL Activities] audience Managerとのすべてのオンサイトおよびオフサイトでのインタラクションの集計合計を定義し、次のカテゴリに分けます。

* **[!UICONTROL Server Calls]**:Webサイト、サーバー、電子メール、モバイルアプリケーション、その他のシステムからAudience Managerに送信されるデータ収集または取得イベント。
* **[!UICONTROL Pixel Calls](旧称[!UICONTROL Impression Server Calls])**:広告から収集されたデータ（ターゲットプラットフォームのインプレッション数など）またはAudience Managerに対する電子メールインプレッション呼び出し。 これらのパラメーターは、クエリ文字列 `d_event` 内にパラメーターが存在する必要があります。
* **[!UICONTROL On-Boarded Records]**:独自の顧客関係管理システム(CRM)や、コールセンターレコード、デバイスID、外部データプロバイダーからのカスタムデータフィードなど、他のオフラインデータファイルから取り込んだ一意のレコード。
* **[!UICONTROL Log File Records]**:ターゲットプラットフォームからAudience Managerに取り込まれたログファイルの一意のレコード。

> [!NOTE]
> 一意のレコードは、Audience Managerの顧客に代わってアドビが保存するファイル内のデータの個々のレコードを定義します。

また、グラフの種類を使用し [!UICONTROL Activity Usage Trends] て、2種類のグラフを切り替えることもできます。

![aur-ui-graphs](assets/aur-ui-graphs.png)

また、タイムライン内の特定の日付にカーソルを合わせて、その日付の詳細な使用方法を確認することもできます。

![aur-hover](assets/aur-hover.png)

## アクティビティ使用状況レポートのエクスポート {#export}

Audience Managerのアクティビティの使用レベルをより詳細に把握するために、含めるレコードのタ [!UICONTROL Activity Usage Report] イプに基づいてを書き出すことができます。

![aur輸出](assets/aur-export.png)

レポート **[!UICONTROL Onboarded Records Breakdown]**とレポ**[!UICONTROL Onsite Server Calls Breakdown]** ートは、これらのアクティビティで使用できるソースデータの最も詳細なインサイトを提供します。 これらの分類に関連付けられるボリュームは、実装に基づいています。

### オンボードレコードの分類 {#onboarded-breakdown}

このレポートには、データソース別に分類されたオンボードレコードが含まれています。

### Onsiteサーバーコールの分類 {#onsite-breakdown}

このレポートには、3つのソースからのサーバーコールの内訳が含まれます。 [!UICONTROL Analytics]、 [!UICONTROL Target]、、 [!UICONTROL Other]、

* **[!UICONTROL Analytics]**:これらは、すべてのAdobe AnalyticsインスタンスからAudience Managerに渡される課金対象のサーバーコールで、サーバー側転送も含まれます。 セカンダリサーバーコールまたは重複したサーバーコール（複数のレポートスイートからのサーバー側転送の場合など）は課金対象のアクティビティではないので、この分類には含まれません。
* **[!UICONTROL Target]**:これらは、Adobe targetからAudience Managerへのサーバー側呼び出しで、サーバー間統合の一環としてAudience Managerのセグメントデータを取得します。
* **[!UICONTROL Other]**:他のWebサイトまたはシステム（パートナーサイト、ダイレクトサーバーコールなど）からの呼び出し、、、、イベント呼び出し、呼び出しを介したモバイ[!DNL SDK]ルブ[!DNL DIL]ラウザー/アプリ呼び出しが含ま[!DNL DCS]れます。 また、cookie統合(サーバ[!DNL Target]ー間ではなく)として設定されている場合の呼び出しも含まれます。
