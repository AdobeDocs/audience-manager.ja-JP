---
description: キー値ペアに基づいて 1 つまたは複数のシグナルを検索します。
seo-description: キー値ペアに基づいて 1 つまたは複数のシグナルを検索します。
seo-title: キー値ペアによるシグナルの検索
title: キー値ペアによるシグナルの検索
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# キー値ペアによるシグナルの検索 {#search-signals-by-key-value-pairs}

キー値ペアに基づいて 1 つまたは複数のシグナルを検索します。複数のシグナルを検索する場合は、![Add](assets/icon_add.png) ボタンをクリックします。検索するキー値ペアを入力してから、以下のフィルターで検索結果を絞り込みます。

* **Signal Status**：特性に含まれているシグナル、未使用シグナルまたはその両方を検索します。
* **View Records For**：受信シグナルの検索期間を選択します。
* **Minimum Counts**：選択した期間における合計カウント数が指定値以上であるシグナルのみを表示します。

>[!IMPORTANT]
>
>処理時間を短縮するため、キー値ペアによる検索では、データサンプリングに基づいて結果が取得されます。See [Data Sampling and Error Rates](/help/using/reporting/report-sampling.md) for details on how [!DNL Audience Manager] uses data sampling and why slight result variations may appear when comparing key-value search to general searches.

複数のキー値ペアを使用してシグナルを検索する場合、[!DNL Audience Manager] は論理 **AND** 演算子で各ペアを結合します。例として、以下のキー値ペアを指定して検索をおこなうとします。

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

検索結果では、同じ呼び出しに対して 3 つのフィルターすべて（`c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`）を満たすシグナルのみが返されます。

![](assets/signals-search.png)

## 大文字と小文字の無区別および検索条件の自動入力候補 {#case-insensitivity}

キーおよび値の検索フィールドでは、大文字と小文字は区別されません。また、キーの検索フィールドでは自動入力候補が表示されます。

![](assets/signal-search-suggestions.png)

例えば、[!DNL Audience Manager] で以下のシグナルを受信したとします。

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

キー検索フィールドに `product` と入力すると、自動入力候補として `productCategory`、`newProduct`、`PRODUCT` および `product` が表示されます。

同様に、`product == phone` と指定して検索した場合、[!UICONTROL Data Explorer] では `PRODUCT == phone` と `product == PHONE` の両方の結果が返されます。
バックフィルをおこなった特性適合でも、大文字と小文字は区別されません。キー値ペアが `PRODUCT == SMARTPHONE` のシグナルを含む特性は、キー値ペアが `product == smartphone` のシグナルとしても認定されます。