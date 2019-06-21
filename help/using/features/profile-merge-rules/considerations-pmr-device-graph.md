---
description: リアルタイムのセグメント母集団がほとんどあるいはまったくないセグメントには、デバイスグラフを伴うプロファイル結合ルールを使用しないでください。
seo-description: リアルタイムのセグメント母集団がほとんどあるいはまったくないセグメントには、デバイスグラフを伴うプロファイル結合ルールを使用しないでください。
seo-title: デバイスグラフを伴うプロファイル結合ルールの重要な考慮事項
title: デバイスグラフを伴うプロファイル結合ルールの重要な考慮事項
uuid: 93cd8861-210d-4c52-9cb7-6f2dd7dc018a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# デバイスグラフを伴うプロファイル結合ルールの重要な考慮事項 {#important-considerations-for-profile-merge-rules-with-device-graphs}

Avoid using [!UICONTROL Profile Merge Rules] with a [!UICONTROL Device Graph] for segments which have little to no real-time segment population.

>[!IMPORTANT]
>
>If the [!UICONTROL Profile Merge Rule] is configured incorrectly, the segment population exported to batch destinations may be significantly lower than expected.

[デバイスグラフを伴うプロファイル結合ルール](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options)を使用するセグメントは、セグメント作成後に [Audience Manager のエッジサーバー](../../reference/system-components/components-edge.md)でリアルタイムに認識されたデバイスに対してのみ評価されます。

Remember, a [!UICONTROL Profile Merge Rule] with a [!UICONTROL Device Graph] has one of the following device options selected, as shown below.

![](assets/pmr-considerations-1.png)

セグメントの対象としてリアルタイムに認定されるデバイスは、[セグメントのリアルタイム母集団](../../features/segments/segment-builder-data.md#segment-populations)によって測定されます。

![](assets/pmr-considerations-2.png)

リアルタイムのセグメント母集団が小さい場合は、セグメントの対象として認定されるデバイスのうち、リアルタイムに認識されているデバイスがきわめて少ないことになります。For best performance, segments with little to no real-time population should use a [!UICONTROL Profile Merge Rule] set to evaluate the *[!UICONTROL Current Device]*, like in the image below.

![](assets/pmr-considerations-3.png)

Setting the [!UICONTROL Profile Merge Rule] to evaluate the *[!UICONTROL Current Device]* ensures that all devices (not just those seen in real-time) are evaluated for the segment. セグメントの対象として認定されたすべてのデバイスは、以下に示すように、合計セグメント母集団で定義されます。

![](assets/pmr-considerations-4.png)