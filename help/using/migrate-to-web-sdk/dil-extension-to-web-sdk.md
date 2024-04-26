---
title: Audience Managerタグ拡張機能から Web SDK タグ拡張機能に移行します
description: Audience Managerタグ拡張機能から Web SDK タグ拡張機能にAudience Managerするためにデータ収集ライブラリを更新する手順を理解します
source-git-commit: c80f39c4001d2bcfa94012b9f4ffa720806487d4
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---


# Audience Manager用にデータ収集ライブラリをAudience Managerタグ拡張機能から Web SDK タグ拡張機能に更新します

## 対象読者

このページは、を使用するAudience Managerユーザーを対象としています [Audience Managerタグ拡張機能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) ウェブ収集データをAudience Manager化する。 AppMeasurement JavaScript ライブラリを使用しているお客様の場合は、データ収集ライブラリをAudience Manager用に更新する方法に関するガイドを参照してください [AppMeasurement JavaScript ライブラリから Web SDK JavaScript ライブラリへ](appmeasurement-to-web-sdk.md).

## この実装パスのメリットとデメリット

この移行アプローチを使用すると、メリットとデメリットの両方が生じます。 各オプションを慎重に検討し、組織に最適なアプローチを決定します。

| メリット | デメリット |
| --- | --- |
| <ul><li>**サイトにコードの変更はありません**：実装には既にタグがインストールされているので、移行に関するすべての更新をタグインターフェイスで行えます。</li><li>**既存の実装を使用**：このアプローチでは、まったく新しい実装は必要ありません。 新しいルールのアクションが必要になる場合でも、最小限の変更で、既存のデータ要素とルール条件を再利用できます。</li><li>**スキーマは必要ありません**:Web SDK への移行のこの段階では、XDM スキーマは必要ありません。 代わりに、にデータを入力できます `data` オブジェクト。Adobe Audience Managerにデータを直接送信します。 Web SDK への移行が完了したら、組織のスキーマを作成し、データストリームマッピングを使用して適用可能な XDM フィールドを入力できます。 移行プロセスのこの段階でスキーマが必要だった場合、組織はAdobe Audience Manager XDM スキーマの使用を強制されます。 このスキーマを使用すると、組織が今後独自のスキーマを使用するのが難しくなります。</li></ul> | <ul><li>**技術的債務の履行**：このアプローチは既存の実装の変更済み形式を使用するので、実装ロジックを追跡し、必要に応じて変更を実行するのが難しい場合があります。 カスタムコードは特にデバッグが困難な場合があります。</li><li>**Platform にデータを送信するには、マッピングが必要です**:Real-Time CDPを使用する準備が整ったら、Adobe Experience Platformのデータセットにデータを送信する必要があります。 このアクションでは、のすべてのフィールドが `data` オブジェクトは、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリです。 マッピングは、このワークフローに対して 1 回だけ行う必要があります。実装の変更は必要ありません。 ただし、XDM オブジェクトでデータを送信する場合に必要ない追加の手順です。</li></ul> |

Adobeでは、Adobe Audience Manager タグ拡張機能を使用する既存の実装がある場合は、この実装パスに従うことをお勧めします。

## Web SDK への移行に必要な手順

以下の手順には、取り組むべき具体的な目標が含まれています。 各手順を選択すると、実行方法に関する詳細な手順が表示されます。

+++**1.データストリームの作成と設定**

Adobe Experience Platform Data Collection でデータストリームを作成するには、以下の手順に従います。 このデータストリームにデータを送信すると、データがAudience Managerに転送されます。 今後、この同じデータストリームがReal-Time CDPにデータを転送します。

1. に移動します。 [experience.adobe.com](https://experience.adobe.com) 認証情報を使用してログインします。
1. 右上のホームページまたは製品セレクターを使用して、に移動します **[!UICONTROL Data Collection]**.
1. 左側のナビゲーションで、を選択します。 **[!UICONTROL Datastreams]**.
1. を選択 **[!UICONTROL New Datastream]**.
1. 目的の名前を入力し、を選択します **[!UICONTROL Save]**.
1. データストリームを作成したら、次を選択します。 **[!UICONTROL Add Service]**.
1. サービスのドロップダウンメニューで、を選択します **[!UICONTROL Adobe Audience Manager]**.
1. 必ずを実行してください **[!UICONTROL Enable XDM Flattened Fields]** オプションはオフです。

   ![Audience Managerサービスを追加](assets/add-service.png) {style="border:1px solid lightslategray"}

これで、データストリームがデータを受け取り、Audience Managerに渡す準備が整いました。

+++

+++**2.タグプロパティに Web SDK 拡張機能を追加します**

この節では、次の手順で行われる移行作業の大部分のためにタグを準備します。

1. Adobe Experience Platform インターフェイスの左上にあるハンバーガーアイコンを選択してから、を選択します。 **[!UICONTROL Tags]**.
1. 目的のタグプロパティを選択します。
1. タグプロパティの左側のナビゲーションで、 **[!UICONTROL Extensions]**.
1. を選択 **[!UICONTROL Catalog]** 上部の近くに、使用可能なすべての拡張機能のリストが表示されます。
1. を検索して選択します。 **[!UICONTROL Adobe Experience Platform Web SDK]** 拡張機能を選択してから、 **[!UICONTROL Install]** 右側です。

   ![カタログ](assets/catalog.png) {style="border:1px solid lightslategray"}

1. 拡張機能の設定が表示されます。 を見つけます。 **[!UICONTROL Datastreams]** を選択し、使用しているサンドボックスと、前の手順で作成したデータストリームを選択します。

   ![データストリームの選択](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. を選択 **[!UICONTROL Save]**.

これで、タグプロパティに Web SDK がインストールされました。

+++

+++**3.データオブジェクトデータ要素の作成**

データオブジェクトデータ要素は、Web SDK がデータストリームに送信するために使用するペイロードを設定するための直感的なフレームワークを提供します。 次の手順で更新するほとんどのルールは、このデータ要素とやり取りします。

1. タグインターフェイスの左側のナビゲーションで、 **[!UICONTROL Data Elements]**.
1. を選択 **[!UICONTROL Add Data Element]**
1. データ要素に次の設定を行います。
   * **[!UICONTROL Name]**:「データレイヤー」や「データオブジェクト」など、必要なもの
   * **[!UICONTROL Extension]**：[!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**：[!UICONTROL Variable]
   * チェックボックスは、そのまま残すことができます。
1. 右側で、次の設定を選択します。
   * プロパティラジオボタン： **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**：[!UICONTROL Adobe Audience Manager]
1. を選択 **[!UICONTROL Save]**.

   ![データ要素の作成](assets/create-data-element.png) {style="border:1px solid lightslategray"}

これで、タグプロパティに、各ルールを更新するために必要なすべてが揃いました。

+++

+++**4.Audience Manager拡張機能の代わりに Web SDK 拡張機能を使用するようにルールを更新します**

この手順には、Web SDK への移行に必要な作業の大部分が含まれており、実装の仕組みに関する知識が必要です。 一般的なタグルールの編集方法の例を以下に示します。 Audience Manager拡張機能へのすべての参照を Web SDK 拡張機能に置き換えるために、実装内のすべてのタグルールを更新します。

1. タグインターフェイスの左側のナビゲーションで、 **[!UICONTROL Rules]**.
1. 編集するルールを選択します。
1. アクションを選択 **[!UICONTROL Audience Manager - Set Variables]**
1. このルール内で設定されたすべてのAudience Manager変数に注意してください。 ドロップダウンメニューで設定された変数と、カスタムコード内で設定された変数の両方を含めます。
1. 変更： [!UICONTROL Action Configuration] を次の設定に変更します。
   * **[!UICONTROL Extension]**：[!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**：変数を更新
1. 手順 3 で作成したデータオブジェクトが、右側のドロップダウンで選択されていることを確認します。 **[!UICONTROL Data element]** フィールド。
1. Audience Managerのキーと値のペアを、Audience Manager拡張機能で設定したのと同じ値に設定します。
1. Web SDK 拡張機能を使用してすべてのルールロジックをレプリケートしたら、次を選択します。 **[!UICONTROL Keep Changes]**.
1. Audience Managerタグ拡張機能を使用して値を設定するアクション設定ごとに、これらの手順を繰り返します。

上記の手順は、値を設定するルールにのみ適用されます。 以下の手順は、 [!UICONTROL Action Configuration] [!UICONTROL Send Event].

1. Web SDK イベントを送信するルールを選択します。
1. アクションタイプを選択します **[!UICONTROL Send Event]**.
1. 変更： [!UICONTROL Action Configuration] を次の設定に変更します。
   * **[!UICONTROL Extension]**：[!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**：[!UICONTROL Send event]
1. 右側で、アクション設定を次のように変更します。
   * **[!UICONTROL Type]**：を使用 **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]**：手順 3 で作成したデータオブジェクトを選択します。
1. を選択 **[!UICONTROL Keep Changes]**.
1. Audience Managerを使用してイベントを送信するすべてのアクション設定について、これらの手順を繰り返します。

+++

+++**5.更新されたルールの公開**

更新されたルールの公開は、タグ設定に対する他の変更と同じワークフローに従います。

1. タグインターフェイスの左側のナビゲーションで、 **[!UICONTROL Publishing Flow]**.
1. を選択 **[!UICONTROL Add Library]**.
1. このタグコミットに「Web SDK にアップグレード」などの名前を付けます。
1. を選択 **[!UICONTROL Add All Changed Resources]**.
1. を選択 **[!UICONTROL Save]**.
1. 公開ワークフローには、オレンジ色の点が表示され、ビルド中であることを示します。 ドットが緑色に変わると、変更を開発環境で使用できるようになります。
1. 開発環境で変更をテストし、すべてのルールが適切に実行され、データオブジェクトに想定される値が入力されていることを確認します。
1. 準備が整ったら、ライブラリを承認用に送信し、ステージング環境にビルドしてから、最終的に承認して実稼動環境に公開します。

   ![公開フロー](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6.Audience Manager拡張機能を無効にする**

タグ実装が Web SDK に完全に移行されたら、Audience Manager拡張機能を無効にできます。

1. タグインターフェイスの左側のナビゲーションで、 **[!UICONTROL Extensions]**.
1. を見つけて選択します。 [!UICONTROL Audience Manager] 拡張機能。 右側で、を選択します **[!UICONTROL Disable]**.
1. 上記と同じ公開ワークフローに従って、の削除を公開します [!UICONTROL Audience Manager] 拡張機能。
1. 実稼動環境で拡張機能を無効にすると、その拡張機能を完全にアンインストールできます。 拡張機能を選択し、右側の「。..」メニューを選択してから、を選択します **[!UICONTROL Uninstall]**.
1. 上記と同じ公開ワークフローに従って、変更を実稼動環境に公開します。

+++

この時点で、Audience Manager実装は Web SDK に完全に移行され、将来Real-Time CDPに移行する準備が整います。

