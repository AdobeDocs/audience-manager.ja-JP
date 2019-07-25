---
description: GET または POST メソッドを使用して DCS API にデータを送信します。
seo-description: GET または POST メソッドを使用して DCS API にデータを送信します。
seo-title: DCS API メソッド
solution: Audience Manager
title: DCS API メソッド
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS API メソッド {#dcs-api-methods}

Send data to the [!UICONTROL DCS] [!DNL API] using `GET` or `POST` methods.

[!UICONTROL DCS] メソッドか `GET` メソッドのどちらかを使用して、`POST` にデータを送信できます。[curl](https://curl.haxx.se/) / を使用した以下のサンプル呼び出しを見てみましょう。これら 3 つのサンプル呼び出しでは、シグナル `c_likes = famous popstar` および `c_loves = famous actress` をデバイスプロファイル `12345678901234567890123456789012345678` に追加しています。

>[!NOTE]
>
>コードと例の&#x200B;*斜体*&#x200B;の部分は変数のプレースホルダーです。この方法で [!UICONTROL DCS] にデータを送信する際には、プレースホルダーを実際の値に置き換えてください。

## GET でのデータ送信 {#send-data-via-get}

`GET` 呼び出しのサイズの上限は 8K であることに注意してください。

<pre><code>curl- i"<i>yourcompany.demdex.net/event</i>?
d_uuid=<i>12345678901234567890123456789012345678</i>&amp;d_rtbd=json&amp;<i>c_likes=famous%20popstar</i>&amp;<i>c_loves=famous%20actress</i>"
</code></pre>

## POST でのデータ送信 {#send-data-via-post}

`POST` メソッドを使用してデータを送信する際には、以下の要件に注意してください。

* サイズの上限は 32K です。
* コンテンツタイプを `application/x-www-form-urlencoded` に設定します。

### サンプル呼び出し

<pre><code>
curl -X POST \ 
  https:// <i>yourcompany</i>.demdex.net/event \ 
  -H 'content-type: application/x-www-form-urlencoded' \ 
  -d ' <i>c_likes=famous%20popstar</i>&amp; <i>c_loves=famous%20actress</i>&amp;<i>d_uuid=12345678901234567890123456789012345678</i>'
</code></pre>

<pre><code>
curl -X POST \ 
  https:// <i>yourcompany</i>.demdex.net/event \ 
  -H 'content-type: application/x-www-form-urlencoded' \ 
  -d ' <i>c_likes=famous%20popstar</i>&amp; <i>c_loves=famous%20actress</i>&amp;<i>d_uuid=12345678901234567890123456789012345678</i>'
</code></pre>
