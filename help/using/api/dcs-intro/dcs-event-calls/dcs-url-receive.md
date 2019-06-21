---
description: /event 呼び出しで DCS 応答を要求する方法については、ここを参照してください。この節では、応答の例と、応答でよく使用されるデータ要素の定義を示します。
seo-description: /event 呼び出しで DCS 応答を要求する方法については、ここを参照してください。この節では、応答の例と、応答でよく使用されるデータ要素の定義を示します。
seo-title: DCS からのデータ受信
solution: Audience Manager
title: DCS からのデータ受信
uuid: fbb77197-8530-48a8-b708-d785f7214494
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DCS からのデータ受信 {#receive-data-from-the-dcs}

[!UICONTROL DCS] 呼び出しで `/event` 応答を要求する方法については、こちらを参照してください。この節では、応答の例と、応答でよく使用されるデータ要素の定義を示します。

このコンテンツを確認する前に、[DCS へのデータ送信](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)を参照してください。

## DCS 応答パラメーター：復習 {#dcs-response-parameters}

[!UICONTROL DCS] からの応答を受信する場合は、`d_rtbd=json` 要求に [!UICONTROL DCS] を含める必要があります。このパラメーターを省略した場合、[!UICONTROL DCS] はデータを返しません。データを要求する場合の [!UICONTROL DCS] への基本的な呼び出しでは、次の構文を使用します。

<pre><code>https://domainalias.demdex.net/event<i></i>?<i>key1</i>= <i>val1</i>，&amp;<i>key2</i>= <i>val2</i>&amp; d_ dst=1&amp; d_ rdbd= json&amp; d_ cb=<i>callback</i></code>
</pre>

## レスポンスのサンプル {#sample-response}

[DCS へのデータ送信](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)ドキュメントで、架空の会社 [!DNL Acme, Inc.] がこの呼び出しをおこなったことを思い出してください。

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

この呼び出しには必要な応答パラメーターが含まれているので、[!UICONTROL DCS] は以下のような [!DNL JSON] オブジェクトを送り返します。実際の応答は、これと同様の場合もあれば、もっと複雑な場合もあります。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 応答パラメーター {#response-parameters}

[!UICONTROL DCS] からの応答でよく見かけるパラメーターを、それぞれ次の表で定義します。これは、イベント呼び出しや、データを返すその他の [!UICONTROL DCS][!DNL API] クエリに当てはまります。

| パラメーター | 説明 |
|--- |--- |
| `c` | [URL の宛先](../../../features/destinations/manage-destinations.md#configure-url-destination)として設定された URL です。 |
| `cn` | [Cookie の宛先](../../../features/destinations/manage-destinations.md#create-cookie-destination)の Cookie 名フィールドに設定された名前または ID です。 |
| `cv` | &quot;cn&quot;:&quot;destinaton name&quot; パラメーターで定義された宛先に送信された値です。 |
| `dcs_region` | [サーバー間DCSの呼び出し](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | このオブジェクトには、UI で設定されるすべての URL 宛先の情報が含まれています。このオブジェクトの値（リスト）は、ユーザーのアクションに応じて動的に変わります。 |
| `dmn` | Cookie の宛先の「Cookie Domain」フィールドに指定されたドメインです。[Cookie の宛先のオプション設定](../../../features/destinations/manage-destinations.md#optional-settings-cookies)を参照してください。サーバー間統合の場合は、`aam-api.com` などのドメインを使用することをお勧めします。 |
| `e` | URL の宛先に設定されたセキュア URL です。 |
| `stuff` | このオブジェクトには、すべての Cookie の宛先の情報が含まれています。このオブジェクトの値（リスト）は、ユーザーのアクションに応じて動的に変わります。 |
| `tid` | トランザクション ID（デバッグ目的で使用される 12 文字の一意の ID）です。DCS への各 /event 呼び出しでは、応答の改善および高速化に関するサポートへの問い合わせで参照できる tid を受け取ります。 |
| `ttl` | Cookie の有効期間（日単位）です。 |
| `u` および `uuid` | Audience Managerこれが必要になるのは、[サーバー間 DCS 呼び出し](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)をおこなう場合です。 |
| `y` | Destination type,  iFrame (`iframe`) or image (`img`). |

>[!MORE_LIKE_THIS]
>
>* [DCS でサポートされるキー値のプレフィックスと変数](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

