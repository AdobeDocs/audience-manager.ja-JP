---
description: 競合状態を防ぐ方法と DCS エラー処理について説明します。
seo-description: 競合状態を防ぐ方法と DCS エラー処理について説明します。
seo-title: 競合状態とエラー処理
solution: Audience Manager
title: 競合状態とエラー処理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 100%

---


# 競合状態とエラー処理 {#race-conditions-and-error-handling}

競合状態を防ぐ方法と [!DNL DCS] エラー処理について説明します。

## 競合状態の防止 {#prevent-race-conditions}

競合状態が起こる可能性があるのは、最初のクエリへの応答とユーザーの Cookie へのデータの書き込みを [!DNL DCS] が完了しないうちに、複数の呼び出しを同時に（または矢継ぎ早に）DCS に送信する場合です。競合状態が起こると、Cookie データが破損したり不適切に上書きされるおそれがあるので、好ましくありません。ベストプラクティスとして次の対処法を考慮すると、この問題を避けるのに役に立ちます。

* 同じユーザーから [!DNL DCS] への複数の呼び出しを同時にまたは矢継ぎ早におこなわない。
* 応答が戻ってくるのを待ってから、次の呼び出しをおこなう。

## エラー処理  {#error-handling}

無効なクエリや不完全な形式のクエリの場合は、エラー処理が限られます。無効な要求の場合は、`HTTP 200 OK` 応答が返されるだけで、データは返されません。また、ユーザーが以下のいずれかに該当する場合、[!DNL DCS] は要求の処理を停止し、特性データを破棄し、`HTTP 200 OK` 応答を返します。

* Audience Manager レベルまたはパートナーレベルでの追跡をオプトアウトしている。
* 無効な地域または選択されていない地域に所在している。
* ブラウザーの Cookie（すべてまたはサードパーティのみ）を無効にしている。

詳しくは、[DCS エラー コード、メッセージ、例](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)を参照してください。