---
description: Audience Manager を使用していないのに、JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。なぜですか？
seo-description: 使用していないのに JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。なぜですか？
seo-title: Audience Manager を使用していないのに、JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。なぜですか？
solution: Audience Manager
title: Audience Manager を使用していないのに、JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。なぜですか？
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 100%

---


# Audience Manager の顧客ではないのに、サイトに Audience Manager JavaScript 呼び出しが表示される

## 質問

Adobe Audience Manager を使用していないのに、JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。

なぜこのようなことが起こるのでしょうか？

## 回答

プロパティで [Experience Cloud ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を実行している可能性があります。そうであれば、この Audience Manager 参照は、必ずしも Audience Manager を実行するプロパティを参照していません。そうではなく、Audience Manager がこのサービスに機能を提供していることを意味します。

Audience Manager サーバーコールは、通常、[顧客 ID を同期](https://docs.adobe.com/content/help/ja-JP/id-service/using/id-service-api/methods/setcustomerids.html)するためにおこなわれます。
