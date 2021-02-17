---
description: DCS は受信する ID を監視し、一定期間に異常に高い頻度で送信された ID をブロックリストに登録します。
keywords: id；監視；dcs
seo-description: DCS は受信する ID を監視し、一定期間に異常に高い頻度で送信された ID をブロックリストに登録します。
seo-title: ID の監視と拒否リスト登録
solution: Audience Manager
title: ID の監視と拒否リスト登録
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 99%

---


# ID の監視と拒否リスト登録

[!DNL DCS] は受信する ID を監視し、一定期間に異常に高い頻度で送信された ID をブロックリストに登録します。

## 概要

Audience Manager インフラストラクチャを悪意のあるアクティビティから保護するため、[!DNL DCS] は高度なアルゴリズムを使用して受信する ID を監視します。[!UICONTROL Data Provider Unique User ID]（[!UICONTROL CRM ID]）、[!UICONTROL Audience Manager Unique User ID]（[!UICONTROL AAM UUID]）、または [!UICONTROL Experience Cloud ID]（[!UICONTROL ECID]）を使用できます。Audience Manager でサポートされる ID について詳しくは、[Audience Manager の ID のインデックス](../../../reference/ids-in-aam.md)を参照してください。

[!DNL DCS] は悪意の可能性があるアクティビティを検出するために、これらの ID を受信する頻度を監視します。[!DNL DCS] がある特定の ID について、短期間に大量の [!DNL DCS] リクエストを検出すると、その ID はブロックリストに追加されます。

## エラーコード

ブロックリストに追加された ID は、[!DNL DCS]から受け取ったエラーコードで識別できます。受信する可能性のあるエラーコードは次のとおりです。

* 303: Blocked customer ID
* 306: Blocked declared device ID
* 307: Blocked profile operation for ID

受信する可能性のあるエラーコードについて詳しくは、[DCS エラーコード、メッセージ、例](dcs-error-codes.md)を参照してください。

## ブロックリストからの ID の削除

不正なデータレポートにつながるため、ブロックリストに追加された ID は今後のリクエストで使用しないでください。[!DNL DCS] では、ブロックリストから ID を削除することはサポートされていません。

## ID 同期への影響

[!DNL DCS] 呼び出しには、1 つまたは複数のタイプの ID を含めることができます。単一の ID を含む呼び出しは、その ID がブロックリストに登録されている場合、完全に無視され、この状況で ID 同期はおこなわれません。

複数の ID 呼び出しにブロックリストに登録されている ID も含まれる場合、[!DNL DCS] はブロックリストに登録されている ID を無視し、残りの許可されている ID のみを同期に使用します。

## ID のブロックリスト登録の原因と修正点

ID がブロックリストに追加される原因として最もよくあるのは、顧客インフラストラクチャと Audience Manager 間の不適切な統合です。ID がブロックリストに登録された場合は、Audience Manager の統合を十分に確認してください。Audience Manager を Experience Cloud の他のソリューションまたは外部システムと連携するように設定する方法について詳しくは、**実装および統合ガイド**&#x200B;を参照してください。

ID がブロックリストに登録される別のよくある原因は、ボット（Web クローラー）のインデックス作成です。通常、これによってトラフィックが増加し、同じ ID が複数回 [!DNL DCS] に送信されます。ブロックリストに ID が追加される理由としてインデックスボットを識別する場合は、Web サイトへのボットアクセスを制限する必要があります。

統合に関する問題を特定できない場合は、カスタマーサポートまでお気軽にお問い合わせください。サポートリクエストを開始する前に、必ずブラウザーの `.har` `HTTP` アーカイブを準備しておいてください。このアーカイブは、サポートチームが ID がブロックリストに追加された理由を特定するのに役立ちます。