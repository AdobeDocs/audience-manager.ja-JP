---
description: Audience Manager を使用していないのに、JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。なぜですか？
seo-description: 使用していないのに JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。なぜですか？
seo-title: Audience Manager を使用していないのに、JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。なぜですか？
solution: Audience Manager
title: Audience Manager を使用していないのに、JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。なぜですか？
feature: サポート
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
translation-type: ht
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: ht
source-wordcount: '189'
ht-degree: 100%

---

# Audience Manager の顧客ではないのに、サイトに Audience Manager JavaScript 呼び出しが表示される

## 質問

Adobe Audience Manager を使用していないのに、JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。

なぜこのようなことが起こるのでしょうか？

## 回答

プロパティで [Experience Cloud ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を実行している可能性があります。そうであれば、この Audience Manager 参照は、必ずしも Audience Manager を実行するプロパティを参照していません。そうではなく、Audience Manager がこのサービスに機能を提供していることを意味します。

Audience Manager サーバーコールは、通常、[顧客 ID を同期](https://docs.adobe.com/content/help/ja-JP/id-service/using/id-service-api/methods/setcustomerids.html)するためにおこなわれます。
