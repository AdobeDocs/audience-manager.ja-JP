---
description: Predictive Audiences は、データサイエンスを使用して、リアルタイムに不明なオーディエンスを個別のペルソナに分類するのに役立ちます。
seo-description: Predictive Audiences は、データサイエンスを使用して、リアルタイムに不明なオーディエンスを個別のペルソナに分類するのに役立ちます。
seo-title: Predictive Audiences レポート
solution: Audience Manager
title: Predictive Audiences レポート
feature: アルゴリズムモデル
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 100%

---

# Predictive Audiences レポート

[!UICONTROL Predictive Audiences] モデルを保存すると、Audience Manager はモデルのトレーニングを開始します。2 ～ 3 時間以内に、計算済みのモデルが[データ収集サーバー](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)上のオーディエンスの分析を開始します。レポートは、翌日に使用できるようになります。

[!UICONTROL Predictive Audiences] 分類の結果を確認するには、**[!UICONTROL Audience Data]**／**[!UICONTROL Models]** に移動して、リストのモデルをクリックします。

左側にあるフィルタリングオプションを使用して、モデル名を検索したり、モデルのタイプに基づいて結果をフィルタリングしたりします。

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

モデルの表には次の情報が表示されます。

* **[!UICONTROL ID]**：Audience Manager アカウントで各モデルを一意に識別するモデル ID。
* **[!UICONTROL Name]**：モデル作成ステップで指定した名前。
* **[!UICONTROL Description]**：モデル作成ステップで指定した説明。
* **[!UICONTROL Model Type]**：各モデルのタイプ（[!UICONTROL Look-Alike Modeling] または [!UICONTROL Predictive Audiences]）。
* **[!UICONTROL Status]**：各モデルのステータス。
   * **[!UICONTROL Pending]**：モデルは初期化中で、まもなく結果の生成が始まります。
   * **[!UICONTROL Active]**：モデルは正常に実行中で、結果を生成しています。
   * **[!UICONTROL Warning]**：データが不十分なので（つまり、ベースライン母集団が少なく、ユーザープロファイルがリッチでないので）、モデルが結果の生成に失敗しました。
   * **[!UICONTROL Error]**：モデルが実行に失敗しました。アドビの担当者に問い合わせる必要があります。

## モデルの概要レポート {#model-report}

モデルを選択したら、そのレポートページが読み込まれます。ページの上部に、1 日のリアルタイム適合に基づいて、モデルがターゲットオーディエンスを分類した、上位 5 件の予測セグメント（規模の大きい順）が表示されます。**[!UICONTROL Other]** カテゴリには、上位 5 件の予測セグメントに含まれない、残りのペルソナが含まれます。

Audience Manager には、[!UICONTROL Predictive Audiences] に関する色分けされたドーナツグラフとタイムライングラフの両方が表示されます。

ページの上部にあるペルソナのタブをクリックすることで、ドーナツグラフとタイムライングラフに追加／削除されます。

ドーナツグラフには、ターゲットオーディエンスのペルソナベースの分類が表示されるのに対して、タイムライングラフには、予測セグメントの 1 日のリアルタイム母集団トレンドが過去 6 日間にわたって表示されます。

モデルステータスが [!UICONTROL Pending]、[!UICONTROL Warning] または [!UICONTROL Error] の場合、グラフの代わりにモデルステータスが表示されます。

![smart-persona-report](assets/predictive-audiences-report.png)

レポートの表には、各 [!UICONTROL Predictive Audiences] セグメントに関する次の情報が表示されます。

1. **[!UICONTROL SEGMENT ID]**：各ペルソナに関連付けられた、自動作成されたセグメントのセグメント ID。
1. **[!UICONTROL NAME]**：ペルソナ名。
1. **[!UICONTROL STATUS]**：[!UICONTROL Predictive Audiences] セグメントのステータス。
   * **[!UICONTROL Succeeded]**：ユーザーはこのセグメントに分類されています。
   * **[!UICONTROL Pending]**：セグメントはまだ初期化中です。
   * **[!UICONTROL Insufficient Training Data]**：データが不十分なので、ユーザーはこのセグメントに分類されていません。合計ベースライン母集団が少なすぎて、学習するのに十分なデータを提供できません。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**：過去 24 時間のペルソナごとのセグメントの適合数。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**：合計モデル母集団に対する、過去 24 時間のペルソナごとのセグメントの適合率。

## Influential Traits {#influential-traits}

[!UICONTROL Influential Traits] は、訪問者のペルソナ分類を決定するための最も強力な予測因子となる、[!UICONTROL Predictive Audiences] アルゴリズムが検出した特性です。

記号は、特性の存在によって、選択したペルソナにユーザーが属する可能性が増加する（+）か減少する（-）かを示します。

ペルソナのすべての Influential Traits を表示するには、[!UICONTROL View All Influential Traits] をクリックします。

[!UICONTROL Influential Traits] ウィンドウには、選択したモデルのペルソナごとに、次の情報が表示されます。

![influential-traits](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**：選択したペルソナの各 Influential Traits の特性 ID。
1. **[!UICONTROL NAME]**：選択したペルソナの各 Influential Traits の名前。
1. **[!UICONTROL DESCRIPTION]**：選択したペルソナの各 Influential Traits の説明。
1. **[!UICONTROL WEIGHT]**：選択したペルソナの各 Influential Traits の重み。[!UICONTROL Influential Traits] は、デフォルトでは、重み（降順）で並べ替えられます。重みの値は、その予測力を示します。記号は、特性の存在によって、ペルソナに属する可能性が増加する（+）か減少する（-）かを示します。
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**：過去 30 日間の選択したペルソナに対する Influential Traits ごとのユニークな特性の適合数。
