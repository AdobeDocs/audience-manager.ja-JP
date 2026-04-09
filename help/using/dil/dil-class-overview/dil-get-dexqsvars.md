---
description: 広告サーバーからの特定の値を取得します。
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
TQID: https://experienceleague.adobe.com/O8xeJARK4qVGj8SOXmO8OHLqfOcSPZZWvWoGad0Wji8
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: b82b475d-1e7d-46c6-9172-1f9c73004b11
subfeature_v2: id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 50%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>2023年7月以降、Adobeは[!DNL Data Integration Library (DIL)]と[!DNL DIL]拡張機能の開発を中止しました。
>
>既存のお客様は、引き続き[!DNL DIL]実装を使用できます。 ただし、Adobeはこの時点を超えて[!DNL DIL]を開発しません。 お客様は、長期的なデータ収集戦略について[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を評価することをお勧めします。
>
>2023年7月以降に新しいデータ収集インテグレーションを導入するお客様は、代わりに[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を使用してください。

広告サーバーからの特定の値を取得します。

**関数シグネチャ：**`dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**パラメーター**

| 名前 | のタイプ | 説明 |
|---|---|---|
| `variableName` | 文字列 | 値を取得する変数の名前。 |
| `partner` | 文字列 | 検索するパートナーの名前。 |
| `containerNSID` | 整数 | 検索するコンテナの [!DNL NSID]。デフォルトは `0` です。 |

**応答**

[!UICONTROL DIL] インスタンスの変数の値が返されます。

**サンプルコード**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
