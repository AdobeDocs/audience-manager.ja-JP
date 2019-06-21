---
description: パートナー専用の DIL インスタンスを取得します。
keywords: Audience Manager API;AAM API
seo-description: パートナー専用の DIL インスタンスを取得します。
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# getDil{#getdil}

パートナー専用の DIL インスタンスを取得します。

**関数シグネチャ：**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## パラメーター

| 名前 | タイプ | 説明 |
|---|---|---|
| `partner` | 文字列 | 検索するパートナーの名前。 |
| `containerNSID` | 整数 | デフォルトは `0` です。検索するコンテナの NSID。オプションです。 |

## 応答

パートナーとコンテナの NSID が正しく一致すると、パートナー専用の [!UICONTROL DIL] インスタンスが返されます。一致する NSID がない場合は、「`The DIL instance with partner <name> and containerNSID <ID> was not found.`」というメッセージでエラーが（スローではなく）返されます。

## サンプルコード

<pre class="java"><code>DIL. getDIL（'<i>partner</i>'， <i>containerNSID</i>）;
DIL. getDIL（'<i>partner</i>'）;</code>
</pre>
