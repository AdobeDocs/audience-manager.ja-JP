---
description: API に関するよくある質問と問題点の説明です。
seo-description: API に関するよくある質問と問題点の説明です。
seo-title: API に関するよくある質問
solution: Audience Manager
title: API に関するよくある質問
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 100%

---


# API に関するよくある質問 {#api-faq}

API に関するよくある質問と問題点の説明です。

<!-- 

faq_api.xml

 -->

特定のメソッドとコードサンプルの詳細は、[REST API](../api/rest-api-main/rest-api-main.md) のドキュメントに記載されています。

<br> 

**[!UICONTROL DIL]が[!UICONTROL GET]および[!UICONTROL POST]メソッドでイベント呼び出しをおこなうのはなぜですか？**

[!UICONTROL DIL] では、イベント呼び出しのクエリ文字列の長さに基づいて、`GET` または `POST` メソッドでデータを [!DNL Audience Manager] に渡します。この動作は `GET` および `POST` メソッドにデフォルトで組み込まれています。[!DNL Audience Manager] に固有のものではありません。

* URL に含まれている文字の数が 2048 以下の場合、[!UICONTROL DIL] は `GET` でイベント呼び出しをおこないます。`GET` イベント呼び出しでは、データがクエリ文字列パラメーターとして URL に含まれます。このパラメーターはキー値ペアとして渡されます。

* URL に含まれている文字の数が 2048 を超える場合、[!UICONTROL DIL] は `POST` でイベント呼び出しをおこないます。`POST` イベント呼び出しでは、データが要求の本文に含まれます。[!UICONTROL DIL] では、データをキー値ペアに格納して、URL クエリ文字列ではなくフォームデータとして情報を渡します。

メソッドごとにデータの渡し方は異なりますが、機能には影響はありません。例えば、どちらのメソッドでも [!DNL Audience Manager] がデータを宛先に送信し、ID 同期が正常に機能し、データシグナルから特性を作成できます。

<br> 

**[!UICONTROL REST API]を使用すると何ができますか？**

[!UICONTROL REST API] を使用すると、ユーザーインターフェイスで使用可能な [!DNL Audience Manager] のほとんどの機能と関数をプログラムで操作できます。

<br> 

**[!UICONTROL REST API]クライアント ID およびシークレット**&#x200B;を取得するには、どうすればよいですか？

パートナーソリューションの担当者に連絡して、[!DNL API] のアクセス資格情報を取得してください。アドビの API では、トークンの認証、権限付与、更新に [OAuth 2.0](https://oauth.net/2/) 標準を使用しています。詳しくは、[OAuth 認証](../api/rest-api-main/aam-api-getting-started.md#oauth)を参照してください。
