---
description: 以下の手順には、AdWords リマーケティングリスト、ピクセルコード、Audience Manager の URL 宛先が必要です。検索広告向けリマーケティングリスト（RLSA）統合とも呼ばれます。有料検索にのみ適用されます。
seo-description: 以下の手順には、AdWords リマーケティングリスト、ピクセルコード、Audience Manager の URL 宛先が必要です。検索広告向けリマーケティングリスト（RLSA）統合とも呼ばれます。有料検索にのみ適用されます。
seo-title: Google AdWords リマーケティングリストへのセグメントの送信
solution: Audience Manager
title: Google AdWords リマーケティングリストへのセグメントの送信
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 72%

---


# Google Ads リマーケティングリストへのセグメントの送信 {#send-segments-to-a-google-adwords-remarketing-list}

This procedure requires a [!DNL Google Ads] remarketing list, pixel code, and an Audience Manager [!DNL URL] [!DNL destination]. 検索連動型広告のリマーケティングリスト（[!DNL RLSA]）との統合とも呼ばれます。有料検索にのみ適用されます。

>[!IMPORTANT]
>これは、2 つのシステムの製品化された統合ではありません。

To set up a [!DNL Google Ads] remarketing list as an [!DNL Audience Manager] [!DNL URL destination]:

1. [!DNL Google Ads] アカウントで、[Web サイトのリマーケティングリストを作成](https://support.google.com/adwords/answer/2454064?hl=ja)し、コンバージョン ID を書き出します。
1. ベース URL およびセキュア URL のテンプレートとして、次の URL を使用します。xxxxxxxx セクションをコンバージョン ID に置き換えます。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [Create a [!DNL URL destination]](../../features/destinations/create-url-destination.md) or edit an existing [!DNL destination]. Use the following settings when creating the [!DNL destination]:
   * Type：URL
   * Serialize：Enabled
   * Delimiter：Semicolon（;）

1. In the [!UICONTROL Segment Mappings] section of your [!DNL URL] [!DNL destination], add the code from step 2 to the [!DNL URL] and [!DNL Secure URL] fields. [!DNL URL] および [!DNL Secure URL] フィールドで、コードにそれぞれ `http:` と `https:` のプレフィックスを付けます。

   >[!IMPORTANT]
   >
   >エンコードされているアンパサンド（`&`）は、エンコードされていないアンパサンド（`&`）に置き換えます。

   安全でない [!DNL URL] コード：

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   セキュア [!DNL URL] コード：

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 「**[!UICONTROL Save]**」をクリックします。

   >[!NOTE]
   >
   >If you&#39;re working with multiple segments, get a new pixel for each segment you want to map to a [!DNL Google Ads] [!DNL destination]. これにより、データが所定のリマーケティングリストに適用されます。

1. When mapping a new segment to this [!DNL destination] in Audience Manager, define the mapping as `aam=segmentID` and replace `segmentID` with the ID of your segment.
1. [!DNL Google Ads] でバケットを定義する際には、手順 6 で定義したマッピングを照合するルールrを作成します。

マッピングが完了すると、次のようになります。

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [指標をさらに制限する [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [AdWords リマーケティングリストについて](https://support.google.com/adwords/answer/2472738?hl=ja)
>* [AdWords リマーケティングの仕組み](https://support.google.com/adwords/answer/2454000)

