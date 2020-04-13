---
description: オーディエンスマネージャーを使用していないが、JavaScriptデバッガーにオーディエンスマネージャーのJavaScript呼び出しが表示される — 理由
seo-description: を使用していないが、JavaScriptデバッガーにオーディエンスマネージャーのJavaScript呼び出しが表示される — 理由
seo-title: オーディエンスマネージャーを使用していないが、JavaScriptデバッガーにオーディエンスマネージャーのJavaScript呼び出しが表示される — 理由
solution: Audience Manager
title: オーディエンスマネージャーを使用していないが、JavaScriptデバッガーにオーディエンスマネージャーのJavaScript呼び出しが表示される — 理由
translation-type: tm+mt
source-git-commit: 1f5c1a91f0b5df5291d3143d297e25128b5bb716

---


# アドビはオーディエンスマネージャのお客様ではありませんが、サイトでオーディエンスマネージャのJavaScript呼び出しを確認してください。

## 質問

Adobe Debuggerを使用していませんが、JavaScriptオーディエンスでオーディエンスマネージャーのJavaScript呼び出しが表示されています。

なぜこんな事が起こるの？

## 回答

プロパティで [Experience Cloud Identity Serviceを実行している可能性があります](https://docs.adobe.com/content/help/en/id-service/using/home.html) 。 この場合、このオーディエンスマネージャの参照は、Managerを実行するプロパティを参照する必要はありません。オーディエンスマネージャの参照 代わりに、オーディエンスマネージャーがこのサービスに電力を供給します。

通常、オーディエンスIDを同期するために、Configuration Managerサ [ーバー呼び出しが行われます](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)。
