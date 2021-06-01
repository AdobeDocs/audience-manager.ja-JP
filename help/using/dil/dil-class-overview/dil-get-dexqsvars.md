---
description: 広告サーバーからの特定の値を取得します。
seo-description: 広告サーバーからの特定の値を取得します。
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL の実装
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 100%

---

# dexGetQSVars{#dexgetqsvars}

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
