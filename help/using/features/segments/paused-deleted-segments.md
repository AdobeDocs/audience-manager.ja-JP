---
description: セグメントビルダーを使用してアクティブなセグメントを一時停止または削除した場合の、セグメント化されたユーザー、データおよび宛先に対する影響について説明します。
seo-description: セグメントビルダーを使用してアクティブなセグメントを一時停止または削除した場合の、セグメント化されたユーザー、データおよび宛先に対する影響について説明します。
seo-title: 一時停止および削除されたセグメント
solution: Audience Manager
title: 一時停止および削除されたセグメント
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 一時停止および削除されたセグメント {#paused-and-deleted-segments}

Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using [!UICONTROL Segment Builder].

## 一時停止および削除コントロールへのアクセス

Hover over a segment name in the segments list to expose the **[!UICONTROL pause]** and **[!UICONTROL delete]** icons (in the [!UICONTROL Actions] column). これらの機能は、前述のように、セグメントに影響します。

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
>[!DNL API] メソッドを使用してセグメントを一時停止および削除することもできます。詳しくは、[REST API](../../api/rest-api-main/rest-api-main.md) を参照してください。