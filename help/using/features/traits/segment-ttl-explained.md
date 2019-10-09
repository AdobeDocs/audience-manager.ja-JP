---
description: 特性の有効期間（TTL）がセグメントのメンバーシップにどのような影響を与えるかを説明します。
seo-description: 特性の有効期間（TTL）がセグメントのメンバーシップにどのような影響を与えるかを説明します。
seo-title: セグメントと特性の有効期間についての説明
solution: Audience Manager
title: セグメント有効期間の説明
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
translation-type: tm+mt
source-git-commit: 17906734132813984437216f2a6cbc1c7bf14937

---


# セグメントと特性の有効期間についての説明{#segment-time-to-live-explained}

特性の [!UICONTROL time-to-live]（[!DNL TTL]）がセグメントのメンバーシップにどのような影響を与えるかを説明します。

<!-- segment-ttl-explained.xml -->

## 有効期間

[!DNL TTL] は、最後の特性資格認定イベントの後、サイト訪問者がセグメントにとどまっている期間を定義します。[!DNL TTL] は、セグメントではなく、特性に対して設定されます。Visitors fall out of a segment if they do not qualify for a trait before the end of the [!DNL TTL] interval. 新しい特性に対するデフォルトの [!DNL TTL] は 120 日です。0 日に設定すると、特性は有効期限なしになります。[TTL 値を設定](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)します（特性作成インターフェイスの「[!UICONTROL Advanced Options]」セクションで特性を作成または編集する場合）。

### 1日のTTLの説明

1日に設定す [!DNL TTL] ると、TTLタイマーは、特性実現の翌日から開始し、特性実現の日に残った時間はカウントしません。

Audience Managerは、次の [!DNL TTL] 式に基づいて1日の特性の有効期 [!DNL TTL] 限を計算します。

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **例1**:特徴1:00で1 [!DNL UTC][!DNL TTL]日で実現。 [!DNL TTL] は24時間+ 24時間 — 1 = 47時間後に期限切れになります。
* **例2**:特徴は23:00に1 [!DNL UTC]日で実現した [!DNL TTL]。 [!DNL TTL] 24 + 24 - 23 = 25時間後に期限が切れます。

## [!DNL TTL] とセグメントからのドロップアウト

A user falls out of a segment if they do not qualify for any of its traits within the [!DNL TTL] interval. For example, if you have a 1-trait segment with a 30 days [!DNL TTL], the user will drop out of that segment if they do not qualify for the trait again within the next 30 days.

![](assets/ttl-explained.png)

## [!DNL TTL] とセグメントの更新

The [!DNL TTL] resets, and the user remains in a segment, if they qualify for that segment’s trait within the [!DNL TTL] period. Also, because most segments contain multiple traits with their own [!DNL TTL] intervals, a user can remain in a segment, and reset the [!DNL TTL] interval, as long as they keep qualifying for any traits associated with the segment.

例えば、特性 A（30 日の [!DNL TTL]）と特性 B（15 日の [!DNL TTL]）で構成されるセグメント 1 があるとします。Assuming a visitor qualifies for each trait only once, the illustration below outlines the [!DNL TTL] renewal process and total in-segment duration.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL はサードパーティの TTL 設定とは独立している

[!DNL Audience Manager] ピクセルに対して設定された[!DNL TTL] は、サードパーティ（[!DNL DSP]、広告ネットワークなど）によって使用される他のピクセルに設定された [!DNL TTL] とは独立して動作することに注意してください。

>[!MORE_LIKE_THIS]
>
>* [特性の有効期間の設定](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

