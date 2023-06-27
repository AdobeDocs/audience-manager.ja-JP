---
description: 広告サーバーからの特定の値を取得します。
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 56%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>2023 年 7 月より、Adobeは、 [!DNL Data Integration Library (DIL)] そして [!DNL DIL] 拡張子。
><br><br>
>既存のお客様は、引き続き [!DNL DIL] 実装。 しかし、Adobeは発展しない [!DNL DIL] この点を越えて お客様は、 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) 長期のデータ収集戦略に対応するために使用されます。
><br><br>
>2023 年 7 月以降に新しいデータ収集統合を実装する場合は、 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) 代わりに、

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
