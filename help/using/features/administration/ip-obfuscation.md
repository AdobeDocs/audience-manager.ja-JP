---
description: グローバルプライバシー規制により、多くの国で IP アドレスの難読化が求められる場合があります。Audience Manager を使用すると、訪問者の IP アドレス全体または国ごとに難読化できます。
seo-description: グローバルプライバシー規制により、多くの国で IP アドレスの難読化が求められる場合があります。Audience Manager を使用すると、訪問者の IP アドレス全体または国ごとに難読化できます。
solution: Audience Manager
title: IP アドレスの難読化
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 100%

---


# IP アドレスの難読化 {#ip-obfuscation}

Audience Manager で収集された IP アドレスを難読化するには、この機能を使用します。

## 概要と方法 {#overview-and-methodology}

グローバルプライバシー規制により、多くの国で IP アドレスの難読化が求められる場合があります。Audience Manager を使用すると、訪問者の IP アドレス全体または国ごとに難読化できます。

### IP の難読化方法

「プライバシーバイデザイン」の原則に従い、Adobe Audience Manager では、すべての地域に対してグローバルに、または特定の国に対して、UI からの IP 難読化を有効にすることができます。この設定を有効にすると、IP アドレスが Audience Manager に取り込まれると、IP アドレスの最後のオクテット（最後の部分）は即座に破棄されます。Audience Manager は、処理（オプションの IP アドレスの地域の参照またはログ作成を含む）に先立って、IP アドレスのこの部分を破棄します。例：

* 難読化前：`255.255.255.255`
* 難読化後：`255.255.255.0`

[データプライバシーの節](/help/using/overview/data-security-and-privacy/data-privacy.md)の「IP アドレスの収集と IP アドレスの難読化」も参照してください。

## IP アドレスの難読化の要件 {#ip-obfuscation-requirements}

IP アドレスの難読化は、Audience Manager管理者アカウントでのみ使用できます。ユーザーに管理者権限を割り当てる方法については、[ユーザーの作成](/help/using/features/administration/administration-overview.md#create-users)を参照してください。

>[!NOTE]
>
> Audience Manager によって処理される大量のデータにより、IP 難読化の変更には、設定を更新時点からカウントして最大 4 時間かかることがあります。

## IP アドレスの難読化の設定 {#configure-ip-obfuscation}

IP アドレスの難読化を設定するには、次の手順に従います。

1. 管理者アカウントでAudience Managerにログインし、**Administration／Privacy** に移動します。
2. 使用する IP 難読化の種類を選択します。
   1. **Obfuscate all IP addresses（すべての IP アドレスを難読化）：**&#x200B;訪問者がどの地域から来ているかに関係なく、すべての訪問者 IP アドレスの最後のオクテットを難読化します。
   2. **Obfuscate IP addresses for specific countries（特定の国の IP アドレスを難読化）：**&#x200B;特定の国の訪問者 IP アドレスの最後のオクテットを難読化します。**国名リスト**&#x200B;または対応する「**Search**」フィールドを使用して IP を難読化する国を見つけ、「+」アイコンをクリックしてそれらの国を「**Selected for Obfuscation**」リストに追加します。「**Selected for Obfuscation**」リストに必要な国をすべて追加したら、「**Save**」をクリックします。

![](assets/ip-obfuscation.png)

## IP アドレスの難読化の無効化 {#disable-ip-obfuscation}

IP アドレスの難読化をグローバルに無効にするには、**Administration／Privacy** に移動し、「**Do not obfuscate IP addresses**」を選択して、「**Save**」をクリックします。

特定の国に対して IP アドレスの難読化を無効にするには、「**Selected for Obfuscation**」リストで国を探し、対応する **X** アイコンをクリックします。完了したら、「**Save**」をクリックします。

## 関連する概念 {#related-concepts}

* [データプライバシー](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP アドレス難読化のビデオのデモ
>[!VIDEO](https://video.tv.adobe.com/v/27218/)

