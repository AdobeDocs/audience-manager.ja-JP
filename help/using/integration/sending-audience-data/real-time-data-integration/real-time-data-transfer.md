---
description: リアルタイム受信データ取り込みプロセスは、ユーザーのブラウザーからの一連の HTTP リクエストを使用して、Audience Manager にデータを渡します。
seo-description: リアルタイム受信データ取り込みプロセスは、ユーザーのブラウザーからの一連の HTTP リクエストを使用して、Audience Manager にデータを渡します。
seo-title: リアルタイム受信データ取り込み
solution: Audience Manager
title: リアルタイム受信データ取り込み
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 100%

---


# リアルタイム受信データ取り込み {#real-time-inbound-data-ingestion}

リアルタイム受信データ取り込みプロセスは、ユーザーのブラウザーからの一連の `HTTP` リクエストを使用して、Audience Manager にデータを渡します。

<!-- c_rt_inbound_real_time.xml -->

受信データは、シグナルと呼ばれるキー値ペアの形式である必要があります。通常、各シグナルは、ユーザーインターフェイスまたは [!DNL API] で作成または管理されたセグメントにマッピングされます。

## URL 文字列パラメーターおよび構文 {#url-string-syntax}

受信データ転送の [!DNL URL] には、以下の表で説明する変数が含まれている必要があります。リアルタイムデータ転送を設定する前に、[!DNL Audience Manager] UI で必ず[特性を作成](../../../features/traits/create-onboarded-rule-based-traits.md)および[フォルダー構造](../../../features/traits/trait-storage.md#create-trait-storage-folder)を作成してください。

>[!NOTE]
>
>斜体のコンテンツを実際のパラメーター値に置き換えてください。

| パラメーター | 説明 |
|---|---|
| `<KEY>` | キー値ペア内の一意の識別子（例：gender、color、price）。 |
| `<VAL>` | キーによって定義されたデータセットに属する変数（例：gender=male、color=green、price=100） |

### URL 構文

リアルタイム受信データ取り込みプロセスの間、適切な形式の [!DNL URL] 文字列は次の構文に従います。

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
