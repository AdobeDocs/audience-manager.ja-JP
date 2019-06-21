---
description: Audience Manager では、アカウントに作成できる特性、セグメント、宛先、アルゴリズムモデルの数に上限を設定しています。制限は、ユーザーインターフェイスを使用して作成された場合、または API メソッドを使用してプログラムによって作成された場合のどちらに対しても適用されます。使用制限は、アドビの API やユーザーインターフェイへの不正アクセスを試みる可能性がある自動プロセスから Audience Manager を守るのに役立ちます。
seo-description: Audience Manager では、アカウントに作成できる特性、セグメント、宛先、アルゴリズムモデルの数に上限を設定しています。制限は、ユーザーインターフェイスを使用して作成された場合、または API メソッドを使用してプログラムによって作成された場合のどちらに対しても適用されます。上限を設けることで、API またはユーザーインターフェイスが自動プロセスによって不正利用されることを防ぐことができます。
seo-title: 使用の制限
solution: Audience Manager
title: 使用の制限
topic: DIL API
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
translation-type: tm+mt
source-git-commit: a9550d71bbc6adf939539df05cd38a9d22ef261b

---


# 使用制限 {#usage-limits}

Audience Manager では、アカウントに作成できる特性、セグメント、宛先、アルゴリズムモデルの数に上限を設定しています。Limits apply to these items whether created in the user interface or programmatically through [!DNL API] methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our [!DNL API]s or user interface.

## ID マッピングの上限 {#id-mapping-limits}

次の表に、デバイス ID の [ID マッピング](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)の上限を示します。Once an ID reaches any of the limits below, Audience Manager adds new ID mappings based on a [!DNL FIFO] (first in, first out) logic, by removing the oldest stored ID mapping, and adds the new one. Audience Manager でサポートされる ID について詳しくは、[Audience Manager の ID インデックス](../../reference/ids-in-aam.md)を参照してください。

| ID マッピング | 上限 |
|-----------|-------------- |
| デバイス広告ID（DID）へのデバイス広告ID（CRM ID） | 100デバイス広告ID（大文字）から1クロスデバイスID（CRM ID） |
| デバイスID（CRM ID）からデバイス広告ID（DID）への変換 | 10デバイスID（CRM ID）から1デバイス広告ID（DID）への変換 |
| Cookie/ブラウザーIDへのcookie/ブラウザーID | 1000Cookie/ブラウザーID1cookie/ブラウザーID |

## 項目の限度 {#item-limits}

以下の表は、各項目タイプの現時点での限度のリストです。You cannot create new traits, segments, destinations, or [!UICONTROL Algorithmic Models] if you reach a specific limit for one of these items. 限度に達した場合、古い項目を削除しないと、新しい項目の作成はできません。

### 特性の限度

| 特性タイプ | 上限 |
| -------------------------- | ------------------------------------- |
| 合計特性 | 100,000 |
| 合計特性認定 | 150,000. For more information on trait qualification, see Trait Qualification Limit in [Trait Qualifications Reference](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit). |
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
| アクティブなアルゴリズムモデル | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| アルゴリズムモデルの最大オーディエンスサイズ | 25,000,000.この制限は増やすことはできません。オーディエンスのサイズを小さくするには、モデルに対して少ないデータソースを選択するか、短いルックバック期間を選択します。 |
| モデルの最大除外特性数 | 500. See [Trait Exclusion in Algorithmic Modeling](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

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

You can see usage and limits for your account by going to **[!UICONTROL Administration > Limits]**. アクセスには管理者権限が必要です。

![使用制限画像](assets/usage-limits.png)

## 項目の限度の引き上げ {#increase-item-limits}

ここで紹介しているデフォルトの限度は、業務上十分な使用量を確保できることを想定したものです。継続的にこの限度に到達してしまう場合は、アカウント担当者と限度の引き上げを検討してください。