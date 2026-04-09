---
description: ウィンドウが読み込まれた後に読み込まれたことを DIL に知らせるために使用されます。
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
TQID: https://experienceleague.adobe.com/gLycCnA5nwb-91miUts-VvlFK4YfVxvju7GAl-NZW8w
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: b82b475d-1e7d-46c6-9172-1f9c73004b11
subfeature_v2: id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 98
ht-degree: 34%

---

# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>2023年7月以降、Adobeは[!DNL Data Integration Library (DIL)]と[!DNL DIL]拡張機能の開発を中止しました。
>
>既存のお客様は、引き続き[!DNL DIL]実装を使用できます。 ただし、Adobeはこの時点を超えて[!DNL DIL]を開発しません。 お客様は、長期的なデータ収集戦略について[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を評価することをお勧めします。
>
>2023年7月以降に新しいデータ収集インテグレーションを導入するお客様は、代わりに[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を使用してください。

ウィンドウが読み込まれた後に読み込まれたことを DIL に知らせるために使用されます。

**関数シグネチャ：**`isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## サンプルコード

```
DIL.isAddedPostWindowLoad();
```
