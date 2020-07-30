---
description: Audience Manager では、アカウントに作成できる特性、セグメント、宛先、アルゴリズムモデルの数に上限を設定しています。制限は、ユーザーインターフェイスを使用して作成された場合、または API メソッドを使用してプログラムによって作成された場合のどちらに対しても適用されます。使用制限は、アドビの API やユーザーインターフェイへの不正アクセスを試みる可能性がある自動プロセスから Audience Manager を守るのに役立ちます。
seo-description: Audience Manager では、アカウントに作成できる特性、セグメント、宛先、アルゴリズムモデルの数に上限を設定しています。制限は、ユーザーインターフェイスを使用して作成された場合、または API メソッドを使用してプログラムによって作成された場合のどちらに対しても適用されます。使用制限は、アドビの API やユーザーインターフェイへの不正アクセスを試みる可能性がある自動プロセスから Audience Manager を守るのに役立ちます。
seo-title: 使用の制限
solution: Audience Manager
title: 使用の制限
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: 7d2f4b45ac3e45c9b4fcaffa4b5c5324ff03e683
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 95%

---


# 使用の制限 {#usage-limits}

Audience Manager では、アカウントに作成できる特性、セグメント、宛先、アルゴリズムモデルの数に上限を設定しています。制限は、ユーザーインターフェイスを使用して作成された場合、または [!DNL API] メソッドを使用してプログラムによって作成された場合のどちらに対しても適用されます。上限を設けることで、[!DNL API] またはユーザーインターフェイスが自動プロセスによって不正利用されることを防ぐことができます。

## ID マッピングの上限 {#id-mapping-limits}

次の表に、デバイス ID の [ID マッピング](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)の上限を示します。ID が以下のいずれかの上限に達すると、Audience Manager は、保存時期が最も古い ID マッピングを削除し新しい ID マッピングを追加する先入れ先出し（[!DNL FIFO]）方式で、新規 ID マッピングを追加します。Audience Manager でサポートされる ID について詳しくは、[Audience Manager の ID インデックス](../../reference/ids-in-aam.md)を参照してください。

| ID マッピング | 上限 |
|-----------|-------------- |
| クロスデバイス ID（[DPUUID](../../reference/ids-in-aam.md)）に対してデバイス広告 ID（[DAID](../../reference/ids-in-aam.md)） | クロスデバイス ID（[DPUUID](../../reference/ids-in-aam.md)） 1 個に対してデバイス広告 ID（[DAID](../../reference/ids-in-aam.md)） 100 個 |
| デバイス広告 ID（[DAID](../../reference/ids-in-aam.md)）に対してクロスデバイス ID（[DPUUID](../../reference/ids-in-aam.md)） | 各 [DPID](../../reference/ids-in-aam.md) あたり、デバイス広告 ID（[DAID](../../reference/ids-in-aam.md)） 1 個に対してクロスデバイス ID（[DPUUID](../../reference/ids-in-aam.md)） 10 個 |
| cookie／ブラウザー ID に対して cookie／ブラウザー ID | 1000 cookie／ブラウザー ID に対して 1  cookie／ブラウザー ID |

## 項目の限度 {#item-limits}

以下の表は、各項目タイプの現時点での限度のリストです。いずれかの項目が所定の限度に達すると、新しい特性、セグメント、宛先、[!UICONTROL Algorithmic Models]は作成できなくなります。限度に達した場合、古い項目を削除しないと、新しい項目の作成はできません。

### 特性の限度

| 特性タイプ | 上限 |
| -------------------------- | ------------------------------------- |
| 合計特性 | 100,000 |
| 特性認定の合計数 | 150,000特性認定について詳しくは、[特性認定に関するリファレンス](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)を参照してください。 |
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
| Active [!UICONTROL Look-Alike Models] | 20. Audience Manager は&#x200B;*アクティブ*&#x200B;なアルゴリズムモデルのみを制限としてカウントするようになりました。 |
| [!UICONTROL Look-Alike Models] 最大オーディエンスサイズ | 25,000,000  の限度を引き上げることはできません。オーディエンスのサイズを小さくするには、モデルに対して少ないデータソースを選択するか、短いルックバック期間を選択します。 |
| Maximum number of excluded traits for a [!UICONTROL Look-Alike Model] | 500. See [Trait Exclusion in Algorithmic Modeling](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| ナキシム [!UICONTROL Predictive Audiences Models] | 10 |
| 基準となる人の最大数 [!UICONTROL Predictive Audiences Models] | 50 |

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