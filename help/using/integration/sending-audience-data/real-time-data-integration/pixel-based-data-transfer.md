---
description: シンプルなピクセル（ユーザーを特性の対象に認定するのに使用できる）で、リアルタイムデータ転送を実行します。Audience Manager インターフェイスを使用すると、クライアントは、任意の数のピクセルをセルフサービスベースで作成できます。ピクセル文字列は、シンプルな ID またはキー値ペアで構成されます。
seo-description: シンプルなピクセル（ユーザーを特性の対象に認定するのに使用できる）で、リアルタイムデータ転送を実行します。Audience Manager インターフェイスを使用すると、クライアントは、任意の数のピクセルをセルフサービスベースで作成できます。ピクセル文字列は、シンプルな ID またはキー値ペアで構成されます。
seo-title: ピクセルベースのデータ転送
solution: Audience Manager
title: ピクセルベースのデータ転送
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 100%

---


# ピクセルベースのデータ転送 {#pixel-based-data-transfers}

シンプルなピクセル（ユーザーを特性の対象に認定するのに使用できる）で、リアルタイムデータ転送を実行します。Audience Manager インターフェイスを使用すると、クライアントは、任意の数のピクセルをセルフサービスベースで作成できます。ピクセル文字列は、シンプルな ID またはキー値ペアで構成されます。

<!-- c_rt_inbound_pixel_transfers.xml -->

受信データ転送を有効にするには、ベンダーおよびクライアントは以下をおこないます。

1. ベンダーまたはパートナーが発動する特性を決定します。
1. 特性のピクセルを取得します。特性リスト画面で、**[!UICONTROL Actions]** 列の上にマウスポインターを置いて、目的の特性の **[!UICONTROL Get trait URL]** 記号をクリックします。
1. [!DNL URL] をベンダーまたはパートナーに提供します。

## 例

この基本的なイベント呼び出しでは、特性 ID 1234 を [!DNL Audience Manager] に送信します。

```
https://something.demdex.net/event?d_sid=1234
```

イベント呼び出しで特性 ID をシリアル化すると、ページからの `HTTP` トラフィックの削減に役立ちます。次の例に示すように、追加の特性 ID を URL 文字列に追加します。

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
