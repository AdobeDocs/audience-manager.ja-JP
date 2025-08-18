---
description: 広告サーバーからの特定の値を取得します。
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 50%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>2023 年 7 月以降、Adobeは [!DNL Data Integration Library (DIL)] および [!DNL DIL] 拡張機能の開発を廃止しました。
>
>既存のお客様は、[!DNL DIL] 実装を引き続き使用できます。 ただし、Adobeはこの点を超えて [!DNL DIL] 開発を行うことはありません。 お客様は、長期的なデータ収集戦略について [0}Experience Platform Web SDK} を評価することをお勧めします。](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)
>
>2023 年 7 月以降、新しいデータ収集統合機能の実装を検討しているお客様は、代わりに [0}Experience Platform Web SDK} を使用する必要があります。](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)

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
