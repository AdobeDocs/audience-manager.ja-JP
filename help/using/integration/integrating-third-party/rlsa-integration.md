---
description: 以下の手順には、AdWords リマーケティングリスト、ピクセルコード、Audience Manager の URL 宛先が必要です。検索広告向けリマーケティングリスト（RLSA）統合とも呼ばれます。有料検索にのみ適用されます。
seo-description: 以下の手順には、AdWords リマーケティングリスト、ピクセルコード、Audience Manager の URL 宛先が必要です。検索広告向けリマーケティングリスト（RLSA）統合とも呼ばれます。有料検索にのみ適用されます。
seo-title: セグメントを Google Adwords リマーケティングリストに送信
solution: Audience Manager
title: セグメントを Google Adwords リマーケティングリストに送信
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

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

1. In Audience Manager, [Create a URL destination](../../features/destinations/create-url-destination.md) or edit an existing destination. 宛先を作成する際には、次の設定を使用します。
   * タイプ:URL
   * シリアライズ:有効にする
   * Delimiter:セミコロン（;）

1. 宛先の [!UICONTROL Segment Mappings] セクションで [!DNL URL] 、手順2から [!DNL URL][!DNL Secure URL] フィールドにコードを追加します。コードに、それぞれ `http:` と `https:`[!DNL URL][!DNL Secure URL] フィールドとフィールドのプレフィックスを付けます。

   >[!IMPORTANT]
   >
   >エンコードされているアンパサンド（`&`）は、エンコードされていないアンパサンド（`&`）に置き換えます。

   安全 [!DNL URL] でないコード:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   セキュア [!DNL URL] コード:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. **[!UICONTROL Save]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >複数のセグメントを使用している場合は、Google広告の宛先にマップする各セグメントの新しいピクセルを取得します。これにより、データが所定のリマーケティングリストに適用されます。

1. 新しいセグメントをAudience `aam=segmentID` Managerでこの宛先にマッピングする場合、マッピングを定義して、セグメントのID `segmentID` に置き換えます。
1. で [!DNL Google Ads]グループを定義する場合、手順6で定義したマッピングに一致するルールを作成します。

マッピングが完了すると、次のようになります。

![](../assets/rlsa_mapping.png)

>[!MORE_LIKE_THIS]
>
>* [宛先](../../features/destinations/destinations.md)
>* [URL 宛先の作成](../../features/destinations/create-url-destination.md)
>* [AdWords リマーケティングリストについて](https://support.google.com/adwords/answer/2472738)
>* [AdWords リマーケティングの仕組み](https://support.google.com/adwords/answer/2454000)

