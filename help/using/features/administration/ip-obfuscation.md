---
description: グローバルプライバシー規制により、多くの国で IP アドレスの難読化が求められる場合があります。Audience Manager を使用すると、訪問者の IP アドレス全体または国ごとに難読化できます。
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: IP アドレスの難読化
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: ae074cdeb8dcf6f6a224c2ede5f3bb704b28f49f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 83%

---

# IP アドレスの難読化 {#ip-obfuscation}

Audience Manager で収集された IP アドレスを難読化するには、この機能を使用します。

## 概要と手法 {#overview-and-methodology}

グローバルプライバシー規制により、多くの国で IP アドレスの難読化が求められる場合があります。Audience Manager を使用すると、訪問者の IP アドレス全体または国ごとに難読化できます。

### IP の難読化方法

「プライバシーバイデザイン」の原則に従い、Adobe Audience Manager では、すべての地域に対してグローバルに、または特定の国に対して、UI からの IP 難読化を有効にすることができます。この設定を有効にすると、IP アドレスが Audience Manager に取り込まれると、IP アドレスの最後のオクテット（最後の部分）は即座に破棄されます。Audience Manager は、処理（オプションの IP アドレスの地域の参照またはログ作成を含む）に先立って、IP アドレスのこの部分を破棄します。例：

* 難読化前：`255.255.255.255`
* 難読化後：`255.255.255.0`

[データプライバシーの節](/help/using/overview/data-security-and-privacy/data-privacy.md)の「IP アドレスの収集と IP アドレスの難読化」も参照してください。

### IP の不明化の予測 {#precedence}

[&#x200B; データストリームレベルの IP の不明化 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja#create) は、Audience Managerで設定した IP の不明化オプションよりも優先され、すべての IP アドレスに適用されます。 Audience Managerで行われたジオロケーション検索は、データストリームレベルの [!UICONTROL IP obfuscation] オプションの影響を受けます。 完全に不明化された IP に基づくAudience Managerでの位置情報ルックアップは、結果として得られた位置情報データに基づくセグメントが実現されない、未知のリージョンが原因となります。

## IP アドレスの不明化の要件 {#ip-obfuscation-requirements}

IP アドレスの難読化は、Audience Manager管理者アカウントでのみ使用できます。ユーザーに管理者権限を割り当てる方法については、[ユーザーの作成](/help/using/features/administration/administration-overview.md#create-users)を参照してください。

>[!NOTE]
>
> Audience Manager によって処理される大量のデータにより、IP 難読化の変更には、設定を更新時点からカウントして最大 4 時間かかることがあります。

## IP アドレスの不明化の設定 {#configure-ip-obfuscation}

IP アドレスの難読化を設定するには、次の手順に従います。

1. 管理者アカウントでAudience Managerにログインし、**Administration／Privacy** に移動します。
2. 使用する IP 難読化の種類を選択します。
   1. **Obfuscate all IP addresses（すべての IP アドレスを難読化）：**&#x200B;訪問者がどの地域から来ているかに関係なく、すべての訪問者 IP アドレスの最後のオクテットを難読化します。
   2. **Obfuscate IP addresses for specific countries（特定の国の IP アドレスを難読化）：**&#x200B;特定の国の訪問者 IP アドレスの最後のオクテットを難読化します。**国名リスト**&#x200B;または対応する「**Search**」フィールドを使用して IP を難読化する国を見つけ、「+」アイコンをクリックしてそれらの国を「**Selected for Obfuscation**」リストに追加します。「**Selected for Obfuscation**」リストに必要な国をすべて追加したら、「**Save**」をクリックします。

![](assets/ip-obfuscation.png)

## IP アドレスの不明化を無効にする {#disable-ip-obfuscation}

IP アドレスの難読化をグローバルに無効にするには、**Administration／Privacy** に移動し、「**Do not obfuscate IP addresses**」を選択して、「**Save**」をクリックします。

特定の国に対して IP アドレスの難読化を無効にするには、「**Selected for Obfuscation**」リストで国を探し、対応する **X** アイコンをクリックします。完了したら、「**Save**」をクリックします。

## 関連する概念 {#related-concepts}

* [データプライバシー](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP アドレス難読化のビデオのデモ
>[!VIDEO](https://video.tv.adobe.com/v/35075?captions=jpn)
