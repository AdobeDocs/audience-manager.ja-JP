---
description: ウィンドウが読み込まれた後に読み込まれたことを DIL に知らせるために使用されます。
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 34%

---


# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>2023 年 7 月以降、Adobeは [!DNL Data Integration Library (DIL)] および [!DNL DIL] 拡張機能の開発を廃止しました。
>
>既存のお客様は、[!DNL DIL] 実装を引き続き使用できます。 ただし、Adobeはこの点を超えて [!DNL DIL] 開発を行うことはありません。 お客様は、長期的なデータ収集戦略について [0}Experience Platform Web SDK} を評価することをお勧めします。](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)
>
>2023 年 7 月以降、新しいデータ収集統合機能の実装を検討しているお客様は、代わりに [0}Experience Platform Web SDK} を使用する必要があります。](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)

ウィンドウが読み込まれた後に読み込まれたことを DIL に知らせるために使用されます。

**関数シグネチャ：**`isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## サンプルコード

```
DIL.isAddedPostWindowLoad();
```
