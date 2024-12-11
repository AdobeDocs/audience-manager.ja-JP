---
title: Audience Manager用にデータ収集ライブラリをAppMeasurementのJavaScript ライブラリから Web SDK JavaScript ライブラリに更新します。
description: AppMeasurementのJavaScript ライブラリから Web SDK JavaScript ライブラリにAudience Managerするためにデータ収集ライブラリを更新する手順を理解します。
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: 3ba980e97763866d82bdf94109068f1f1f8f63d2
workflow-type: tm+mt
source-wordcount: '2398'
ht-degree: 0%

---


# Audience Manager用にデータ収集ライブラリをAppMeasurementのJavaScript ライブラリから Web SDK JavaScript ライブラリに更新します

## 対象読者 {#intended-audience}

このページは、[!DNL AppMeasurement] JavaScript ライブラリを使用して web データをAudience Managerに送信するAudience ManagerおよびAdobe Analyticsのお客様向けです。

現在のデータ収集方法に応じて、Web SDK への移行手順に関するガイダンスについては、次の表を参照してください。

| 既存のデータ収集方法 | Web SDK の移行手順 |
|---------|----------|
| [!DNL AppMeasurement] JavaScript ライブラリ | このガイドの手順に従ってください。 |
| [!DNL Audience Manager] [ タグ拡張機能 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | [Audience Managerタグ拡張機能から Web SDK タグ拡張機能へのデータ収集ライブラリの更新 ](dil-extension-to-web-sdk.md) の手順に従います。 |
| [!DNL AppMeasurement] JavaScript ライブラリ + [!DNL Audience Manager] [DILライブラリ ](../dil/dil-overview.md) | [Audience Managerタグ拡張機能から Web SDK タグ拡張機能へのデータ収集ライブラリの更新 ](dil-extension-to-web-sdk.md) の手順に従います。 |

## 移行の概要 {#overview}

[!DNL AppMeasurement] から [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) への移行は、主にAdobe Analyticsの移行です。 Audience Manager版のお客様の場合、この移行にはAudience Managerも含まれます。 両方を一緒に移行する必要があります。 主にAudience Managerを扱う場合は、この移行に Analytics チームを関与させます。

[!DNL AppMeasurement] をAudience Managerデータ収集に使用している場合、現在、Analytics データをAudience Managerに送信する [!DNL Server-side Forwarding (SSF)] アプローチを使用しています。 この設定では、Analytics データ収集リクエストがAudience Managerに転送され、ページに対するAudience Manager応答も処理します。

これは長年にわたる標準的なアプローチであり、現在の設定である可能性があります。 [!DNL AppMeasurement] ライブラリに `AudienceManagement` モジュールが含まれ、データ収集呼び出しにリクエスト（`/b/ss/examplereportsuite/10/`）の `/10/` パスが含まれている場合、このガイドは役に立ちます。

## サーバーサイド転送（SSF）と Web SDK データフローの比較 {#data-flows}

以下の手順では、Web SDK （およびEdge Network）に移行する際の、分析とAudience Managerの間のデータフローの違いを理解することが重要です。

サーバーサイド転送では、Analytics 地域データ収集ノードがデータを収集し、Audience Managerが受け入れるシグナルに変換してAudience Managerに送信し、Audience Managerレスポンスをページに返します。 次に、[!DNL AppMeasurement] ライブラリの [!DNL AudienceManagement] モジュールが応答を処理します（Cookie の削除、URL の宛先の送信など）。 Analytics がAdobeサーバーを使用してAudience Managerにデータを転送するため、このプロセスはサーバーサイド転送と呼ばれます。

Web SDK を使用すると、Edge Networkは、別個のアクションで Analytics とAudience Managerにデータを送信します。 Web SDK は、すべてのソリューションにデータを送信する単一のライブラリであり、Edge Networkは、ソリューションに依存しないデータポイントをソリューション固有の形式に変換します。

この新しいデータフローでは、すべてのデータがEdge Network[ データストリーム ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview) に送信され、必要に応じて、Adobeソリューションにデータを送信する [ 設定 ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) できます。 Audience Managerのために、データストリームでAudience Managerサービスを有効にすると、[!DNL XDM] および Analytics データが、Audience Managerで受け入れられるシグナルに変換されます。 また、このEdge NetworkはページへのAudience Manager応答を返します。Web SDK が応答を処理します。これは、[!DNL AppMeasurement] や [!DNL AudienceManagement] モジュールと同様です。

## タグとタグ以外の移行 {#tags-vs-non-tags}

[!DNL AppMeasurement] 拡張機能を持つタグを使用する場合でも、別のタグ管理システムの [!DNL AppMeasurement] ライブラリを使用する場合でも、ページに直接 [!DNL AppMeasurement] を配置する場合でも、Web SDK にAudience Managerを移行する手順は同じです。 Audience Managerの移行は Analytics の移行に依存するので、[!DNL AppMeasurement] から Web SDK への移行手順は、Analytics の移行中に決定されます。

この情報については、{Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) または [2}JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) ベースの実装に関する Analytics ドキュメントで説明しています。[

## XDM と `data.__adobe.` ノード {#xdm-data-nodes}

[Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) の主な機能の 1 つは、[Real-time Customer Data Platform（RTCDP） ](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home) にデータを送信することです。 これを実現し、完全な再実装を行わずに他のExperience Cloudソリューションのデータを引き続き収集するために、データ収集サーバー呼び出し内でソリューション固有のデータを区分化します。 この呼び出しでは、[ エクスペリエンスデータモデル（XDM） ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home) と呼ばれる、標準化された JSON スキーマを使用します。

ブラウザーやデバイスに関する情報など、ソリューションに依存しない要素は、所定の XDM 構造でEdge Networkに送信されます。 Edge Networkは、このデータをソリューション固有の形式に変換します。 ただし、Target、Analytics およびAudience Managerに固有のデータは、XDM ペイロード内の専用の `data.__adobe` ノードに保存されます。

例：

* Analytics 変数 `s.eVar1` は、XDM ペイロードで `data.__adobe.analytics.evar1` のように表されます。
* 顧客のロイヤルティステータスに関連する Target パラメーターは、`data.__adobe.target.loyaltyStatus` として保存されます。

データストリームでExperience Platformサービスが有効になっている場合でも、`__adobe` ノード内のデータは、Experience Platformに送信されずに、それぞれのソリューション（Analytics やAudience Managerなど）に送信されます。 つまり、Analytics とAudience Managerの現在の設定を維持しながら、必要なデータ要素を XDM スキーマ要素に柔軟にマッピングして、[ データ収集のためのデータ準備 ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) を使用したExperience Platformのリアルタイムユースケースを実現できます。

例えば、チェックアウト時に買い物かごのコンテンツをレポートするために使用される Analytics `s.products` 文字列は、元の形式で Analytics とAudience Managerに引き続き送信できます。 同時に、この文字列の要素を使用して、Experience Platformのユースケース向けにより直感的な XDM カートスキーマを作成できます。

ほとんどのAudience Manager実装はAudience Managerに転送される Analytics データに依存しているので、Audience Manager特性の式の多くは Analytics 変数（`c_evar#`、`c_prop#` および `c_events`）に基づいている可能性が高くなります。 移行時に XDM 形式を使用して特性式を再構築するのを避けるために、Edge Networkはデフォルトで設定されており、`data.__adobe.analytics` ノードで見つかった Analytics 変数をAudience Managerシグナルに変換します。 このプロセスは、サーバーサイド転送のワークフローに似ています。

Edge Networkがこの変換を実行できるのは、ページからの 1 回のデータ収集呼び出しが、複数のAdobeソリューションをフィードする 1 つのデータストリームに送信されるからです。 したがって、分析とAudience Managerの両方で [!DNL AppMeasurement] から Web SDK への移行のほとんどは、主に `data.__adobe.analytics` ノードを使用します。

Edge Networkは、XDM ペイロードおよびパケットヘッダーからのデバイスおよびブラウザーデータをAudience Manager信号に変換する。 これにより、Audience Manager特性の式で `h_` および `d_` platform キーを引き続き使用できます。

## `data.__adobe.audiencemanager` ノード {#data-note}

`data.__adobe.audiencemanager` ノードは、Analytics に依存しないAudience Manager実装に使用されます。 [tag extension migration guide](dil-extension-to-web-sdk.md) に記載されているように、[Audience Managerライブラリ ](../dil/dil-overview.md) ライブラリを介して以前に送信されたカスタムDILのキーと値のペアを格納します。

このガイドで概要を説明する移行には `data.__adobe.audiencemanager` ノードは不要ですが、ここで説明する新しいデータフローを使用すると、Analytics に記録されずにデータをAudience Managerに送信できます。

Analytics に含めずにカスタムのキーと値のペアをAudience Managerに送信する必要がある場合は、`data.__adobe.audiencemanager` ノードを使用できます。 このノードのデータセットは、データ収集サーバー呼び出しでAudience Manager変換された Analytics データに追加されます。

## この実装パスのメリットとデメリット

この移行アプローチを使用すると、メリットとデメリットの両方が生じます。 各オプションを慎重に検討し、組織に最適なアプローチを決定します。

| メリット | デメリット |
| --- | --- |
| <ul><li>**既存の実装を使用**：このアプローチには実装の変更が必要ですが、まったく新しい実装を最初から行う必要はありません。 実装ロジックへの最小限の変更で、既存のデータレイヤーとコードを使用できます。</li><li>**スキーマは必要ありません**:Web SDK への移行のこの段階では、XDM スキーマは必要ありません。 代わりに、`data` オブジェクトにデータを入力し、データをAudience Managerに直接送信できます。 Web SDK への移行が完了したら、組織のスキーマを作成し、データストリームマッピングを使用して適用可能な XDM フィールドを入力できます。 移行プロセスのこの段階でスキーマが必要だった場合、組織はAudience Manager XDM スキーマの使用を強制されます。 このスキーマを使用すると、組織が今後独自のスキーマを使用するのが難しくなります。</li></ul> | <ul><li>**実装の技術的負債**：このアプローチは既存の実装を変更した形式を使用するので、実装ロジックを追跡し、必要に応じて将来変更を実行するのは難しい場合があります。</li><li>**Platform にデータを送信するにはマッピングが必要**：組織でAdobe Experience Platformを使用する準備が整ったら、Real-Time CDPのデータセットにデータを送信する必要があります。 このアクションでは、`data` オブジェクトのすべてのフィールドが、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリである必要があります。 マッピングは、このワークフローに対して 1 回だけ行う必要があります。実装の変更は必要ありません。 ただし、XDM オブジェクトでデータを送信する場合に必要ない追加の手順です。</li></ul> |

Adobeでは、次のシナリオでこの実装パスを使用することをお勧めします。

* 既存の実装がある場合は、Adobe Analytics AppMeasurement JavaScript ライブラリを使用します。 Audience Managerタグ拡張機能を使用した実装がある場合は、代わりに [Audience Managerタグ拡張機能から Web SDK タグ拡張機能に移行 ](dil-extension-to-web-sdk.md) に従います。
* 今後Real-Time CDPを使用する予定ですが、Audience Manager実装を Web SDK 実装に最初から置き換える必要はありません。 Web SDK で実装をゼロから置き換えることは最も努力が必要ですが、最も実行可能な長期的な実装アーキテクチャも提供します。 組織がクリーンな Web SDK 実装の作業を進んで行う場合は、[Web SDK ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) を参照してください。

## Web SDK への移行に必要な手順

データ収集統合を Web SDK に移行するには、次の手順に従います。

+++**1.Analytics 実装を移行する**.

Analytics チームと協力して、{Tags[ または ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)2}JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) ベースの実装で Analytics の移行手順に従います。 [Analytics 実装を移行したら、次の手順に進みます。

+++

+++**2.データストリームにAudience Managerサービスを追加し** す。

手順 1 で作成したデータストリームにAudience Managerサービスを追加します。

1. [experience.adobe.com](https://experience.adobe.com) に移動し、資格情報を使用してログインします。
1. 右上のホームページまたは製品セレクターを使用して、**[!UICONTROL Data Collection]** に移動します。
1. 左側のナビゲーションで、「**[!UICONTROL Datastreams]**」を選択します。
1. 手順 1 の Analytics 移行の一部として作成したデータストリームを選択します。
1. 「**[!UICONTROL Add Service]**」を選択します。
1. サービス ドロップダウンメニューで、「**[!UICONTROL Audience Manager]**」を選択します。
1. 「**[!UICONTROL Cookie Destinations Enabled]**」オプションと「**[!UICONTROL URL Destinations Enabled]**」オプションをオンにします。 これらのオプションを使用すると、Edge Networkは、これらのAudience Managerの宛先タイプをページに返すことができます。
1. **[!UICONTROL Enable XDM Flattened Fields]** が無効になっていることを確認します。 このオプションを選択すると、Analytics 変数からAudience Managerシグナルへの自動変換が無効になります。 このオプションは、Edge Networkが Analytics データをAudience Managerシグナルに自動変換する前に Web SDK に移行したユーザーの後方互換性を維持するように設計されています。

   >[!NOTE]
   >
   >**[!UICONTROL Enabled XDM Flattened Fields]** オプションを有効にして Web SDK に移行するには、XDM 形式のAudience Managerで必要なデータと、prop、eVar またはイベントを使用するすべてのAudience Manager特性を、代わりに XDM 形式のデータを検索するように更新する必要があります。 Adobeは、このオプションを無効のままにすることをお勧めします。


   ![Audience Managerサービスを追加 ](assets/add-service.png) {style="border:1px solid lightslategray"}

1. 「**[!UICONTROL Save]**」を選択して、データストリーム設定を保存します。

これで、データストリームがデータを受け取り、Audience Managerに渡す準備が整いました。 データストリーム ID をメモします。この ID は、コードで Web SDK を設定する際に必要になるからです。

+++

+++**3.サードパーティ ID 同期を有効にし、Audience Managerコンテナ ID を設定し** す。

1. [experience.adobe.com](https://experience.adobe.com) に移動し、資格情報を使用してログインします。
1. 右上のホームページまたは製品セレクターを使用して、**[!UICONTROL Data Collection]** に移動します。
1. 左側のナビゲーションで、「**[!UICONTROL Datastreams]**」を選択します。
1. 手順 1 の Analytics 移行の一部として作成したデータストリームを選択します。
1. データストリーム設定ページの右上隅にある「**[!UICONTROL Edit]**」を選択します。
1. **[!UICONTROL Advanced Options]** ドロップダウンメニューを展開し、**[!UICONTROL Third Party ID Sync]** 機能がまだ有効になっていない場合は有効にします。 このオプションは、Audience ManagerおよびExperience Platformデータパートナーのパートナー ID 同期を返すようにEdge Networkに指示します。

   ![ サードパーティ ID 同期を有効にする ](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. ほとんどの場合、「**[!UICONTROL Third Party ID Sync Container ID]**」フィールドは空白のままにできます。 デフォルトで `0` になります。 ただし、適切なコンテナ ID を使用する場合は、次の手順に従います。
   * ブラウザーウィンドウを匿名モードまたはプライベートモードで開き、移行の一部であるページに移動します。
   * ブラウザーの開発者ツールを使用して、`dpm.demdex.net/id` へのネットワーク呼び出しについてフィルタリングします。 この呼び出しは、最初の訪問の最初のページでのみ実行されるので、匿名ブラウザーまたはプライベートブラウザーが必要になります。
   * リクエストのペイロードを表示します。 `d_nsid` パラメーターが 0 とは異なる場合は、**[!UICONTROL Third Party ID Sync Container ID]** フィールドにコピーします。

1. 「**[!UICONTROL Save]**」を選択します。

これで、データストリームで、Audience Managerにデータを送信し、Audience Manager応答を Web SDK に渡す準備が整いました。

+++

## Analytics Report Suite Manager UI でのサーバーサイド転送とAudience Analyticsの設定 {#configure-ssf-analytics}

Analytics の [ サーバーサイド転送 ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) 機能を熟知している場合は、「*Analytics レポートスイートマネージャー UI のサーバーサイド転送設定を無効にして、Analytics データがAudience Managerに 2 回送信されないようにする必要がありますか？*」と疑問に思うかもしれません。

答えは「いいえ」です。この設定を無効にしないでください。 その理由は次のとおりです。

この設定が有効になっていると、[!DNL AudienceManagement] モジュールがページの [!DNL AppMeasurement] ライブラリに追加され、そのレポートスイートに送信されるすべてのデータもAudience Managerに送られます。

GDPR のプライバシー規制に準拠するために、Analytics でデータを収集してもAudience Managerでは収集できないシナリオがあります。 さらに、グローバルレポートスイートに関するケースや、一部のデータ収集呼び出しをAudience Managerに送信すべきでない地域固有のユースケースもあります。 これを解決するために、Adobeは、サーバーサイド転送の「オフボタン」を導入しました。

サーバーサイド転送に重点を置いた [Analytics と GDPR コンプライアンスのページ ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr) で説明したように、`cm.ssf=1` コンテキスト変数を Analytics データ収集サーバーに追加すると、データ収集呼び出しがAudience Managerに転送されるのを防ぐことができます。

この設定を無効にしない理由は 2 つあります。

1. データストリームでAudience Managerサービスが有効になっている場合、Edge Networkは、Analytics に送信されるすべてのデータ収集リクエストに `cm.ssf` 変数を追加します。 これにより、Analytics データがAudience Managerにも送信されなくなります。 AnalyticsAudience Managerの検証に使用されるAssurance ログでは、移行サービスがデータストリームで有効になっている場合に、`cm.ssf=1` 変数が表示されます。
1. また、この設定により、[!DNL Audience Analytics] 統合のデータフローが有効になります。 [ 統合の概要 ](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam) で説明しているように、このAudience Analyticsではサーバーサイド転送が必要です。これは、Analytics データ収集サーバーに対するAudience Manager応答が処理前に Analytics ヒットに追加されるからです。 Edge Network内でも同様のプロセスが行われます。 サーバーサイド転送が有効な場合、Edge Networkは Analytics に送信されるデータに対して、Audience Managerレスポンスから必要なセグメントを追加します。

まとめると、Audience Analyticsが Web SDK 実装で引き続き機能し、Audience Managerでデータが二重にカウントされないように、この設定を有効にしておくことが重要です。
