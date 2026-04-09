---
description: サーバー間（S2S）API には、DCS ユーザーデータの送受信や独自システムまたはアプリケーションでの操作を可能にするコードおよびメソッドが用意されています。
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: サーバー間データ転送用の DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
TQID: https://experienceleague.adobe.com/lXTSMwju5lxRhrz0VpOlxbHLa2POAQHGOIzzP3j980s
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 296
ht-degree: 96%

---

# サーバー間データ転送用の DCS API{#dcs-apis-for-server-to-server-data-transfers}

サーバー間（[!UICONTROL S2S]）[!DNL API] には、[!DNL DCS] ユーザーデータの送受信や独自システムまたはアプリケーションでの操作を可能にするコードおよびメソッドが用意されています。

## 一般的なユースケース {#common-use-cases}

[!UICONTROL Server-to-server]は、ランディングページやその他のインタラクションを訪問者の関心に基づいてカスタマイズするのに役に立ちます。一般的なユースケースには次のものが含まれます。

* オンサイトパーソナライゼーション：訪問者のセグメントに基づいて関連性の高いコンテンツやコールトゥアクションを動的に追加することにより、サイトでの訪問者のエクスペリエンスを調整します。
* カスタマーサービスの向上：サーバー間データ転送を通じて [!DNL Audience Manager] セグメントを [!DNL CRM] などのシステムにインポートします。このデータは、コールサービスやオンラインチャットのオペレーターにとって、関連性の高いパーソナライズされた顧客情報になります。

## 要件：ユーザー ID と地域サーバー名 {#requirements}

[!UICONTROL DCS API] では、データ要求を検証し実行するためにユーザー ID と地域 ID が必要です。

* ユーザー ID が必要なのは、データを特定の訪問者に関連付ける必要があるからです。
* 地域 ID が必要なのは、呼び出しをサーバー名に結び付けるためと、サイト訪問者に地理的に最も近いデータセンターにユーザーデータが保存されるからです。

## はじめに {#getting-started}

現在、このガイドでは次のタスクの方法を説明しています。

* [!DNL Audience Manager] のお客様として既に受信している [!DNL DCS] ファイルからユーザー ID と地域 ID を取得する。

* [!DNL Visitor ID Service] を使用している場合に、ユーザー ID と地域 ID を取得する。
* ユーザー ID と地域 ID が用意できたら、[!DNL DCS] への呼び出しをおこなう。

今後、新しい方法が使用可能になったら、その説明も追加していきます。開始するには、以下の節を参照してください。

* [DCS 応答からのユーザー ID と地域 ID の取得](dcs-aam-ids.md)
* [Experience Cloud IDを使用してユーザーIDとリージョンを取得…](dcs-mcid-ids.md)
* [サーバー間 DCS API 呼び出しの実行](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API リファレンス](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)
