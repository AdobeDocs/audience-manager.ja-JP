---
description: プログラムで宛先機能を操作するためのメソッド。
seo-description: プログラムで宛先機能を操作するためのメソッド。
seo-title: 宛先 API メソッド
solution: Audience Manager
title: 宛先 API メソッド
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 100%

---

# 宛先 API メソッド {#destination-api-methods}

プログラムで宛先機能を操作するためのメソッド。

<!-- c_destinations_api.xml -->

Audience Manager において、宛先とは、データの共有相手となる他のシステム（広告サーバー、[!DNL DSP]、広告ネットワーク、エクスチェンジ、独自のファーストパーティ Cookie など）になります。

## 宛先タイプ：URL および Cookie {#destination-types}

`destinationType` パラメーターで使用される変数の一覧を示します。[!UICONTROL URL] または [!UICONTROL cookie destination] を操作する場合は、`push` または `ADS` を指定します。使用可能な宛先 [!DNL API] メソッドで[!UICONTROL server-to-server destinations]の宛先を作成することはできません。

<!-- r_destination_types.xml -->

| API 宛先タイプ | UI 宛先タイプ |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [宛先のタイプを選択する方法](../../../features/destinations/destinations.md)

