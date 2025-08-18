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
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 55%

---

# getDil{#getdil}

>[!WARNING]
>
>2023 年 7 月以降、Adobeは [!DNL Data Integration Library (DIL)] および [!DNL DIL] 拡張機能の開発を廃止しました。
>
>既存のお客様は、[!DNL DIL] 実装を引き続き使用できます。 ただし、Adobeはこの点を超えて [!DNL DIL] 開発を行うことはありません。 お客様は、長期的なデータ収集戦略について [0&rbrace;Experience Platform Web SDK&rbrace; を評価することをお勧めします。](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)
>
>2023 年 7 月以降、新しいデータ収集統合機能の実装を検討しているお客様は、代わりに [0&rbrace;Experience Platform Web SDK&rbrace; を使用する必要があります。](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)

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
