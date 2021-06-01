---
description: 宛先とセグメントマッピングを削除するための DELETE メソッドと POST メソッド
seo-description: 宛先とセグメントマッピングを削除するための DELETE メソッドと POST メソッド
seo-title: 宛先の削除
solution: Audience Manager
title: 宛先の削除
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 100%

---

# 宛先の削除 {#delete-destinations}

宛先およびセグメントマッピングを削除できる `DELETE` および `POST` メソッド。

<!-- r_delete_destinations_all.xml -->

## 宛先の削除

宛先を削除するための `DELETE` メソッド。

>[!NOTE]
>
>宛先を削除できるようにするには、その前にすべてのセグメントマッピングを削除する必要があります。

* リクエスト：`DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* レスポンス：成功すると、コード `204 No Content` が返されます。

## 宛先の一括削除

この `POST` メソッドで複数の宛先を削除します。リクエスト本文内で配列を使用して宛先 ID（`destinationId`）を渡します。

* リクエスト：`POST https://api.demdex.com/v1/destinations/bulk-delete/`
* レスポンス：成功すると、コード `204 No Content` が返されます。

## セグメントマッピング ID による宛先マッピングの削除

指定したセグメント ID に従って宛先マッピングを削除する `POST` メソッド。

* リクエスト：`DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* レスポンス：成功すると、コード `204 No Content` が返されます。
