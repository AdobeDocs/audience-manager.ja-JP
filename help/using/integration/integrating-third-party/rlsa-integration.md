---
description: 以下の手順には、AdWords リマーケティングリスト、ピクセルコード、Audience Manager の URL 宛先が必要です。検索広告向けリマーケティングリスト（RLSA）統合とも呼ばれます。有料検索にのみ適用されます。
seo-description: 以下の手順には、AdWords リマーケティングリスト、ピクセルコード、Audience Manager の URL 宛先が必要です。検索広告向けリマーケティングリスト（RLSA）統合とも呼ばれます。有料検索にのみ適用されます。
seo-title: Google AdWords リマーケティングリストへのセグメントの送信
solution: Audience Manager
title: Google AdWords リマーケティングリストへのセグメントの送信
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
translation-type: ht
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Google Ads リマーケティングリストへのセグメントの送信 {#send-segments-to-a-google-adwords-remarketing-list}

以下の手順には、[!DNL Google Ads] リマーケティングリスト、ピクセルコード、Audience Manager の [!DNL URL] 宛先が必要です。検索連動型広告のリマーケティングリスト（[!DNL RLSA]）との統合とも呼ばれます。有料検索にのみ適用されます。

>[!IMPORTANT]
>これは、2 つのシステムの製品化された統合ではありません。

[!DNL Google Ads] リマーケティングリストを [!DNL Audience Manager] の URL 宛先として設定するには：

1. [!DNL Google Ads] アカウントで、[web サイトのリマーケティングリストを作成](https://support.google.com/adwords/answer/2454064?hl=ja)し、コンバージョン ID を書き出します。
1. ベース URL およびセキュア URL のテンプレートとして、次の URL を使用します。xxxxxxxx セクションをコンバージョン ID に置き換えます。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Audience Manager で、[URL 宛先を作成](../../features/destinations/create-url-destination.md)するか、既存の宛先を編集します。宛先を作成する際には、次の設定を使用します。
   * Type：URL
   * Serialize：Enabled
   * Delimiter：Semicolon（;）

1. [!DNL URL] 宛先の [!UICONTROL Segment Mappings] セクションで、手順 2 のコードを [!DNL URL] および [!DNL Secure URL] フィールドに追加します。[!DNL URL] および [!DNL Secure URL] フィールドで、コードにそれぞれ `http:` と `https:` のプレフィックスを付けます。

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
   >複数のセグメントを操作している場合、Google Ads の宛先にマッピングする各セグメントの新しいピクセルを取得します。これにより、データが所定のリマーケティングリストに適用されます。

1. 新しいセグメントを Audience Manager の宛先にマッピングする際は、マッピングを `aam=segmentID` として定義し、`segmentID` をセグメントの ID に置き換えます。
1. [!DNL Google Ads] でバケットを定義する際には、手順 6 で定義したマッピングを照合するルールrを作成します。

マッピングが完了すると、次のようになります。

![](../assets/rlsa_mapping.png)

>[!MORE_LIKE_THIS]
>
>* [宛先](../../features/destinations/destinations.md)
>* [URL 宛先の作成](../../features/destinations/create-url-destination.md)
>* [AdWords リマーケティングリストについて](https://support.google.com/adwords/answer/2472738)
>* [AdWords リマーケティングの仕組み](https://support.google.com/adwords/answer/2454000)

