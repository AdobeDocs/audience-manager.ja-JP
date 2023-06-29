---
description: パートナー専用の DIL インスタンスを取得します。
keywords: Audience Manager API;AAM API
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 60%

---

# getDil{#getdil}

>[!WARNING]
>
>2023 年 7 月より、Adobeは、 [!DNL Data Integration Library (DIL)] そして [!DNL DIL] 拡張子。
><br>
>既存のお客様は、引き続き [!DNL DIL] 実装。 しかし、Adobeは発展しない [!DNL DIL] この点を越えて お客様は、 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) 長期のデータ収集戦略に対応するために使用されます。
><br>
>2023 年 7 月以降に新しいデータ収集統合を実装する場合は、 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) 代わりに、

パートナー専用の DIL インスタンスを取得します。

**関数シグネチャ：**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## パラメーター

| 名前 | のタイプ | 説明 |
|---|---|---|
| `partner` | 文字列 | 検索するパートナーの名前。 |
| `containerNSID` | 整数 | デフォルトは `0` です。検索するコンテナの NSID。オプションです。 |

## 応答

パートナーとコンテナの NSID が正しく一致すると、パートナー専用の [!UICONTROL DIL] インスタンスが返されます。一致する API がない場合は、「`The DIL instance with partner <name> and containerNSID <ID> was not found.`」というメッセージでエラーが（スローではなく）返されます。

## サンプルコード

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
