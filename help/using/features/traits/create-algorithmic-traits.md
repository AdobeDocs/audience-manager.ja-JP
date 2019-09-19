---
description: アルゴリズム特性の作成プロセスに特有のセットアップ手順や機能について説明します。
seo-description: アルゴリズム特性の作成プロセスに特有のセットアップ手順や機能について説明します。
seo-title: アルゴリズム特性の作成
solution: Audience Manager
title: アルゴリズム特性の作成
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# アルゴリズム特性の作成 {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

アルゴリズム特性を作成するには、「[!UICONTROL Traits]」に移動して、以下の手順に従ってください。

1. 「**[!UICONTROL Create New Trait]**」をクリックして、ドロップダウンメニューから「**[!UICONTROL Algorithmic]**」を選択します。
1. 「[Basic Information](../../features/traits/create-onboarded-rule-based-traits.md)」セクションで、以下の操作をおこないます。
   * 特性の名前を設定します。
   * データソースを選択します。
   * 保存フォルダーを選択します。
1. 「[!UICONTROL Configuration]」パネルを展開し、「**[!UICONTROL Browse All Models]**」をクリックします。新しいウィンドウが開き、特性で使用するモデルを選択できるようになります。
1. モデルを選択して、「**[!UICONTROL Add Selected Model to Trait]**」をクリックします。モデルを追加すると、リーチと精度の設定が表示されます。
1. リーチと精度を目標として選択し、それぞれのドロップダウンメニューから値を選択します。終了したら、「**[!UICONTROL Save]**」をクリックします。

>[!MORE_LIKE_THIS]
>
>* [精度とリーチ](../../features/traits/trait-accuracy-reach.md)


## アルゴリズム特性{#configure-settings}の設定 

[!UICONTROL Trait Builder]の「[!UICONTROL Configuration]」セクションを使用すると、アルゴリズムモデルを特性に関連付けることができます。アルゴリズム特性の作成プロセスを完了するには、モデルを選択し、リーチまたは精度の目標を選びます。

### 前提条件

<!-- r_algo_trait_config_section.xml -->

* [アルゴリズムモデルを作成する](../../features/algorithmic-models/create-model.md#build-model)。
* モデルデータの実行が完了したことを知らせる通知電子メールを受け取る。
* 必須フィールドを「[Basic Information](../../features/traits/create-onboarded-rule-based-traits.md)」セクションに入力する。

### 構成フィールドと設定

| インターフェイス要素 | 説明 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | 「**[!UICONTROL Update]**」ボタンをクリックして、モデルウィンドウを開きます。このウィンドウで、特性の作成に使用するアルゴリズムモデルを選択します。 |
| **[!UICONTROL Select Goal Accuracy]** | 精度に基づいて特性を作成する場合にこのオプションを選択します。精度は、潜在的なユーザーがベースラインにどれだけ近いかを示すスコア値です。精度の範囲は 0（最も低い精度）から 1（最も高い精度）の間となります。 |
| **[!UICONTROL Reach and Accuracy Data Columns]** | このセクションは右側にあり、モデルの精度とリーチ値を表す数値データを最大 21 行表示します。 |
| **[!UICONTROL Reach and Accuracy Slider]** | このスライダーはグラフの下にあり、リーチや精度の目標を示す数値を設定できます。スライダーを設定してから、リーチまたは精度目標ボタンを選択し、特性を作成します。 |

>[!MORE_LIKE_THIS]
>
>* [精度とリーチ](../../features/traits/trait-accuracy-reach.md)