---
description: 世界液なプライバシー規制のトレンドを受け、多くの国で IP アドレスの難読化が求められるようになってきました。Audience Manager を使用すると、訪問者の IP アドレス全体または国ごとに難読化できます。
seo-description: 世界液なプライバシー規制のトレンドを受け、多くの国で IP アドレスの難読化が求められるようになってきました。Audience Manager を使用すると、訪問者の IP アドレス全体または国ごとに難読化できます。
solution: Audience Manager
title: IPアドレスの難読化
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# IPアドレスの難読化 {#ip-obfuscation}

Audience Managerで収集されたIPアドレスを不明化するには、この機能を使用します。

## Overview and Methodology {#overview-and-methodology}

世界液なプライバシー規制のトレンドを受け、多くの国で IP アドレスの難読化が求められるようになってきました。Audience Manager を使用すると、訪問者の IP アドレス全体または国ごとに難読化できます。

### IPの不明化方法

Adobe Audience Managerでは、「プライバシーによるプライバシー」の原則に従って、すべての地理的地域または特定の国に対してグローバルにUIからのIPの不明化を有効にできます。この設定を有効にすると、IPアドレスの最後のオクテット（最後の部分）がAudience Managerに取り込まれたときに即座に破棄されます。Audience Managerは、処理前（オプションの地理的ルックアップまたはIPアドレスのログを含む）の前に、この部分のIPアドレスを破棄します。次に例を示します。

* Before obfuscation: `255.255.255.255`
* After obfuscation: `255.255.255.0`

[データプライバシーセクションのIPアドレスおよびIPアドレスの不明化の収集も参照](/help/using/overview/data-security-and-privacy/data-privacy.md)してください。

## IP Address Obfuscation Requirements {#ip-obfuscation-requirements}

IPアドレスの不明化は、Audience Manager管理者アカウントでのみ使用できます。See [Create Users](/help/using/features/administration/administration-overview.md#create-users) to understand how to assign administrator privileges for a user.

>[!NOTE]
>
> Audience Managerによって処理される大量のデータにより、設定を更新する時点から、IPの不明化の変更が最大4時間かかることがあります。

## Configure IP Address Obfuscation {#configure-ip-obfuscation}

IPアドレスの不明化を設定するには、次の手順に従います。

1. Log in to Audience Manager with an administrator account and go to **Administration &gt; Privacy**.
2. 使用するIPの不明化のタイプを選択します。
   1. **すべてのIPアドレスを不明化:** 訪問者が元の地域に関係なく、すべての訪問者IPアドレスの最後のオクテットを不明化するには、このオプションを選択します。
   2. **特定の国のIPアドレスの不明化:** このオプションを選択すると、特定の国の訪問者IPアドレスの最終オクテットをAudience Managerが不明化します。Use the **List of Countries** or the corresponding **Search** field to find the countries to enable IP obfuscation for, and click the + icon to add them to the **Selected for Obfuscation** list. Once you&#39;ve added all the required countries to the **Selected for Obfuscation** list, click **Save**.

![](assets/ip-obfuscation.png)

## Disable IP Address Obfuscation {#disable-ip-obfuscation}

To disable IP address obfuscation globally, go to **Administration &gt; Privacy**, select **Do not obfuscate IP addresses**, and click **Save**.

To disable IP address obfuscation for specific countries, find the countries in the **Selected for Obfuscation** list, then click their corresponding **X** icon. Click **Save** when you&#39;re done.

## 関連する概念 {#related-concepts}

* [データのプライバシー](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IPアドレス不明化ビデオのデモ
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=jpn)

