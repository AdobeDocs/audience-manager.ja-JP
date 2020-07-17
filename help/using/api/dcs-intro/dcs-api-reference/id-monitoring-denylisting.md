---
description: DCSは、受信したIDを監視し、短時間に異常に高い率で送信されたIDをブロックリストに追加します。
keywords: id;monitoring;dcs
seo-description: DCSは、受信したIDを監視し、短時間に異常に高い率で送信されたIDをブロックリストに追加します。
seo-title: ID の監視と拒否リスト登録
solution: Audience Manager
title: ID の監視と拒否リスト登録
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 35%

---


# ID の監視と拒否リスト登録

The [!DNL DCS] monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.

## 概要

Audience Manager インフラストラクチャを悪意のあるアクティビティから保護するため、[!DNL DCS] は高度なアルゴリズムを使用して受信する ID を監視します。[!UICONTROL Data Provider Unique User ID]（[!UICONTROL CRM ID]）、[!UICONTROL Audience Manager Unique User ID]（[!UICONTROL AAM UUID]）、または [!UICONTROL Experience Cloud ID]（[!UICONTROL ECID]）を使用できます。Audience Manager でサポートされる ID について詳しくは、[Audience Manager の ID のインデックス](../../../reference/ids-in-aam.md)を参照してください。

[!DNL DCS] は悪意の可能性があるアクティビティを検出するために、これらの ID を受信する頻度を監視します。When the [!DNL DCS] detects an unusually large amount of [!DNL DCS] requests for any given ID in a short amount of time, that ID is added to a deny list.

## エラーコード

ブロックリストに追加されたIDは、から受け取ったエラーコードで識別でき [!DNL DCS]ます。 受信する可能性のあるエラーコードは次のとおりです。

* 303: Blocked customer ID
* 306: Blocked declared device ID
* 307: Blocked profile operation for ID

受信する可能性のあるエラーコードについて詳しくは、[DCS エラーコード、メッセージ、例](dcs-error-codes.md)を参照してください。

## ブロックリストからのIDの削除

ブロックリストに追加されたIDは、誤ったデータレポートを引き起こすので、今後のリクエストでは使用しないでください。 では、ブロックリストからIDを削除することはサポートされていません。 [!DNL DCS]

## ID 同期への影響

[!DNL DCS] 呼び出しには、1 つまたは複数のタイプの ID を含めることができます。単一のIDを含む呼び出しは、そのIDがブロックリストに追加され、この状況ではID同期が発生しない場合、完全に無視されます。

When a multiple ID call also includes a denylisted ID, the [!DNL DCS] disregards the denied ID and only uses the remaining, allowed IDs for synchronization.

## IDブロックリストに加えるの原因と修正

IDがブロックリストに追加される最も多い原因は、顧客のインフラストラクチャとAudience Managerの間の誤った統合です。 IDを特定する場合は、Audience Managerブロックリストに加える統合を十分に確認してください。 Audience Manager を Experience Cloud の他のソリューションまたは外部システムと連携するように設定する方法について詳しくは、**実装および統合ガイド**&#x200B;を参照してください。

Another frequent cause of IDs being added to deny lists are indexing bots (web crawlers), which generally cause increases in traffic, leading to the same IDs being sent to the [!DNL DCS] multiple times. ブロックリストにIDが追加される理由としてインデックスボットを識別する場合は、Webサイトへのボットアクセスを制限する必要があります。

統合に関する問題を特定できない場合は、カスタマーサポートまでお気軽にお問い合わせください。サポートリクエストを開始する前に、必ずブラウザーの `.har` `HTTP` アーカイブを準備しておいてください。このアーカイブは、サポートチームがIDがブロックリストに追加された理由を特定するのに役立ちます。