---
description: DCS は受信する ID を監視し、一定期間に異常に高い頻度で送信された ID をブラックリストに登録します。
keywords: ID;監視;ブラックリスト登録;DCS
seo-description: DCS は受信する ID を監視し、一定期間に異常に高い頻度で送信された ID をブラックリストに登録します。
seo-title: ID の監視とブラックリスト登録
solution: Audience Manager
title: ID の監視とブラックリスト登録
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: ht
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# ID の監視とブラックリスト登録

[!UICONTROL DCS] は受信する ID を監視し、一定期間に異常に高い頻度で送信された ID をブラックリストに登録します。

## 概要

Audience Manager インフラストラクチャを悪意のあるアクティビティから保護するため、[!UICONTROL DCS] は高度なアルゴリズムを使用して受信する ID を監視します。[!UICONTROL Data Provider Unique User ID]（[!UICONTROL CRM ID]）、[!UICONTROL Audience Manager Unique User ID]（[!UICONTROL AAM UUID]）、または [!UICONTROL Experience Cloud ID]（[!UICONTROL ECID]）を使用できます。Audience Manager でサポートされる ID について詳しくは、[Audience Manager の ID のインデックス](../../../reference/ids-in-aam.md)を参照してください。

[!UICONTROL DCS] は悪意の可能性があるアクティビティを検出するために、これらの ID を受信する頻度を監視します。[!UICONTROL DCS] がある特定の ID について、短期間に大量の [!UICONTROL DCS] リクエストを検出すると、その ID はブラックリストに登録されます。

## エラーコード

[!UICONTROL DCS] から受信したエラーコードによって、ブラックリストに登録された ID を識別できます。受信する可能性のあるエラーコードは次のとおりです。

* 303: Blocked customer ID
* 306: Blocked declared device ID
* 307: Blocked profile operation for ID

受信する可能性のあるエラーコードについて詳しくは、[DCS エラーコード、メッセージ、例](dcs-error-codes.md)を参照してください。

## ブラックリストの登録解除

ブラックリストに登録された ID は、データレポートが不正確になるので、今後のリクエストでは使用しないでください。[!UICONTROL DCS] では、ID のブラックリスト登録解除はサポートされていません。

## ID 同期への影響

[!UICONTROL DCS] 呼び出しには、1 つまたは複数のタイプの ID を含めることができます。単一の ID を含む呼び出しは、その ID がブラックリストに登録されている場合、完全に無視され、この状況で ID 同期はおこなわれません。

複数の ID 呼び出しにブラックリストに登録されている ID も含まれる場合、[!UICONTROL DCS] はブラックリストに登録されている ID を無視し、残りのブラックリストに登録されていない ID のみを同期に使用します。

## ID のブラックリスト登録の原因と修正点

ID がブラックリストに登録される最もよくある原因は、顧客インフラストラクチャと Audience Manager 間の不適切な統合です。ID がブラックリストに登録された場合は、Audience Manager の統合を十分に確認してください。Audience Manager を Experience Cloud の他のソリューションまたは外部システムと連携するように設定する方法について詳しくは、**実装および統合ガイド**&#x200B;を参照してください。

ID がブラックリストに登録される別のよくある原因は、ボット（Web クローラー）のインデックス作成です。通常、これによってトラフィックが増加し、同じ ID が複数回 [!UICONTROL DCS] に送信されます。ID がブラックリストに登録された原因が、ボットのインデックス作成であると特定された場合は、ボットのアクセスを Web サイトに制限する必要があります。

統合に関する問題を特定できない場合は、カスタマーサポートまでお気軽にお問い合わせください。サポートリクエストを開始する前に、必ずブラウザーの `.har` `HTTP` アーカイブを準備しておいてください。このアーカイブは、サポートチームが ID がブラックリストに登録された理由を特定するのに役立ちます。