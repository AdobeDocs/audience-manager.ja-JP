---
description: 競合状態を防ぐ方法と DCS エラー処理について説明します。
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: 競合状態とエラー処理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 58%

---

# 競合状態、レート制限、エラー処理 {#race-conditions-and-error-handling}

競合状態を防ぐ方法と [!DNL DCS] エラー処理について説明します。

## 競合状態の防止 {#prevent-race-conditions}

最初のクエリへの応答とユーザーの cookie へのデータの書き込みが完了する前に、[!DNL DCS] ーザーに対して複数の呼び出しを同時に（または連続して）送信すると、競合状態が発生する可能性があります。 競合状態が起こると、Cookie データが破損したり不適切に上書きされるおそれがあるので、好ましくありません。ベストプラクティスとして次の対処法を考慮すると、この問題を避けるのに役に立ちます。

* 同じユーザーから [!DNL DCS] への複数の呼び出しを同時にまたは矢継ぎ早におこなわない。
* 応答が戻ってくるのを待ってから、次の呼び出しをおこなう。

## レート制限 {#rate-limiting}

Adobeでは、サービスの可用性に悪影響を与える可能性のある過度の DCS API 呼び出しを検出した場合、レート制限が行われる可能性があります。

レート制限が有効になっている場合は、DCS 呼び出しで `429 Too Many Requests` HTTP 応答ステータスコードが返される場合があります。 この HTTP 応答を受信した場合は、後で API 呼び出しを再試行してください。

## エラー処理 {#error-handling}

無効なクエリや不完全な形式のクエリの場合は、エラー処理が限られます。無効な要求の場合は、`HTTP 200 OK` 応答が返されるだけで、データは返されません。また、ユーザーが以下のいずれかに該当する場合、[!DNL DCS] は要求の処理を停止し、特性データを破棄し、`HTTP 200 OK` 応答を返します。

* Audience Manager レベルまたはパートナーレベルでの追跡をオプトアウトしている。
* 無効な地域または選択されていない地域に所在している。
* ブラウザーの Cookie（すべてまたはサードパーティのみ）を無効にしている。

[DCS エラーコード、メッセージ、例 &#x200B;](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md) も参照してください。
