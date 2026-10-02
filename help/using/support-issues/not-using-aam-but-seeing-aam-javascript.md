---
description: Audience Manager を使用していないのに、JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。なぜですか？
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: Audience Manager を使用していないのに、JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。なぜですか？
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
TQID: 'https://experienceleague.adobe.com/Zpe6ML-WJ5tu4x-gYuPJfAn4IklOxFw2bW8E7ys8YSc'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
    internal-label: Support
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 100%
---
# Audience Manager の顧客ではないのに、サイトに Audience Manager JavaScript 呼び出しが表示される

## 質問

Adobe Audience Manager を使用していないのに、JavaScript デバッガーに Audience Manager JavaScript 呼び出しが表示されています。

なぜこのようなことが起こるのでしょうか？

## 回答

プロパティで [Experience Cloud ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を実行している可能性があります。 そうであれば、この Audience Manager 参照は、必ずしも Audience Manager を実行するプロパティを参照していません。 そうではなく、Audience Manager がこのサービスに機能を提供していることを意味します。

Audience Manager サーバーコールは、通常、[顧客 ID を同期](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=ja)するためにおこなわれます。
