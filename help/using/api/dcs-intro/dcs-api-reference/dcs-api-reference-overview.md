---
description: DCS API のコード、メソッド、プロセスの概念的情報、説明、定義です。
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: DCS API リファレンスの概要
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
TQID: https://experienceleague.adobe.com/e7W6fcETh4YArPa0k2hn11GMYgFjSU4AxALe92a7DhE
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 276
ht-degree: 100%

---

# DCS API リファレンスの概要

[!DNL DCS API] のコード、メソッド、プロセスの概念的情報、説明、定義です。

* [DCS API メソッド](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

  GET または POST メソッドを使用して [!DNL DCS API] にデータを送信します。

* [DCS エラーコード、メッセージ、例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

  データ収集サーバー（DCS）で生成されるエラーコードおよびメッセージをコード ID 順に説明します。

* [ID のモニタリングと拒否リストへの登録](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

  DCS は受信する ID を監視し、一定期間に異常に高い頻度で送信された ID をブロックリストに登録します。

* [DCS の地域 ID、場所、ホスト名](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

  DCS の呼び出しをおこなうには、地域 DCS サーバーのホスト名が必要です。DCS では、サイト訪問者に地理的に近いデータセンターに情報を保存するからです。間違った DCS にクエリを送信しても機能しますが、そのような呼び出しは非効率的で、応答の遅延につながるおそれがあります。DCS リクエストをおこなうには、地域 ID を対応する地域ホスト名に合わせ、適切なホスト名でクエリを作成します。

* [DCS 呼び出しでのキー値ペアの形式](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

  呼び出しをおこなう場合、DCS では標準形式またはシリアル化された形式のキー値ペアデータを受信します。この節では、標準のキー値ペアデータとシリアル化されたキー値ペアデータの形式について説明します。

* [競合状態とエラー処理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

  競合状態を防ぐ方法と DCS エラー処理について説明します。

* [DCS API 呼び出しでサポートされている属性](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

  データ収集サーバー（DCS）に渡すことができるデータの構文とサポートされている属性（キー値ペア）について説明します。この情報は、DCS リクエストの形式設定や DCS システムから返されるパラメーターの理解に役立ちます。
