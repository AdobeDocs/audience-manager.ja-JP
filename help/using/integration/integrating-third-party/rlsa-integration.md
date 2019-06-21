---
description: 以下の手順には、AdWords リマーケティングリスト、ピクセルコード、Audience Manager の URL 宛先が必要です。検索広告向けリマーケティングリスト（RLSA）統合とも呼ばれます。有料検索にのみ適用されます。
seo-description: 以下の手順には、AdWords リマーケティングリスト、ピクセルコード、Audience Manager の URL 宛先が必要です。検索広告向けリマーケティングリスト（RLSA）統合とも呼ばれます。有料検索にのみ適用されます。
seo-title: セグメントを Google Adwords リマーケティングリストに送信
solution: Audience Manager
title: セグメントを Google Adwords リマーケティングリストに送信
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

This procedure requires a [!DNL Google Ads] remarketing list, pixel code, and an Audience Manager [!DNL URL] destination. It is also known as a remarketing list for search ads ([!DNL RLSA]) integration. 有料検索にのみ適用されます。

>[!IMPORTANT]
>これは、システムのシステム化された統合ではありません。

To set up a [!DNL Google Ads] remarketing list as an [!DNL Audience Manager] URL destination:

1. [!DNL Google Ads] アカウントで、Webサイトリマーケティングリスト [](https://support.google.com/adwords/answer/2454064?hl=en) を作成し、コンバージョンIDを書き留めます。
1. ベースURLおよびセキュアURLのテンプレートとして、次のURLを使用します。xxxxxxxxセクションを変換IDに置き換えます。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [Create a URL destination](../../features/destinations/manage-destinations.md#configure-url-destination) or edit an existing destination. 宛先を作成する際には、次の設定を使用します。
   * タイプ:URL
   * シリアライズ:有効にする
   * Delimiter:セミコロン（;）

1. In the [!UICONTROL Segment Mappings] section of your [!DNL URL] destination, add the code from step 2 to the [!DNL URL] and [!DNL Secure URL] fields. Prefix the code with `http:` and `https:` in the [!DNL URL] and [!DNL Secure URL] fields, respectively.

   >[!IMPORTANT]
   >
   >エンコードされているアンパサンド（`&`）は、エンコードされていないアンパサンド（`&`）に置き換えます。

   Unsecure [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. **[!UICONTROL Save]** をクリックします。

   >[!NOTE]
   >
   >複数のセグメントを使用している場合は、Google広告の宛先にマップする各セグメントの新しいピクセルを取得します。これにより、データが所定のリマーケティングリストに適用されます。

1. When mapping a new segment to this destination in Audience Manager, define the mapping as `aam=segmentID` and replace `segmentID` with the ID of your segment.
1. When defining a bucket in [!DNL Google Ads], create a rule that matches the mapping defined at step 6.

マッピングが完了すると、次のようになります。

![](../assets/rlsa_mapping.png)

>[!MORE_LIKE_THIS]
>
>* [宛先](../../features/destinations/destinations.md)
>* [URL 宛先の作成](../../features/destinations/manage-destinations.md#configure-url-destination)
>* [AdWords リマーケティングリストについて](https://support.google.com/adwords/answer/2472738)
>* [AdWords リマーケティングの仕組み](https://support.google.com/adwords/answer/2454000)

