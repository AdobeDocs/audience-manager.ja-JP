---
description: Audience Manager および Adobe Experience Platform ID サービスは demdex.net ドメインを呼び出し、そこからデータを受け取ります。アドビが見慣れないサードパーティドメインを扱っているように見えるかもしれませんが、そうではありません。この節では、demdex.net 呼び出しの構成要素について説明します。
seo-description: Audience Manager および Adobe Experience Platform ID サービスは demdex.net ドメインを呼び出し、そこからデータを受け取ります。アドビが見慣れないサードパーティドメインを扱っているように見えるかもしれませんが、そうではありません。この節では、demdex.net 呼び出しの構成要素について説明します。
seo-title: demdex ドメインの呼び出しについて
solution: Audience Manager
title: demdex ドメインの呼び出しについて
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: リファレンス
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: ht
source-wordcount: '361'
ht-degree: 100%

---

# [!DNL Demdex] ドメインの呼び出しについて  {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] および [!DNL Adobe Experience Platform Identity Service] は `demdex.net` ドメインに対し呼び出しをおこない、データを受け取ります。[!DNL Adobe] が見慣れないサードパーティドメインを扱っているように見えるかもしれませんが、そうではありません。この節では、`demdex.net` 呼び出しの構成要素について説明します。

| 呼び出しの構成要素 | 説明 |
|---|---|
| `demdex.net` | [!DNL Adobe] が管理しているレガシーのドメインです。[!DNL Audience Manager] の買収前の名前（[!DNL Demdex]）を反映しています。[!DNL Adobe] は 2011 年に [!DNL Demdex] を買収し、[!DNL Audience Manager] というブランド名に変更しました。このドメインは、[!DNL Audience Manager]、[!DNL Adobe Experience Cloud ID Service]、およびアドビの既存のユーザーベースに密接に関連しているので、変更することは困難です。従来の `demdex.net` 呼び出しに他のプレフィックスが付いている場合があります（例：`dcs.demdex.net`、`fast.demdex.net` など）。プレフィックスにかかわらず、`something.demdex.net` への呼び出しは常に [!DNL Adobe] への呼び出しであり、不明な、または疑わしいサードパーティドメインへの呼び出しではありません。 |
| `dpm` | [!DNL DPM] は、[!DNL Data Provider Match] の略語です。これにより、[!DNL Audience Manager] または [!DNL Adobe Experience Cloud ID Service] からの呼び出しで同期または ID リクエストのために顧客データが渡されていることが、[!DNL Adobe] の社内システムにわかります。これは、[!DNL Audience Manager] または [!DNL Adobe Experience Cloud ID Service] からの `demdex.net` 呼び出しとして最も一般的なものです。<br><br>[!DNL DPM] 呼び出し基本事項： <ul><li>[!DNL Audience Manager]：[!DNL Audience Manager] からの [!DNL DPM] 呼び出しは、[!DNL Data Collection Servers] と [!DNL Profile Cache Servers] にデータを送信します。[データ収集コンポーネント](../reference/system-components/components-data-collection.md)を参照してください。</li><li>[!DNL Adobe Experience Cloud ID Service]：[!DNL Adobe Experience Cloud ID Service] からの [!DNL DPM] 呼び出しは、訪問者 ID のリクエストです。[Cookie と Adobe Experience Platform ID サービス](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=ja)、および [Adobe Experience Platform ID サービスが ID をリクエストまたは設定する方法](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html?lang=ja)を参照してください。</li></ul><br>注意：[!DNL Adobe Experience Cloud ID Service] のお客様はドメイン名の [!DNL DPM] プレフィックスを変更できます。詳しくは、[audienceManagerServer と audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html?lang=ja) を参照してください。 |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)
>* [Audience Manager の Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html?lang=ja)

