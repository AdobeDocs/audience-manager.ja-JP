---
description: セグメント化解除とは、デバイスプロファイルを不適格としてセグメントから削除するプロセスのことです。デバイスプロファイルをセグメントから削除できるかどうかは、プロファイル結合ルールの作成時に使用したデバイスオプションによって異なります。
seo-description: セグメント化解除とは、デバイスプロファイルを不適格としてセグメントから削除するプロセスのことです。デバイスプロファイルをセグメントから削除できるかどうかは、プロファイル結合ルールの作成時に使用したデバイスオプションによって異なります。
seo-title: プロファイル結合ルールとデバイスのセグメント化解除プロセス
solution: Audience Manager
title: プロファイル結合ルールとデバイスのセグメント化解除プロセス
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: プロファイルの結合
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 99%

---

# プロファイル結合ルールとデバイスのセグメント化解除プロセス {#profile-merge-rules-and-device-un-segmentation-processes}

セグメント化解除とは、デバイスプロファイルを不適格としてセグメントから削除するプロセスのことです。デバイスプロファイルをセグメントから削除できるかどうかは、[!UICONTROL Profile Merge Rule]の作成時に使用したデバイスオプションによって異なります。

## 使用可能なデバイスオプション {#device-options}

[!UICONTROL Device Options] は、[!UICONTROL Profile Merge Rule] を作成または編集するときに、[!UICONTROL Profile Merge Rules Setup] で利用できます。

## 「Current Device Profile」オプションとデバイスのセグメント化解除 {#current-device-profile-options}

**[!UICONTROL Device Profile]**&#x200B;は、[!UICONTROL Profile Merge Rule]のデフォルトのデバイスプロファイルオプションです。[!DNL Audience Manager] は、[!UICONTROL Profile Merge Rule] が **[!UICONTROL Device Profile]** オプションを使用する際にデバイスプロファイルをセグメントから削除できます。この条件では、次の場合にセグメント化解除が発生します。

* デバイスプロファイルが 120 日間非アクティブである場合。週ごとのデータクリーンアップ処理により、非アクティブなデバイスプロファイルがセグメントから削除されます。
* デバイスプロファイルに対する更新または変更が原因でデバイスが不承認とされるので、このデバイスがセグメントに認定されることはありません。これは、セグメント認定条件が変更された場合、[!DNL AND NOT] 演算子がセグメントルールに適用された場合、または[最新性と頻度](../segments/recency-and-frequency.md)条件で「次よりも小さいか等しい」設定が使用されている場合に発生します。ユースケースについては、[Instant Cross-Device Suppression](instant-cross-device-suppression.md) のドキュメントを参照してください。

![device-only](assets/device-only.png)

## 「No Device Profile」オプションとデバイスのセグメント化解除 {#no-device-option}

[!DNL Audience Manager] は、[!UICONTROL Profile Merge Rule] が **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** オプションを使用すると、セグメントからクロスデバイス ID を削除できます。これらの条件の下で、クロスデバイスプロファイルの更新や変更によってクロスデバイス ID がセグメントの対象として認定されなくなったときに、セグメント化解除がおこなわれます。これは、セグメント認定条件が変更された場合、[!UICONTROL AND NOT] 演算子がセグメントルールに適用された場合、または[最新性と頻度](../segments/recency-and-frequency.md)条件で「次よりも小さいか等しい」設定が使用されている場合に発生します。ユースケースについては、[Instant Cross-Device Suppression](instant-cross-device-suppression.md) のドキュメントを参照してください。

![](assets/current-no-device.png)

## デバイスグラフオプションとデバイスのセグメント化解除 {#device-graph-options-unsegmentation}

[!DNL Audience Manager] では、[!UICONTROL Profile Merge Rule]でデバイスグラフオプションが使用されている場合に、複数のデバイスプロファイルをセグメントから削除できます。デバイスグラフ内のデバイスの結合済みプロファイルが更新や変更によってセグメントの対象として認定されなくなったら、セグメント化解除がおこなわれます。これは、セグメント認定条件が変更された場合、[!UICONTROL AND NOT] 演算子がセグメントルールに適用された場合、または[最新性と頻度](../segments/recency-and-frequency.md)条件で「次よりも小さいか等しい」設定が使用されている場合に発生します。ユースケースについては、[Instant Cross-Device Suppression](instant-cross-device-suppression.md) のドキュメントを参照してください。

>[!NOTE]
>
>**セグメント評価と除外のデバイスの上限は 100 です**。
>Audience Manager は、デバイスグラフを使用するプロファイル結合ルールを持つセグメントを評価する場合、最大 100 のデバイスを結合します。Audience Managerは、[認証済みプロファイル](../../reference/visitor-authentication-states.md)（クロスデバイス ID）を使用して、現在のデバイスと、現在のデバイスにリンクされている最大 99 台のデイスを評価します。セグメント化解除シグナルが発行された場合、現在のデバイスとリアルタイムに認識された最大 100 台の追加デバイスが宛先のセグメントから削除されます。

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [プロファイル結合ルールおよびデバイスグラフに関するよくある質問](../../faq/faq-profile-merge.md)
>* [Instant Cross-Device Suppression](instant-cross-device-suppression.md)

