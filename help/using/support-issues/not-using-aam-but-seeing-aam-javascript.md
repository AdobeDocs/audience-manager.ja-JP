---
description: オーディエンスマネージャーを使用していないが、JavaScriptデバッガーにオーディエンスマネージャーのJavaScript呼び出しが表示される — 理由
seo-description: を使用していないが、JavaScriptデバッガーにオーディエンスマネージャーのJavaScript呼び出しが表示される — 理由
seo-title: オーディエンスマネージャーを使用していないが、JavaScriptデバッガーにオーディエンスマネージャーのJavaScript呼び出しが表示される — 理由
solution: Audience Manager
title: オーディエンスマネージャーを使用していないが、JavaScriptデバッガーにオーディエンスマネージャーのJavaScript呼び出しが表示される — 理由
translation-type: tm+mt
source-git-commit: 7206b43562eded19bfb30f8aea3bcad946a3f834

---


# アドビはオーディエンスマネージャのお客様ではありませんが、サイトでオーディエンスマネージャのJavaScript呼び出しを確認してください。

## 質問

Adobe Debuggerを使用していませんが、JavaScriptオーディエンスでオーディエンスマネージャーのJavaScript呼び出しが表示されています。  なぜこんな事が起こるのでしょう？

## 回答

プロパティで訪問者IDサービスを実行している可能性があります。 このAAM参照を使用している場合、必ずしもオーディエンスマネージャーを実行しているプロパティを参照するわけではありませんが、オーディエンスマネージャーが実際にこのサービスに電力を供給していることを意味します。

AAM呼び出しは、通常、顧客IDの設定を同期するために行われます。
