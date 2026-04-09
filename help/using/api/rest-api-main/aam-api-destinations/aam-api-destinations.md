---
description: プログラムで宛先機能を操作するためのメソッド。
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: 宛先 API メソッド
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
TQID: https://experienceleague.adobe.com/8fUlWE0aqgltxB-bS0X1cjE4Dg0-VvHpRjvWQmjKe5s
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 89
ht-degree: 70%

---

# 宛先 API メソッド {#destination-api-methods}

プログラムで宛先機能を操作するためのメソッド。

<!-- c_destinations_api.xml -->

Audience Managerでは、宛先とは、データを共有する他のシステム（ad server、[!DNL DSP]、ad network、exchange、独自のファーストパーティ Cookieなど）です。

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
