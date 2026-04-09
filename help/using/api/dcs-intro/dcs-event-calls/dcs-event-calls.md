---
description: イベント呼び出しでは、URL 文字列で DCS に情報を送信します。典型的な Audience Manager デプロイメントでは、お客様はアドビの JavaScript データ収集コード（DIL）を使用して DCS にデータを送信します。ただし、お客様が自社のページにアドビの JavaScript コードを組み込むことができない場合があります。企業ポリシーやその他の技術的問題により、アドビの JavaScript コードをページに組み込むことができない場合でも、これらのイベント呼び出し API を使用することで Audience Manager から DCS にデータを送信し、DCS から Audience Manager にデータを返すことができます。
seo-description: Event calls send information to the DCS in a URL string. In a typical Audience Manager deployment, customers use our JavaScript data collection code (DIL) to send data to the DCS. However, sometimes customers cannot put our JavaScript code on their pages. If company policies or other technical issues prevent you from placing our JavaScript code on your pages, you can still work with Audience Manager to send and return data from DCS with these event call APIs.
seo-title: DCS Event Call APIs
solution: Audience Manager
title: DCS イベント呼び出し API
uuid: 84754960-9ef0-454d-8f5c-33846e2494f6
feature: DCS
exl-id: 7eb0ce70-5871-441a-920a-97a711482dde
TQID: https://experienceleague.adobe.com/HYo7px3KGsoBVDcJDXZbX0lrbLW2YunUY265BUdGous
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 227
ht-degree: 96%

---

# DCS イベント呼び出し API {#dcs-event-call-apis}

イベント呼び出しでは、[!DNL URL] 文字列で [!DNL DCS] に情報を送信します。典型的な Audience Manager デプロイメントでは、お客様はアドビの[!DNL JavaScript]データ収集コード（[!UICONTROL DIL]）を使用して [!DNL DCS] にデータを送信します。ただし、お客様が自社のページにアドビの [!DNL JavaScript] コードを組み込むことができない場合があります。企業ポリシーやその他の技術的問題により、アドビの [!DNL JavaScript] コードをページに組み込むことができない場合でも、Audience Manager を操作してこれらのイベント呼び出し [!DNL API] を使用することで、[!DNL DCS] からデータを送信したり返したりできます。

## はじめに {#dcs-getting-started}

この節では、以下の方法を説明するほか、関連する参考情報も示します。

* [!DNL DCS] への呼び出しを実行する。
* [!DNL DCS] からデータを受信する。
* 呼び出しのデータ要素を所定の形式どおりに設定する。
* [!DNL DCS] から返されるパラメーターを理解する。

開始するには、この後の各節を参照してください。[ データをDCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)に送信から開始します。 を参照し、次に、[DCS からのデータ受信](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)を参照してください。

* [DCS へのデータ送信](dcs-url-send.md)
* [DCS からのデータ受信](dcs-url-receive.md)

>[!MORELIKETHIS]
>
>* [DCS API リファレンス](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)
