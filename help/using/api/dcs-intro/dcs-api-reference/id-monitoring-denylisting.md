---
description: DCSは、受信したIDを監視し、短時間に異常に高い率で送信されたIDを拒否リストに追加します。
keywords: id;monitoring;dcs
seo-description: DCSは、受信したIDを監視し、短時間に異常に高い率で送信されたIDを拒否リストに追加します。
seo-title: IDの監視と非公開
solution: Audience Manager
title: IDの監視と非公開
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 33%

---


# IDの監視と非公開

The [!UICONTROL DCS] monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.

## 概要

Audience Manager インフラストラクチャを悪意のあるアクティビティから保護するため、[!UICONTROL DCS] は高度なアルゴリズムを使用して受信する ID を監視します。[!UICONTROL Data Provider Unique User ID]（[!UICONTROL CRM ID]）、[!UICONTROL Audience Manager Unique User ID]（[!UICONTROL AAM UUID]）、または [!UICONTROL Experience Cloud ID]（[!UICONTROL ECID]）を使用できます。Audience Manager でサポートされる ID について詳しくは、[Audience Manager の ID のインデックス](../../../reference/ids-in-aam.md)を参照してください。

[!UICONTROL DCS] は悪意の可能性があるアクティビティを検出するために、これらの ID を受信する頻度を監視します。When the [!UICONTROL DCS] detects an unusually large amount of [!UICONTROL DCS] requests for any given ID in a short amount of time, that ID is added to a deny list.

## エラーコード

拒否リストに追加されたIDは、から受け取ったエラーコードで識別でき [!UICONTROL DCS]ます。 受信する可能性のあるエラーコードは次のとおりです。

* 303: Blocked customer ID
* 306: Blocked declared device ID
* 307: Blocked profile operation for ID

受信する可能性のあるエラーコードについて詳しくは、[DCS エラーコード、メッセージ、例](dcs-error-codes.md)を参照してください。

## 拒否リストからIDを削除しています

リストを拒否するために追加されたIDは、誤ったデータレポートを引き起こすので、今後のリクエストでは使用しないでください。 では、拒否リストからIDを削除することはサポートされていません。 [!UICONTROL DCS]

## ID 同期への影響

[!UICONTROL DCS] 呼び出しには、1 つまたは複数のタイプの ID を含めることができます。単一のIDを含む呼び出しは、そのIDが拒否リストに追加され、この状況ではID同期が発生しない場合、完全に無視されます。

When a multiple ID call also includes a denylisted ID, the [!UICONTROL DCS] disregards the denied ID and only uses the remaining, allowed IDs for synchronization.

## ID非表示の原因と修正点

IDが追加されてリストを拒否する最も多くの原因は、顧客インフラストラクチャとオーディエンスマネージャとの間の誤った統合です。 非公開のIDを特定する場合は、オーディエンスマネージャー統合を十分に確認してください。 Audience Manager を Experience Cloud の他のソリューションまたは外部システムと連携するように設定する方法について詳しくは、**実装および統合ガイド**&#x200B;を参照してください。

Another frequent cause of IDs being added to deny lists are indexing bots (web crawlers), which generally cause increases in traffic, leading to the same IDs being sent to the [!UICONTROL DCS] multiple times. インデックスボットが追加されてリストが拒否される理由として識別される場合は、Webサイトへのボットアクセスを制限する必要があります。

統合に関する問題を特定できない場合は、カスタマーサポートまでお気軽にお問い合わせください。サポートリクエストを開始する前に、必ずブラウザーの `.har` `HTTP` アーカイブを準備しておいてください。このアーカイブは、サポートチームが拒否リストにIDが追加された理由を特定するのに役立ちます。