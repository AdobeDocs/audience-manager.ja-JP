---
description: Destination Builderを使用すると、CookieベースのURLまたはDNL URLのリンク先を作成できます。Destination Builder では、サーバー間（S2S）の宛先を作成することはできませんが、サーバー間宛先のセグメントマッピングを管理することはできます。S2S の宛先をセットアップする場合は、担当のコンサルタントにお問い合わせください。Destination Builder には、Audience Data／Destinations でアクセスできます。
seo-description: Destination Builderを使用すると、CookieベースのURLまたはDNL URLのリンク先を作成できます。Destination Builder では、サーバー間（S2S）の宛先を作成することはできませんが、サーバー間宛先のセグメントマッピングを管理することはできます。S2S の宛先をセットアップする場合は、担当のコンサルタントにお問い合わせください。Destination Builder には、Audience Data／Destinations でアクセスできます。
seo-title: Destination Builder
solution: Audience Manager
title: Destination Builder
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# Destination Builder {#destination-builder}

[!UICONTROL Destination Builder] を使用すると、Cookieベースまたは [!DNL URL] リンク先を作成できます。You cannot create server-to-server ([!DNL S2S]) destinations with [!UICONTROL Destination Builder], but you can manage their segment mappings. Contact your consultant to set up a [!DNL S2S] destination. [!UICONTROL Destination Builder]**[!UICONTROL Audience Data > Destinations]**&#x200B;が配置されていることを確認します。

## Destination Builder の設定 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] は、以下の節と設定で構成されています。

| [!UICONTROL Destination Builder] セクション | 目的 |
|--- |--- |
| 基本情報 | Used to name the destination, describe it, and select destination type ([!DNL URL] or [!DNL cookie]), and platform (all, [!DNL Android], browser, or [!DNL iOS]). |
| 設定 | 次の用途のコントロールが含まれています。<br/><ul><li>Passing in key-value data to [!DNL URL] destinations. データは、個々のキー値ペアとして送信することも、シリアル化されたキー値ペアとして送信することもできます。詳しくは、[宛先のシリアル化](../../features/destinations/key-value-pairs.md#destination-serialized) と [標準とシリアルキーの値のペア](../../features/destinations/key-value-pairs.md) </li><li>Cookie の宛先の要素（Cookie の名前、ドメイン、サイズ、有効期間、データ形式など）を指定する。</li></ul> |
| Segment Mappings | レポートを: <br/><ul><li>宛先のタイプ all に関連するセグメントの検索、追加、管理。 </li><li>Set delivery priorities on individual segments (for [!DNL cookie]-based segments only).</li></ul> |

## データ配信方法 {#data-delivery-methods}

Send information to a destination by passing it in through a [!DNL URL] string, by writing to a browser [!DNL cookie], or through offline server-to-server data transfers.

* [!DNL URL] および Cookie ベースの宛先は、ユーザーがページでアクションをおこなうたびに、データを同期的に送信します。
* サーバー間データ送信は非同期的で、ユーザーがページから移動した後かなり経ってからおこなわれることがあります。選択する配信タイプは、ビジネス要件と特定のデータパートナーによるデータの受信方法によって異なります。

詳しくは、[宛先のタイプを選択する方法](../../features/destinations/destinations.md)を参照してください。