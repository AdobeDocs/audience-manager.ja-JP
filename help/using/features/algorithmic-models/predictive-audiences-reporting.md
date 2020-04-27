---
description: 予測オーディエンスを使用すると、不明なオーディエンスをリアルタイムで別の人物に分類し、データサイエンスを使用できます。
seo-description: 予測オーディエンスを使用すると、不明なオーディエンスをリアルタイムで別の人物に分類し、データサイエンスを使用できます。
seo-title: 予測オーディエンスレポート
solution: Audience Manager
title: オーディエンスマネージャーの予測オーディエンス
translation-type: tm+mt
source-git-commit: 8259f07c91efa0efd88e8f7c87cb1829ffadd77d

---


# 予測オーディエンスレポート

モデルを保存した後、 [!UICONTROL Predictive Audiences] オーディエンスマネージャの開始がトレーニングします。 数時間以内に、計算済みモデルが開始でデータ収集サーバー上のオーディエンス [を分析します](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)。 レポートは翌日に公開されます。

分類の結果を表示するに [!UICONTROL Predictive Audiences] は、/に移動し、 **[!UICONTROL Audience Data]** モデ **[!UICONTROL Models]**&#x200B;ルをリストでクリックします。

左側のフィルタオプションを使用して、モデル名を検索したり、モデルタイプに基づいて結果をフィルタしたりします。

![予測オーディエンスフィルタ](assets/predictive-audiences-filter-models.png)

モデルの表には、次の情報が表示されます。

* **[!UICONTROL ID]**:モデルIDは、Managerアカウント内の各モデルを一意にオーディエンスします。
* **[!UICONTROL Name]**:モデル作成手順で指定した名前
* **[!UICONTROL Description]**:モデル作成手順で指定した説明
* **[!UICONTROL Model Type]**:各モデル(または[!UICONTROL Look-Alike Modeling] )のタ [!UICONTROL Predictive Audiences]イプ
* **[!UICONTROL Status]**:各モデルのステータス：
   * **[!UICONTROL Pending]**:モデルは初期化中で、まもなく結果を出す開始が発生します。
   * **[!UICONTROL Active]**:モデルが正常に実行され、結果が生成されている。
   * **[!UICONTROL Warning]**:データが不十分(基準母集団が少ない、ユーザープロファイルがリッチでないなど)のため、モデルは結果を生成できませんでした。
   * **[!UICONTROL Error]**:モデルの実行に失敗しました。 アドビの担当者にお問い合わせください。

## モデル概要レポート{#model-report}

モデルを選択すると、そのモデルのレポートページが読み込まれます。 ページの上部に、モデルがターゲットオーディエンスを分類した1日のリアルタイム実現に基づく上位5つの予測セグメントが表示されます。 この **[!UICONTROL Other]** カテゴリには、上位5つの最大の予測セグメントに含まれていなかった残りの人が含まれます。

オーディエンスマネージャに、色分けされたドーナツグラフとタイムライングラフの両方が表示されま [!UICONTROL Predictive Audiences]す。

ページの上部にある「個人」タブをクリックすると、グラフやグラフに追加または削除されます。

ドーナツグラフは、ターゲットオーディエンスの個人ベースの分類を示し、グラフは過去6日間の予測セグメントの1日間のリアルタイム訪問者トレンドを示します。

モデルのステータスが、、、ま [!UICONTROL Pending]たはの [!UICONTROL Warning]場合、グ [!UICONTROL Error]ラフの代わりにモデルのステータスが表示されます。

![スマートパーソナレポート](assets/predictive-audiences-report.png)

レポートの表には、各セグメントに関する次の情報が表示さ [!UICONTROL Predictive Audiences] れます。

1. **[!UICONTROL SEGMENT ID]**:各訪問者に関連付けられた、自動作成されたセグメントのセグメントID。
1. **[!UICONTROL NAME]**:個人名
1. **[!UICONTROL STATUS]**:セグメントのステー [!UICONTROL Predictive Audiences] タス：
   * **[!UICONTROL Succeeded]**:ユーザーは、このセグメントに分類されます。
   * **[!UICONTROL Pending]**:セグメントはまだ初期化中です。
   * **[!UICONTROL Insufficient Training Data]**:データが不足しているため、ユーザーはこのセグメントに分類されません。 ベースライン母集団の合計が少なすぎるため、十分なデータが提供されません。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**:過去24時間における各訪問者のセグメントの関連付け数。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**:過去24時間における各訪問者のセグメントの関連付けの割合（モデル母集団全体からの割合）。

## Influential Traits{#influential-traits}

[!UICONTROL Influential Traits] は、アルゴリズムが、 [!UICONTROL Predictive Audiences] その個人の分類を決定する最も強い予測要素であることを発見した特性です。訪問者

特徴の存在が、選択した人物に属するユーザーの尤度を増加(+)するか減少(-)するかを示す符号。

すべての表示の影響を与える特性を選択するには、をクリックしま [!UICONTROL View All Influential Traits]す。

このウ [!UICONTROL Influential Traits] ィンドウには、選択したモデルの各訪問者に関する次の情報が表示されます。

![影響力のある](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**:選択した人物の各影響力のある特性の特性ID。
1. **[!UICONTROL NAME]**:選ばれた人物の各影響力のある特性の名前
1. **[!UICONTROL DESCRIPTION]**:選ばれた人物のそれぞれの影響力のある特性の説明
1. **[!UICONTROL WEIGHT]**:選択した人物の各影響力の重み付け。 [!UICONTROL Influential Traits] は、デフォルトで重み付け順に並べ替えられます。  重み付けの値は、予測力を示します。 符号は、特性の存在が個人に属する可能性を増加させる(+)か減少させる(-)かを示します。
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**:過去30日間の、選択した個人の影響を受ける各特性の固有の特性の関連付けの数です。
