---
description: 'ユーザーベースの宛先は、Audience Managerに共有可能なオーディエンスの概念を紹介します。この指標は、Audience Managerが宛先プラットフォームと共有できるハッシュ化された電子メールのいくつかを理解するのに役立ちます。 '
seo-description: 'ユーザーベースの宛先は、Audience Managerに共有可能なオーディエンスの概念を紹介します。この指標は、Audience Managerが宛先プラットフォームと共有できるハッシュ化された電子メールのいくつかを理解するのに役立ちます。 '
seo-title: 共有可能なオーディエンス
solution: Audience Manager
title: 共有可能なオーディエンス
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 共有可能なオーディエンス {#shareable-audiences}

[!DNL People-Based Destinations] Audience Manager [!DNL Shareable Audiences] の概念を紹介します。この指標は、Audience Managerが宛先プラットフォームと共有できるハッシュ化された電子メールのいくつかを理解するのに役立ちます。

[!DNL Shareable Audiences] は、コンテキストのオーディエンスデータを解釈するのに役立つ指標 [!DNL People-Based Destinations]です。この指標は [!UICONTROL Destinations] 、ページおよび [!UICONTROL Segment] ページ内で表示できます。

## セグメント共有可能オーディエンス {#segment-shareable-audiences}

セグメントページの [!DNL Segment Shareable Audience] 指標は、一致 [するDPUUIDを持つデータソースからのハッシュされた電子メールアドレスの数を示します。これ](../../reference/ids-in-aam.md)によって、そのデータソースに適用されたプロファイル結合ルールに加えて、特定のルックバック期間内の定義済みセグメントにも合致し、Audience Managerは宛先プラットフォームと共有できます。

この指標には1日のルックバック期間があります。これにより、特定の宛先でセグメントのオーディエンスリーチを把握できます。

## 宛先共有可能オーディエンス {#destination-shareable-audience}

ユーザーベースの宛先ページの [!DNL Destination Shareable Audience] 指標は、一致 [するDPUUID](../../reference/ids-in-aam.md)を持つデータソースからのハッシュされた電子メールアドレスの合計数を示し、その宛先にマッピングされているすべてのセグメントからAudience Managerが宛先プラットフォームと共有できるようにします。

![shareable- audiences](assets/dest-shareable-audiences.png)

この指標には全期間のルックバック期間があります。これにより、ハッシュ化された電子メールによって提供されるオーディエンスのスケールを把握して、データソースを把握できます。

## 例

Audience Managerの顧客には、110,000 [のDPUUID](../../reference/ids-in-aam.md) （CRM ID）のデータソースがあります。これらは、100,000ハッシュの電子メールアドレスをAudience Managerに取り込み、複数の人ベースの宛先で使用し、CRM IDに対して100,000のハッシュ化された電子メールアドレスにID同期を実行します。顧客は [!DNL All Cross-Device Profiles] 結合ルールを使用して、次の3つのオーディエンスセグメントを作成できます。

* セグメントA（訪問者のカウント10,000、リンク先Aにマッピング）
* セグメントB（20,000の母集団のカウント、Destination Aにマッピング済み）
* 訪問者Bにマッピングされた50,000の母集団数のセグメントC。

このシナリオでは、以下の手順に従います。

* セグメントA Shareable Audience=10,000;
* Segment B Shareable Audience=20,000;
* セグメントC Shareable Audience=50,000;
* Destination A Shareable Audience= Segment A Shareable Audience+ Segment B Shareable Audience=30,000;
* Destination B Shareable Audience= Segment C Shareable Audience=50,000.

![shareable- audiences- figure](assets/shareable-audiences.png)

> [!NOTE]
>
> 上記の例では、3つのセグメントのすべての80,000ハッシュの電子メールアドレスが、宛先プラットフォームの既存のアカウントと一致しているというわけではありません。これは、Audience Managerが3つのセグメントからそれぞれの宛先にハッシュ化された識別子を送信することを意味します。オーディエンスセグメントをユーザーベースの宛先に送信する場合、パートナー側でオーディエンスの一致が発生します。宛先Aには、一致するユーザーアカウントが最大30,000個ありますが、宛先Bには50,000個のユーザーアカウントがありますが、一致率は保証されません。パートナー固有の指標にはアクセスできません。一致率の「人ベースの宛先の表示に関するよくある質問»の?«一致率?[](../../faq/faq-people-based-destinations.md#match-rates)
