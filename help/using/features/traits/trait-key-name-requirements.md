---
description: ここでは、キー値ペアのキー変数で使用される命名規則について説明します。
seo-description: ここでは、キー値ペアのキー変数で使用される命名規則について説明します。
seo-title: キー変数名の要件
solution: Audience Manager
title: キー変数名の要件
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: 特性
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 100%

---

# キー変数名の要件 {#name-requirements-for-key-variables}

ここでは、キー値ペアのキー変数で使用される命名規則について説明します。

## キー名の要件

<!-- c_tb_key_name_requirements.xml -->

[!UICONTROL Expression Builder]では、キー値ペアのキー変数の名前は、任意の桁の数字に続いて 1 つ以上の文字、ダッシュ、アンダースコアおよび追加の数字で構成できます。

* 有効なキー名：`price123`、`123price`、`price-123`、`c_price123`。

* 無効なキー名：`123`、`price!123`。

## キー変数の _ プレフィックス`c_`

`c_` プレフィックスは、イベント呼び出し URL でデータを送信するパラメーターがその構文を使用している場合は、*常に*&#x200B;必要です。
