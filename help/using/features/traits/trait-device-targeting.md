---
description: Audience Manager アカウントのすべてのプロパティにわたってデバイス関連変数を使用してユーザーをターゲット設定するのに使用できるプラットフォームレベルの共通のキー値ペアについて説明します。
seo-description: Audience Manager アカウントのすべてのプロパティにわたってデバイス関連変数を使用してユーザーをターゲット設定するのに使用できるプラットフォームレベルの共通のキー値ペアについて説明します。
seo-title: プラットフォームレベルのキーによるデバイスターゲティング
solution: Audience Manager
title: プラットフォームレベルのキーによるデバイスターゲティング
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# プラットフォームレベルのキーによるデバイスターゲティング {#device-targeting-with-platform-level-keys}

Audience Manager アカウントのすべてのプロパティにわたってデバイス関連変数を使用して、ユーザーをターゲット設定するのに使用できるプラットフォームレベルの共通のキー値ペアについて説明します。

## プラットフォームレベル変数の目的 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

プラットフォームレベルの変数を使用すると、特定のサイトからデータを渡して、[!DNL Audience Manager] アカウントのすべてのプロパティにわたるターゲット設定に使用できます。これらの変数は[キー値ペア](../../reference/key-value-pairs-explained.md)で構成され、以下に示すように、キーには `d_` というプレフィックスが付加されます。

## ユーザーエージェントによって定義されたプラットフォームレベルのキー {#keys-user-agent}

[!UICONTROL Data Collection Servers] リクエストの [ユーザーエージェントヘッダー](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) からこれらのキーの値を抽出 `HTTP` します。The values represent device-level information from the [!UICONTROL Device Atlas] database. 以下の表に示すシグナルが使用可能です。これらは、ユーザーエージェントの例から抜き出したものです。 の測定に従って、[最も一般的なキーのリストをダウンロード](assets/device_keys.csv)[!UICONTROL Device Atlas]します。

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
>Even if one or more signals cannot be retrieved from the user agent header, the other signals will still be passed to the [!UICONTROL Data Collection Servers].

>[!MORE_LIKE_THIS]
>
>* [キー変数のプレフィックスに関する要件](../../features/traits/trait-variable-prefixes.md)

