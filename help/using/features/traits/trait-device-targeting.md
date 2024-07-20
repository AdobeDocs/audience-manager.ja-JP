---
description: Audience Manager アカウントのすべてのプロパティにわたってデバイス関連変数を使用して、ユーザーをターゲティングするのに使用できるプラットフォームレベルの共通のキー値ペアについて説明します。
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: プラットフォームレベルのキーによるデバイスターゲティング
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 100%

---

# プラットフォームレベルのキーによるデバイスターゲティング {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google は、`User-Agent` ヘッダーを介して収集される情報を最小限に抑えるために、[!DNL Google Chrome] およびすべての [!DNL Chromium] ベースのブラウザーの機能を更新しました。
>2023年3月以降、Audience Manager は [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) を活用してこれらの更新をサポートします。`User-Agent` ヘッダーを介して提供される特性情報を引き続き使用するには、[Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) を使用し、[高エントロピーのユーザーエージェントクライアントヒント](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=ja)を有効にする必要があります。
>これらの更新は [DIL](../../../using/dil/dil-overview.md) でサポートされていないので、[!DNL DIL] を使用する Audience Manager のお客様は、`User-Agent` ヘッダーを介して特性情報を収集できません。

Audience Manager アカウントのすべてのプロパティをまたぐデバイス関連変数を使用して、ユーザーをターゲティングするのに使用できる、プラットフォームレベルの共通のキー値ペアについて説明します。

## プラットフォームレベル変数の目的 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

プラットフォームレベルの変数を使用すると、特定のサイトからデータを渡して、[!DNL Audience Manager] アカウントのすべてのプロパティにわたるターゲティングに使用できます。これらの変数は[キー値ペア](../../reference/key-value-pairs-explained.md)で構成され、以下に示すように、キーには `d_` というプレフィックスが付加されます。

## ユーザーエージェントによって定義されたプラットフォームレベルのキー {#keys-user-agent}

[!UICONTROL Data Collection Servers] は、これらのキーの値を `HTTP` リクエストの[ユーザーエージェントヘッダー](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)から抽出します。値は、[!UICONTROL Device Atlas] データベースからのデバイスレベルの情報を表します。以下の表に示すシグナルが使用可能です。これらは、ユーザーエージェントの例から抜き出したものです。[!UICONTROL Device Atlas] の測定に従って、[最も一般的なキーのリストをダウンロード](assets/device_keys.csv)します。

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>1 つ以上のシグナルがユーザーエージェントヘッダーから取得できなくても、他のシグナルが[!UICONTROL Data Collection Servers]に渡されます。

>[!MORELIKETHIS]
>
>* [キー変数のプレフィックスに関する要件](../../features/traits/trait-variable-prefixes.md)
