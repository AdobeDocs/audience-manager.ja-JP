---
description: GET または POST メソッドを使用して DCS API にデータを送信します。
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS API メソッド
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
TQID: 'https://experienceleague.adobe.com/dERIW4EM4-oMg8p33N2dtDy5BBw3jF1BCQJstW2cZTY'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
    internal-label: Data Collection Server
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 93%
---
# [!DNL DCS] [!DNL API] メソッド {#dcs-api-methods}

`GET` または `POST` メソッドを使用して [!DNL DCS] [!DNL API] にデータを送信します。

`GET` メソッドまたは `POST` メソッドのどちらかを使用して、[!DNL DCS] にデータを送信できます。 [curl](https://curl.haxx.se/) / を使用した以下のサンプル呼び出しを見てみましょう。 これら 3 つのサンプル呼び出しでは、シグナル `c_likes = famous popstar` および `c_loves = famous actress` をデバイスプロファイル `12345678901234567890123456789012345678` に追加しています。

## [!DNL GET]経由でデータを送信 {#send-data-via-get}

`GET` 呼び出しのサイズの上限は 8K であることに注意してください。

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## [!DNL POST]経由でデータを送信 {#send-data-via-post}

`POST` メソッドを使用してデータを送信する際には、以下の要件に注意してください。

* サイズの上限は 32K です。
* コンテンツタイプを `application/x-www-form-urlencoded` に設定します。

### サンプル呼び出し

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
