---
description: Audience Manager では、アカウントに作成できる特性、セグメント、宛先、アルゴリズムモデルの数に上限を設定しています。制限は、ユーザーインターフェイスを使用して作成された場合、または API メソッドを使用してプログラムによって作成された場合のどちらに対しても適用されます。使用制限は、アドビの API やユーザーインターフェイへの不正アクセスを試みる可能性がある自動プロセスから Audience Manager を守るのに役立ちます。
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: 使用の制限
keywords: ID マッピング, ID マッピング, cookie マッピング
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
TQID: https://experienceleague.adobe.com/hyvYo82mjW-ZK5zn5nVzeQNavwIYTnd8LsjpNjiHofs
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cbid: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: d12f0729-c5e9-4a4a-bb39-687f9ab4a97cid: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 99%

---

# 使用の制限 {#usage-limits}

Audience Manager では、アカウントに作成できる特性、セグメント、宛先、アルゴリズムモデルの数に上限を設定しています。制限は、ユーザーインターフェイスを使用して作成された場合、または [!DNL API] メソッドを使用してプログラムによって作成された場合のどちらに対しても適用されます。上限を設けることで、[!DNL API] またはユーザーインターフェイスが自動プロセスによって不正利用されることを防ぐことができます。

## ID マッピングの制限 {#id-mapping-limits}

次の表に、デバイス ID の [ID マッピング](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)の上限を示します。ID が以下のいずれかの上限に達すると、Audience Manager は、保存時期が最も古い ID マッピングを削除し新しい ID マッピングを追加する先入れ先出し（FIFO）方式で、新規 ID マッピングを追加します。Audience Manager でサポートされる ID について詳しくは、[Audience Manager の ID インデックス](../../reference/ids-in-aam.md)を参照してください。

| ID マッピング | 上限 |
|-----------|-------------- |
| クロスデバイス ID（[DPUUID](../../reference/ids-in-aam.md)）に対してデバイス広告 ID（[DAID](../../reference/ids-in-aam.md)） | クロスデバイス ID（[DPUUID](../../reference/ids-in-aam.md)）1 個に対してデバイス広告 ID（[DAID](../../reference/ids-in-aam.md)）100 個 |
| デバイス広告 ID（[DAID](../../reference/ids-in-aam.md)）に対してクロスデバイス ID（[DPUUID](../../reference/ids-in-aam.md)） | 各 [DPID](../../reference/ids-in-aam.md) あたり、デバイス広告 ID（[DAID](../../reference/ids-in-aam.md)）1 個に対してクロスデバイス ID（[DPUUID](../../reference/ids-in-aam.md)）10 個 |
| cookie／ブラウザー ID に対して cookie／ブラウザー ID | 1000 cookie／ブラウザー ID に対して 1  cookie／ブラウザー ID |

## 項目の限度 {#item-limits}

以下の表は、各項目タイプの現時点での限度のリストです。いずれかの項目が所定の限度に達すると、新しい特性、セグメント、宛先、[!UICONTROL Algorithmic Models]は作成できなくなります。限度に達した場合、古い項目を削除しないと、新しい項目の作成はできません。

### 特性の限度

| 特性タイプ | 上限 |
| -------------------------- | ------------------------------------- |
| 合計特性 | 100,000 |
| 特性選定の合計数 | 150,000特性選定について詳しくは、[特性選定に関するリファレンス](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)を参照してください。 |
| アルゴリズム | 50 |
| ルールベース | 100,000 |
| オンボード | 100,000 |
| フォルダー特性 | 2,000 |

### セグメントの限度

| セグメントタイプ | 上限 |
| -------------- | ------------- |
| 合計セグメント | 20,000 |

### 宛先の限度

| 宛先のタイプ | 上限 |
| ------------------ | ------------- |
| 宛先合計 | 1,000 |
| Cookie | 1,000 |
| URL | 1,000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### アルゴリズムモデルの限度

| 項目 | 上限 |
| -------- | ----- |
| Active [!UICONTROL Look-Alike Models] | &#x200B;20. Audience Manager は&#x200B;*アクティブ*&#x200B;なアルゴリズムモデルのみを制限としてカウントするようになりました。 |
| [!UICONTROL Look-Alike Models] 最大オーディエンスサイズ | 25,000,000 の限度を引き上げることはできません。オーディエンスのサイズを小さくするには、モデルに対して少ないデータソースを選択するか、短いルックバック期間を選択します。 |
| [!UICONTROL Look-Alike Model] の最大除外特性数  | 500。[アルゴリズムモデリングにおける特性の除外](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)を参照してください。 |
| 最大 [!UICONTROL Predictive Audiences Models] | 10 |
| [!UICONTROL Predictive Audiences Models] の基準となるペルソナの最大数  | 50 |

### フォルダーの限度

| 項目 | 上限 |
| ------------- | ------------------ |
| 特性フォルダー | 2,000。フォルダー構造は最大 5 階層まで可能です。 |

### 派生シグナルの限度

| 項目 | 上限 |
| --------------- | ------------- |
| 派生シグナル | 50,000。 |

### 会社ユーザーアカウントの限度

| 項目 | 上限 |
| ----------- | ------------- |
| 会社のユーザーアカウントの最大数 | 1,000。 |

## 使用状況の監視 {#monitor-usage}

アカウントの使用状況と限度は、**[!UICONTROL Administration > Limits]** で確認できます。アクセスには管理者権限が必要です。

![使用限度の画像](assets/usage-limits.png)

## 項目の限度の引き上げ {#increase-item-limits}

ここで紹介しているデフォルトの限度は、業務上十分な使用量を確保できることを想定したものです。継続的にこの限度に到達してしまう場合は、アカウント担当者と限度の引き上げを検討してください。
