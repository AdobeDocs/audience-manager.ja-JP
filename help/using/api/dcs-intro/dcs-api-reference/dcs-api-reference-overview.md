---
description: DCS API のコード、メソッド、プロセスの概念的情報、説明、定義です。
seo-description: Adobe Audience Manager（AAM）の DCS API のコード、メソッド、プロセスの概念的情報、説明、定義です。
seo-title: Adobe Audience Manager（AAM）の DCS API リファレンスの概要
title: DCS API リファレンスの概要
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 89%

---


# DCS API リファレンスの概要

DCS API のコード、メソッド、プロセスの概念的情報、説明、定義です。

* [DCS API メソッド](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   GET または POST メソッドを使用して DCS API にデータを送信します。

* [DCS エラーコード、メッセージ、例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   データ収集サーバー（DCS）で生成されるエラーコードおよびメッセージをコード ID の順に説明します。

* [IDの監視と非公開](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   DCSは、受信したIDを監視し、短時間に異常に高い率で送信されたIDを拒否リストに追加します。

* [DCS の地域 ID、場所、ホスト名](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   DCS の呼び出しをおこなうには、地域 DCS サーバーのホスト名が必要です。DCS では、サイト訪問者に地理的に近いデータセンターに情報を保存するからです。間違った DCS にクエリを送信しても機能しますが、そのような呼び出しは非効率的で、応答の遅延につながるおそれがあります。DCS 要求をおこなうには、地域 ID を対応する地域ホスト名に合わせ、適切なホスト名でクエリを作成します。

* [DCS 呼び出しでのキー値ペアの形式](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   呼び出しをおこなう場合、DCS では標準形式またはシリアル化された形式のキー値ペアデータを受信します。この節では、標準のキーと値のペアのデータとシリアル化されたキーと値のペアのデータの形式について説明します。

* [競合状態とエラー処理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   競合状態を防ぐ方法と DCS エラー処理について説明します。

* [DCS API 呼び出しでサポートされている属性](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   データ収集サーバー（DCS）に渡すことができるデータの構文とサポートされている属性（キー値ペア）について説明します。この情報は、DCS 要求の形式設定や DCS システムから返されるパラメーターの理解に役立ちます。
