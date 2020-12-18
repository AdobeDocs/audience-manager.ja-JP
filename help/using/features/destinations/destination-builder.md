---
description: Destination Builder を使用すると、Cookie ベースの宛先や DNL URL の宛先を作成できます。Destination Builder では、サーバー間（S2S）の宛先を作成することはできませんが、サーバー間宛先のセグメントマッピングを管理することはできます。S2S の宛先をセットアップする場合は、担当のコンサルタントにお問い合わせください。Destination Builder には、Audience Data／Destinations でアクセスできます。
seo-description: Destination Builder を使用すると、Cookie ベースの宛先や DNL URL の宛先を作成できます。Destination Builder では、サーバー間（S2S）の宛先を作成することはできませんが、サーバー間宛先のセグメントマッピングを管理することはできます。S2S の宛先をセットアップする場合は、担当のコンサルタントにお問い合わせください。Destination Builder には、Audience Data／Destinations でアクセスできます。
seo-title: 宛先ビルダー
solution: Audience Manager
title: 宛先ビルダー
feature: Destination Basics
translation-type: ht
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: ht
source-wordcount: '317'
ht-degree: 100%

---


# 宛先ビルダー {#destination-builder}

[!UICONTROL Destination Builder] を使用すると、Cookie ベースの宛先や [!DNL URL] の宛先を作成できます。[!UICONTROL Destination Builder] では、サーバー間（[!DNL S2S]）の宛先を作成することはできませんが、サーバー間宛先のセグメントマッピングを管理することはできます。[!DNL S2S] の宛先をセットアップする場合は、担当のコンサルタントにお問い合わせください。[!UICONTROL Destination Builder]は&#x200B;**[!UICONTROL Audience Data > Destinations]**&#x200B;にあります。

## 宛先ビルダーの設定 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] は次のセクションと設定で構成されています。

| [!UICONTROL Destination Builder] セクション | 目的 |
|--- |--- |
| 基本情報 | 宛先の命名、宛先の説明、宛先のタイプ（[!DNL URL] または [!DNL cookie]）とプラットフォーム（すべて、[!DNL Android]、ブラウザー、[!DNL iOS]）の選択に使用します。 |
| 設定 | 次の用途のコントロールが含まれています。<br/><ul><li>[!DNL URL] の宛先にキーと値ペアデータを渡す。データは、個々のキー値ペアとして送信することも、シリアル化されたキーと値のペアとして送信することもできます。詳しくは、「[宛先のシリアル化](../../features/destinations/key-value-pairs.md#destination-serialized)」および「[標準型およびシリアル型のキーと値のペア](../../features/destinations/key-value-pairs.md)」を参照してください。 </li><li>Cookie の宛先の要素（Cookie の名前、ドメイン、サイズ、有効期間、データ形式など）を指定する。</li></ul> |
| Segment Mappings | 以下が可能です。<br/><ul><li>宛先のタイプ all に関連するセグメントの検索、追加、管理。 </li><li>個々のセグメントへの配信優先度の設定（[!DNL cookie] ベースのセグメントのみ）</li></ul> |

## データ配信方法 {#data-delivery-methods}

情報を宛先に送信するには、[!DNL URL] 文字列を通じて情報を渡す、ブラウザーの [!DNL cookie] に書き込む、オフラインのサーバー間データ転送を使用する、の 3 とおりの方法があります。

* [!DNL URL] および Cookie ベースの宛先は、ユーザーがページでアクションをおこなうたびに、データを同期的に送信します。
* サーバー間データ送信は非同期的で、ユーザーがページから移動した後かなり経ってからおこなわれることがあります。選択する配信タイプは、ビジネス要件と特定のデータパートナーによるデータの受信方法によって異なります。

詳しくは、[宛先のタイプを選択する方法](../../features/destinations/destinations.md)を参照してください。