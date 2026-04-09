---
description: このマップには Audience Manager の主要なシステムが含まれています。Audience Manager コンポーネント内およびコンポーネント間のデータの流れが視覚的に表現されています。
seo-description: This map contains the major Audience Manager systems. It visually represents how data flows into, out of, and among Audience Manager components.
seo-title: Platform Architecture  Data Flow Map
solution: Audience Manager
title: プラットフォームアーキテクチャ データフローマップ
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
TQID: https://experienceleague.adobe.com/AuYZKnavjMq-XyilPWgEeWASzFB3K5HuAqx-wsE-H9k
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 91%

---

# プラットフォームアーキテクチャ：データフローマップ {#platform-architecture-data-flow-map}

このマップには Audience Manager の主要なシステムが含まれています。Audience Manager コンポーネント内およびコンポーネント間のデータの流れが視覚的に表現されています。

## このマップの読み方 {#compmap}

<!-- 

c_compmap.xml

 -->

このマップでは、グレーのボックスに [!DNL Audience Manager] システムが配置されています。完全に内部システムであるコンポーネントもあれば、[!DNL Audience Manager] と外部の境界上に位置するコンポーネントもあります。[!DNL Audience Manager] をご使用のお客様にとって、内部コンポーネントは通常透過的であるか、またはアクセスできません。ただし、ユーザーインターフェイスまたはデータ統合を通してこれらのシステムと関わる場合もあります。ボックスのエッジにあるシステムは、[!DNL Audience Manager] と外部との間でデータの収集および送信をおこないます。

[!DNL Audience Manager] で出し入れされるデータのタイプは色によって定義されます。グリーンはクライアントデータ、ブルーは顧客データ（サイトを訪れる訪問者）、オレンジはレポートに使用されるデータをそれぞれ示します。

システムの説明と概要については、[ アクション ](../../reference/system-components/components-data-action.md)、[ コレクション ](../../reference/system-components/components-data-collection.md)、[処理](../../reference/system-components/components-data-processing.md)、および[ タグ管理](../../reference/system-components/components-tag-management.md)のデータ セクションを参照してください。

![](assets/flowmap.png)
