---
description: パートナー専用の DIL インスタンスを取得します。
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: パートナー専用の DIL インスタンスを取得します。
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
translation-type: ht
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: ht
source-wordcount: '73'
ht-degree: 100%

---


# getDil {#getdil}

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
