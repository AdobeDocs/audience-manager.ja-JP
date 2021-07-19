---
description: サーバー間（S2S）API には、DCS ユーザーデータの送受信や独自システムまたはアプリケーションでの操作を可能にするコードおよびメソッドが用意されています。
seo-description: サーバー間（S2S）API には、DCS ユーザーデータの送受信や独自システムまたはアプリケーションでの操作を可能にするコードおよびメソッドが用意されています。
seo-title: サーバー間データ転送用の DCS API
solution: Audience Manager
title: サーバー間データ転送用の DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 100%

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
* [Experience Cloud ID サービスを通じたユーザー ID と地域 ID の取得](dcs-mcid-ids.md)
* [サーバー間 DCS API 呼び出しの実行](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API リファレンス ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

