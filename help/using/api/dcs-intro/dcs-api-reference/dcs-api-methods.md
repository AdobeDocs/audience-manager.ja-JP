---
description: GET または POST メソッドを使用して DCS API にデータを送信します。
seo-description: GET または POST メソッドを使用して DCS API にデータを送信します。
seo-title: DCS API メソッド
solution: Audience Manager
title: DCS API メソッド
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 98%

---


# DCS API メソッド {#dcs-api-methods}

`GET` または `POST` メソッドを使用して [!DNL DCS] [!DNL API] にデータを送信します。

`GET` メソッドまたは `POST` メソッドのどちらかを使用して、[!DNL DCS] にデータを送信できます。[curl](https://curl.haxx.se/) / を使用した以下のサンプル呼び出しを見てみましょう。これら 3 つのサンプル呼び出しでは、シグナル `c_likes = famous popstar` および `c_loves = famous actress` をデバイスプロファイル `12345678901234567890123456789012345678` に追加しています。


## GET でのデータ送信 {#send-data-via-get}

`GET` 呼び出しのサイズの上限は 8K であることに注意してください。

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## POST でのデータ送信 {#send-data-via-post}

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
