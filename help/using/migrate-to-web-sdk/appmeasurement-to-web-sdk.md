---
title: Audience Manager用にデータ収集ライブラリをAppMeasurement JavaScript ライブラリから Web SDK JavaScript ライブラリに更新します。
description: AppMeasurement JavaScript ライブラリから Web SDK JavaScript ライブラリにAudience Managerするためにデータ収集ライブラリを更新する手順を理解します。
source-git-commit: b0c35d79a07b481e332ddf8f4aedab5484416a51
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---


# Audience Manager用にデータ収集ライブラリをAppMeasurement JavaScript ライブラリから Web SDK JavaScript ライブラリに更新します

## 対象読者 {#intended-audience}

このページは、AppMeasurementを使用して web 収集データをAudience Managerに取り込むAudience Managerユーザーを対象としています。 を使用しているお客様の場合 [Audience Managerタグ拡張機能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview)を参照します。Audience Manager用にデータ収集ライブラリを更新する方法については、ガイドを参照してください [Audience Managerタグ拡張機能から Web SDK タグ拡張機能へ](dil-extension-to-web-sdk.md).

## この実装パスのメリットとデメリット

この移行アプローチを使用すると、メリットとデメリットの両方が生じます。 各オプションを慎重に検討し、組織に最適なアプローチを決定します。

| メリット | デメリット |
| --- | --- |
| <ul><li>**既存の実装を使用**：このアプローチでは、いくつかの実装変更が必要ですが、ゼロから完全に新しい実装を行う必要はありません。 実装ロジックへの最小限の変更で、既存のデータレイヤーとコードを使用できます。</li><li>**スキーマは必要ありません**:Web SDK への移行のこの段階では、XDM スキーマは必要ありません。 代わりに、にデータを入力できます `data` データをAudience Managerに直接送信するオブジェクト。 Web SDK への移行が完了したら、組織のスキーマを作成し、データストリームマッピングを使用して適用可能な XDM フィールドを入力できます。 移行プロセスのこの段階でスキーマが必要だった場合、組織はAudience Manager XDM スキーマの使用を強制されます。 このスキーマを使用すると、組織が今後独自のスキーマを使用するのが難しくなります。</li></ul> | <ul><li>**技術的債務の履行**：このアプローチは既存の実装の変更済み形式を使用するので、実装ロジックを追跡し、必要に応じて将来変更を実行するのが難しい場合があります。</li><li>**Platform にデータを送信するには、マッピングが必要です**:Real-Time CDPを使用する準備が整ったら、Adobe Experience Platformのデータセットにデータを送信する必要があります。 このアクションでは、のすべてのフィールドが `data` オブジェクトは、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリです。 マッピングは、このワークフローに対して 1 回だけ行う必要があります。実装の変更は必要ありません。 ただし、XDM オブジェクトでデータを送信する場合に必要ない追加の手順です。</li></ul> |

Adobeでは、次のシナリオでこの実装パスを使用することをお勧めします。

* 既存の実装がある場合は、Adobe Analytics AppMeasurement JavaScript ライブラリを使用します。 Audience Managerタグ拡張機能を使用した実装がある場合は、次に従います [Audience Managerタグ拡張機能から Web SDK タグ拡張機能に移行します](dil-extension-to-web-sdk.md) その代わり。
* 今後Real-Time CDPを使用する予定ですが、Audience Manager実装を Web SDK 実装に最初から置き換える必要はありません。 Web SDK で実装をゼロから置き換えることは最も努力が必要ですが、最も実行可能な長期的な実装アーキテクチャも提供します。 組織がクリーンな Web SDK 実装の作業を進んで行う場合は、 [Web SDK ドキュメント](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) を参照してください。

## Web SDK への移行に必要な手順

以下の手順には、取り組むべき具体的な目標が含まれています。 各手順をクリックすると、実行方法に関する詳細な手順が表示されます。

+++**1.データストリームの作成と設定**

Adobe Experience Platform Data Collection にデータストリームを作成します。 このデータストリームにデータを送信すると、データがAudience Managerに転送されます。 今後、この同じデータストリームがReal-Time CDPにデータを転送します。

1. に移動します。 [experience.adobe.com](https://experience.adobe.com) 認証情報を使用してログインします。
1. 右上のホームページまたは製品セレクターを使用して、に移動します **[!UICONTROL Data Collection]**.
1. 左側のナビゲーションで、を選択します。 **[!UICONTROL Datastreams]**.
1. を選択 **[!UICONTROL New Datastream]**.
1. 目的の名前を入力し、を選択します **[!UICONTROL Save]**.
1. データストリームを作成したら、次を選択します。 **[!UICONTROL Add Service]**.
1. サービスのドロップダウンメニューで、を選択します **[!UICONTROL Audience Manager]**.

   ![Audience Managerサービスを追加](assets/add-service.png) {style="border:1px solid lightslategray"}

これで、データストリームがデータを受け取り、Audience Managerに渡す準備が整いました。 データストリーム ID をメモします。この ID は、コードで Web SDK を設定する際に必要になるからです。

+++

+++**2.Web SDK JavaScript ライブラリのインストール**

参照： [JavaScript ライブラリを使用した Web SDK のインストール](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) を参照してください（詳細および使用するコードブロック）。 の最新バージョンを参照します `alloy.js` そのため、そのメソッド呼び出しを使用できます。

+++

+++**3.Web SDK の設定**

Web SDK を使用して、手順 1 で作成したデータストリームを指すように実装を設定します [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) コマンド。 この `configure` コマンドは、ライブラリのインストールコードと一緒に含めることができるように、すべてのページで設定する必要があります。

の使用 [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) および [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) web SDK 内のプロパティ `configure` コマンド：

* を `edgeConfigId` を前の手順で取得したデータストリーム ID に変更します。
* を `orgId` を組織の IMS 組織 ID に送信します。

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

オプションで、次のその他のプロパティを設定できます [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) 組織の実装要件に応じてコマンドを実行します。

+++

+++**4.JSON ペイロードを使用するようにコードロジックを更新する**

に依存しないように、Audience Managerの実装を変更します `AppMeasurement.js` または `s` オブジェクト。 代わりに、正しい形式の JavaScript オブジェクトに変数を設定し、Adobeに送信する際に JSON オブジェクトに変換します。 持つさま [データレイヤー](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) サイトで値を設定すると、同じ値を引き続き参照できるので、非常に役立ちます。

データをAudience Managerに送信するには、Web SDK ペイロードはを使用する必要があります `data.__adobe.audiencemanager` このオブジェクト内で設定されたすべての analytics 変数を使用します。 このオブジェクト内の変数は、対応するAppMeasurement変数と同じ名前と形式を共有します。 例えば、 `products` 変数です。XDM の場合と同様に、個々のオブジェクトに分割しないでください。 代わりに、 `s.products` 変数：

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

最終的に、このペイロードには、必要な値と、に対するすべての参照が含まれます `s` 実装のオブジェクトが削除されました。 JavaScript が提供する任意のリソースを使用して、このペイロードオブジェクトを設定できます（個々の値を設定するドット表記を含む）。

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**5.Web SDK を使用するメソッド呼び出しを更新します**

を呼び出すすべてのインスタンスを更新 [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) および [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method)、それらを次の値に置き換えます。 [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) コマンド。 考慮すべきシナリオは次の 3 つです。

* **ページビュートラッキング**：ページビュートラッキング呼び出しを Web SDK に置き換えます `sendEvent` コマンド：

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **自動リンクトラッキング**：です [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) 設定プロパティはデフォルトで有効になっています。 Audience Managerにデータを送信するための適切なリンクトラッキング変数が自動的に設定されます。 自動リンクトラッキングを無効にする場合は、このプロパティをに設定します。 `false` 内 [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) コマンド。

* **手動リンクトラッキング**:Web SDK には、pageview 呼び出しと非 pageview 呼び出しの間に別のコマンドはありません。 ペイロードオブジェクト内でその区別をしてください。

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6.変更の検証と公開**

AppMeasurementへの参照とフィールドへの参照をすべて削除したら、 `s` オブジェクトを作成し、変更を開発環境に公開して、新しい実装が機能することを検証します。 すべてが正しく動作することを検証したら、更新を実稼動環境に公開できます。

正しく移行された場合、 `AppMeasurement.js` はサイトで不要になり、このスクリプトへのすべての参照を削除できます。

+++

この時点で、Audience Manager実装は Web SDK に完全に移行され、将来Real-Time CDPに移行する準備が整います。
