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
source-wordcount: '110'
ht-degree: 43%

---


# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>2023 年 7 月より、Adobeは、 [!DNL Data Integration Library (DIL)] そして [!DNL DIL] 拡張子。
>
>既存のお客様は、引き続き [!DNL DIL] 実装。 しかし、Adobeは発展しない [!DNL DIL] この点を越えて お客様は、 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) 長期のデータ収集戦略に対応するために使用されます。
>
>2023 年 7 月以降に新しいデータ収集統合を実装する場合は、 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) 代わりに、

ウィンドウが読み込まれた後に読み込まれたことを DIL に知らせるために使用されます。

**関数シグネチャ：**`isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## サンプルコード

```
DIL.isAddedPostWindowLoad();
```
