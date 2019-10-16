---
description: セグメント化解除とは、デバイスプロファイルを不適格としてセグメントから削除するプロセスのことです。デバイスプロファイルをセグメントから削除できるかどうかは、プロファイル結合ルールの作成時に使用したデバイスオプションによって異なります。
seo-description: セグメント化解除とは、デバイスプロファイルを不適格としてセグメントから削除するプロセスのことです。デバイスプロファイルをセグメントから削除できるかどうかは、プロファイル結合ルールの作成時に使用したデバイスオプションによって異なります。
seo-title: プロファイル結合ルールとデバイスのセグメント化解除プロセス
solution: Audience Manager
title: プロファイル結合ルールとデバイスのセグメント化解除プロセス
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# プロファイル結合ルールとデバイスのセグメント化解除プロセス {#profile-merge-rules-and-device-un-segmentation-processes}

セグメント化解除とは、デバイスプロファイルを不適格としてセグメントから削除するプロセスのことです。デバイスプロファイルをセグメントから削除できるかどうかは、[!UICONTROL Profile Merge Rule]の作成時に使用したデバイスオプションによって異なります。

## 使用可能なデバイスオプション {#device-options}

[!UICONTROL Device Options] は、[!UICONTROL Profile Merge Rule] を作成または編集するときに、[!UICONTROL Profile Merge Rules Setup] で利用できます。

## 「Current Device Profile」オプションとデバイスのセグメント化解除{#current-device-profile-options}

**[!UICONTROL Device Profile]**&#x200B;は、[!UICONTROL Profile Merge Rule]のデフォルトのデバイスプロファイルオプションです。[!DNL Audience Manager] は、[!UICONTROL Profile Merge Rule] が **[!UICONTROL Device Profile]** オプションを使用する際にデバイスプロファイルをセグメントから削除できます。この条件では、次の場合にセグメント化解除が発生します。

* デバイスプロファイルが 120 日間非アクティブである場合。週ごとのデータクリーンアップ処理により、非アクティブなデバイスプロファイルがセグメントから削除されます。
* デバイスプロファイルに対する更新または変更が原因でデバイスが不承認とされるので、このデバイスがセグメントに認定されることはありません。これは、セグメント認定条件が変更された場合、[!DNL AND NOT] 演算子がセグメントルールに適用された場合、または[最新性と頻度](../segments/recency-and-frequency.md)条件で「次よりも小さいか等しい」設定が使用されている場合に発生します。ユースケースについては、[Instant Cross-Device Suppression](instant-cross-device-suppression.md) のドキュメントを参照してください。

![デバイスのみ](assets/device-only.png)

## 「No Device Profile」オプションとデバイスのセグメント化解除{#no-device-option}

[!DNL Audience Manager] は、[!UICONTROL Profile Merge Rule] が **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** オプションを使用すると、セグメントからクロスデバイス ID を削除できます。これらの条件の下で、クロスデバイスプロファイルの更新や変更によってクロスデバイス ID がセグメントの対象として認定されなくなったときに、セグメント化解除がおこなわれます。これは、セグメント認定条件が変更された場合、[!UICONTROL AND NOT] 演算子がセグメントルールに適用された場合、または[最新性と頻度](../segments/recency-and-frequency.md)条件で「次よりも小さいか等しい」設定が使用されている場合に発生します。ユースケースについては、[Instant Cross-Device Suppression](instant-cross-device-suppression.md) のドキュメントを参照してください。

![](../assets/current-no-device.png)

## デバイスグラフオプションとデバイスのセグメント化解除 {#device-graph-options-unsegmentation}

[!DNL Audience Manager] では、[!UICONTROL Profile Merge Rule]でデバイスグラフオプションが使用されている場合に、複数のデバイスプロファイルをセグメントから削除できます。デバイスグラフ内のデバイスの結合済みプロファイルが更新や変更によってセグメントの対象として認定されなくなったら、セグメント化解除がおこなわれます。これは、セグメント認定条件が変更された場合、[!UICONTROL AND NOT] 演算子がセグメントルールに適用された場合、または[最新性と頻度](../segments/recency-and-frequency.md)条件で「次よりも小さいか等しい」設定が使用されている場合に発生します。ユースケースについては、[Instant Cross-Device Suppression](instant-cross-device-suppression.md) のドキュメントを参照してください。

>[!NOTE]
>
>**セグメント評価と除外のデバイスの制限は100です**。
>Audience Managerは、デバイスグラフを使用するプロファイル結合ルールを使用して、セグメントを評価する際に最大100台のデバイスを結合します。 Audience Managerは、認証済みのプロファイル [（デバイス間ID）によって現在のデバイスと現在のデバイスにリンクされている最大99個のデバ](../../reference/visitor-authentication-states.md) イスを評価します。 セグメント解除信号が発行されると、現在のデバイスと追加のデバイスが宛先のセグメントから削除されます。

![](assets/last-device-graph.png)

>[!MORE_LIKE_THIS]
>
>* [プロファイル結合ルールおよびデバイスグラフに関するよくある質問](../../faq/faq-profile-merge.md)
>* [Instant Cross-Device Suppression](instant-cross-device-suppression.md)

