---
description: Audience Manager および Adobe Experience Platform ID サービスは demdex.net ドメインを呼び出し、そこからデータを受け取ります。アドビが見慣れないサードパーティドメインを扱っているように見えるかもしれませんが、そうではありません。この節では、demdex.net 呼び出しの構成要素について説明します。
seo-description: Audience Manager および Adobe Experience Platform ID サービスは demdex.net ドメインを呼び出し、そこからデータを受け取ります。アドビが見慣れないサードパーティドメインを扱っているように見えるかもしれませんが、そうではありません。この節では、demdex.net 呼び出しの構成要素について説明します。
seo-title: demdex ドメインの呼び出しについて
solution: Audience Manager
title: demdex ドメインの呼び出しについて
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 50%

---


# Understanding Calls to the [!DNL Demdex] Domain {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] ドメインに対し [!DNL Adobe Experience Platform Identity Service] て呼び出し、ドメインからデータを受け取り `demdex.net` ます。 This may seem like [!DNL Adobe] is working with an unusual third-party domain, but this is not the case. この節では、`demdex.net` 呼び出しの構成要素について説明します。

| 呼び出しの構成要素 | 説明 |
|---|---|
| `demdex.net` | This is a legacy domain controlled by [!DNL Adobe]. これは、 [!DNL Audience Manager] ([!DNL Demdex])の元の事前取得名を反映しています。 [!DNL Adobe] は 2011 年に [!DNL Demdex] を買収し、[!DNL Audience Manager] というブランド名に変更しました。It is difficult to change this domain because it is entwined deeply with [!DNL Audience Manager], the [!DNL Adobe Experience Cloud ID Service], and our installed user base. 従来の `demdex.net` 呼び出しに他のプレフィックスが付いている場合があります（例：`dcs.demdex.net`、`fast.demdex.net` など）。Regardless of the prefix, a call to `something.demdex.net` is always a call to [!DNL Adobe] and not to some unknown or suspicious third-party domain. |
| `dpm` | [!DNL DPM] はの省略形で [!DNL Data Provider Match]す。 It tells internal, [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the [!DNL Adobe Experience Cloud ID Service] is passing in customer data for synchronization or requesting an ID. This is the most common `demdex.net` call you&#39;ll see from [!DNL Audience Manager] or the [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] 呼び出しの基本： <ul><li>[!DNL Audience Manager]:からの [!DNL DPM] 呼び出しは、データをとに [!DNL Audience Manager] 送信し [!DNL Data Collection Servers] ま [!DNL Profile Cache Servers]す。 [データ収集コンポーネント](../reference/system-components/components-data-collection.md)を参照してください。</li><li>[!DNL Adobe Experience Cloud ID Service]:からの [!DNL DPM] 呼び出し [!DNL Adobe Experience Cloud ID Service] は、訪問者IDのリクエストです。 「 [CookiesとAdobe Experience PlatformIDサービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/intro/cookies.html) 」および「Adobe Experience PlatformIDサービスがIDを要求して設定する [方法](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html.</li></ul><br>注意： [!DNL Adobe Experience Cloud ID Service] ドメイン名のプレフィックスは変更でき [!DNL DPM] ます。 詳しくは、[audienceManagerServer と audienceManagerServerSecure](https://docs.adobe.com/content/help/ja-JP/id-service/using/id-service-api/configurations/subdomain-config.html) を参照してください。 |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)
>* [Audience Manager の Cookie](https://docs.adobe.com/content/help/ja-JP/core-services/interface/ec-cookies/cookies-am.html)

