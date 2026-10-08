---
description: セグメントビルダーを使用してアクティブなセグメントを一時停止または削除した場合の、セグメント化されたユーザー、データおよび宛先に対する影響について説明します。
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: 一時停止および削除されたセグメント
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
TQID: 'https://experienceleague.adobe.com/aLnmaOxB3fkGdwq4XjKz8SFKizwHI7Ll5rBUb-o34BM'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
  - id: b89b323a-1e91-40b1-8d20-96b5b726d55a
    internal-label: Audience management
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
    internal-label: REST APIs
  - id: b52f95d5-ca6b-4fda-a49e-994dc0a63402
    internal-label: Segments
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 100%
---
# 一時停止および削除されたセグメント {#paused-and-deleted-segments}

[!UICONTROL Segment Builder] を使用してアクティブなセグメントを一時停止または削除した場合の、セグメント化されたユーザー、データおよび宛先に対する影響について説明します。

## 一時停止および削除コントロールへのアクセス

セグメントリストでセグメント名の上にマウスポインターを置くと、**[!UICONTROL pause]** および **[!UICONTROL delete]** アイコンが（[!UICONTROL Actions] 列に）表示されます。 これらの機能は、前述のように、セグメントに影響します。

## 一時停止されたセグメントの機能

一時停止（非アクティブ化）されたセグメント：

* 対象として新しく認定されたユーザーのセグメント化を停止する。
* ユーザーのセグメントステータス／メンバーシップを保持する（セグメントからユーザーを削除しない）。
* セグメントリストが維持されるので、再アクティブ化が可能。
* 関連する宛先にデータを送信しない。
* （非アクティブ化した日までの）使用可能なレポートのデータを返す。

## 削除されたセグメントの機能

削除されたセグメント：

* 対象として新しく認定されたユーザーのセグメント化を停止する。
* セグメントメンバーシップから対象ユーザーを削除する。
* セグメントリストから削除される。
* 削除を取り消すことはできない。
* 関連する宛先にデータを送信しない。
* 使用可能なレポートのデータを返さない。

>[!NOTE]
>
>[!DNL API] メソッドを使用してセグメントを一時停止および削除することもできます。 詳しくは、[REST API](../../api/rest-api-main/rest-api-main.md) を参照してください。
