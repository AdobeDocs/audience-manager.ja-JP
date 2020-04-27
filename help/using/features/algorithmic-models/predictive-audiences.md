---
description: 予測オーディエンスを使用すると、不明なオーディエンスをリアルタイムで別の人物に分類し、データサイエンスを使用できます。
seo-description: 予測オーディエンスを使用すると、不明なオーディエンスをリアルタイムで別の人物に分類し、データサイエンスを使用できます。
seo-title: 予測オーディエンスの概要
solution: Audience Manager
title: オーディエンスマネージャーの予測オーディエンス
translation-type: tm+mt
source-git-commit: 74a5de961b2f9ab6afa2caf998ba1100d40cc93a

---


# 予測オーディエンスの概要 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 高度なデータ科学技術を使用して、未知のオーディエンスをリアルタイムで個別の人物に分類するのに役立ちます。

>[!IMPORTANT]
>この記事には、この機能の設定と使用方法を説明する製品ドキュメントが含まれています。法的なアドバイスは何も含まれません。法律に関するガイダンスについては、御社の顧問弁護士にアドバイスを求めてください。

マーケティングコンテキストで、個人とは、訪問者、ユーザー、または潜在的な購入者が定義したオーディエンスセグメントで、人口統計、閲覧習慣、買い物履歴などの特定の特性を共有します。

[!UICONTROL Predictive Audiences] モデルは、オーディエンスマネージャの機械学習機能を使用して、未知のオーディエンスを別の個人に分類することで、この概念をさらに一歩進めます。 オーディエンスマネージャーは、既知のファーストパーティオーディエンスのセットに対する未知のファーストパーティオーディエンスの傾向を計算することで、これを達成するのに役立ちます。

モデルを作成する [!UICONTROL Predictive Audiences] 場合、最初の手順は、ターゲットオーディエンスを分類する基準特性またはセグメントを選択することです。 これらの特性またはセグメントは、ユーザーの個人を定義します。

評価段階では、ベースラインとして定義した各特性ま [!UICONTROL Predictive Audiences] たはセグメントに対して、モデルによって新しいセグメントが作成されます。 次回、オーディエンスオーディエンスから、（どのベースライン特性またはセグメントにも適用されなかった）個人に分類されていない訪問者が表示された場合、モデルは訪問者が属する予測セグメントを判断し、そのセグメントに訪問者を追加します。 [!UICONTROL Predictive Audiences]

ページ内のモデルによって作成された予測セグメントを識別で [!UICONTROL Segments] きます。 各モデ [!UICONTROL Predictive Audiences] ルはフォルダの下に独自のフォルダを [!UICONTROL Predictive Audiences] 持ち、モデルフォルダをクリックすると各モデルのセグメントを表示できます。

![予測オーディエンスセグメント](assets/predictive-audiences-segments.png)

## ユースケース {#use-cases}

To help you better understand how and when you could use [!UICONTROL Predictive Audiences], here are a few use cases that Audience Manager customers can solve by using this feature.

### ユースケース 1

eコマース会社のマーケティング担当者として、Web訪問者とモバイルアフィニティをすべて様々なブランドカテゴリに分類し、ユーザーエクスペリエンスをパーソナライズできるようにします。

### ユースケース 2

メディア会社のマーケティング担当者として、自分の未認証のWeb訪問者とモバイルチャネルをお気に入りのジャンル別に分類し、すべてのジャンルにわたってパーソナライズされたコンテンツを提案したいと思います。

### ユースケース 3

航空会社の会社の広告主として、短いリターゲティングウィンドウ内でリアルタイムに広告を出せるように、旅行先に対する関心に基づいてオーディエンスを分類するようにします。

### ユースケース 4

広告主として、ファーストパーティオーディエンスをリアルタイムで分類し、ニュースの傾向に素早く対応できるようにしたいと思います。

### ユースケース 5

マーケティング担当者として、Webサイトの訪問者がどの段階にあるか（発見、関与、購入、保持など）を予測し、それに応じて顧客のターゲットを行いたいと思います。

### ユースケース 6

メディア会社として、オーディエンスを分類し、広告スペースをプレミアム価格で販売し、訪問者に関連する広告を提供できるようにしたいと思います。

## 予測オーディエンスモデルの仕組み

モデルを作成する [!UICONTROL Predictive Audiences] ときは、次の3つの手順を実行します。

1. まず、自分の個人を定義する2つ以上の特性または2つのセグメントを選択します。
1. 次に、分類するターゲットオーディエンスを定義する特性またはセグメントを選択します。
1. 最後に、モデルの名前を選択し、予測セグメントを保存するデータソースを選択します。

### 個人の選択基準 {#selection-personas}

任意のファーストパーティの特性またはセグメントを選択して、自分の個人を定義できます。 ただし、最適な結果を得るために、次に推奨されるベストプラクティスを示します。

* 個人の特徴またはセグメントを選択し、各個人のデバイスIDが少なくとも数百個になるよ [うにします](../../reference/ids-in-aam.md)。
* 特性がデバイス間のIDに基づい [ている場合](../../reference/ids-in-aam.md)、などのデバイスIDを使用する [プロファイル結合ルールでセグメント](../profile-merge-rules/merge-rules-overview.md) に含めます [](../../reference/ids-in-aam.md)[!UICONTROL Device Graph]。 これにより、アルゴリズムが学習で [きる十分なデバイス](../../reference/ids-in-aam.md) IDを確保できます。
* 特性を1 ～ 3個まで含む、個人の特性または単純なセグメントを選択することをお勧めします。
* 重なりが最小のベースライン特性またはセグメントを選択します。
* デジタルプロパティ全体で詳細な特性をキャプチャしていることを確認します。

### ターゲットオーディエンス {#selection-audience}

個人オーディエンスと同様に、ターゲットを定義する特性またはセグメントを選択して、適切な個人に分類するための豊富な特性を持つリアルタイムユーザーを作成する必要があります。

### 予測オーディエンスモデルのトレーニング段階 {#model-training}

アルゴリズムでファーストパーティオーディエンスを適切な人物に分類する前に、データに基づいて自分自身をトレーニングする必要があります。

定義した各個人に対して、アルゴリズムはそれぞれのオーディエンスを分析し、過去30日間のユーザーのリアルタイムおよび/またはオンボードの特性アクティビティを評価します。
この手順は、ファーストパーティのオーディエンスの変更を考慮するため、24時間に1回実行されます。

### 予測オーディエンスモデルの分類段階 {#model-classification}

ターゲットオーディエンスの一部である訪問者がリアルタイムで表示されると、モデルは、その訪問者が定義されたパーソナの一部であるかどうかを評価します。 どの訪問者にも属さない訪問者に対して、モデルは個人の資格スコアを割り当てます。

ファーストパーティオーディエンスの評価とスコアの割り当てを行う際に、モデルはアカウントで定義され **[!UICONTROL Profile Merge Rule]** たデフォルトを使用します。 最後に、訪問者は最高得点を得た人物に分類されます。

![予測オーディエンスグラフ](assets/predictive-audiences-graph.png)

## 考慮事項と制限 {#considerations}

>[!IMPORTANT]
> 実装段階に進む前に、この節をよく読んでください。

モデルを設定す [!UICONTROL Predictive Audiences] る際は、次の点に注意してください。

* 最大10個のモデルを作成でき [!UICONTROL Predictive Audiences] ます。
* 各モデルに対して、最大50個の基本特性/セグメントを選択できます。
* では、現在、セカンドパーティデータとサードパーティデータはサポートされていませ [!UICONTROL Predictive Audiences]ん。
* オーディエンスの分類は、リアルタイムのファーストパーティオーディエンスのみです。 オンボードされたファーストパーティオーディエンスの分類は、今後の更新でサポートされる可能性があります。
   >[!IMPORTANT]
   > 現在、予測セグメ [!UICONTROL Total Segment Population] ントのは0と表示され、「アウトバウンドデータのバッ [チ転送」は予測オーディエンスでは](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) サポートされていません。 この動作は、今後の更新で変更されます。
* [!UICONTROL Predictive Audiences] すべてのファーストパーティデータソースから、ファーストパーティの特性に基づいてオーディエンスの分類を実行します。
* のセグメント評価で [!UICONTROL Predictive Audiences] は、アカウントで定 **[!UICONTROL Profile Merge Rule]** 義したデフォルトが使用されます。 詳しくは、専用のドキュメ [!UICONTROL Profile Merge Rules] ントを参照して [ください](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html)。
* 一部の特性とセグメントは、ベースラインまたはターゲットオーディエンスです。 [!UICONTROL Predictive Audiences] 次のいずれかをベースラインまたはベースラインオプションとして選択した場合、モデルの保存に失敗するターゲットオーディエンス:
   * 予測特性を使用して作成された予測特性とセグメント
   * [Adobe Experience Platformの特徴](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) またはセグメント
   * アルゴリズム特性；
   * サードパーティの特性。

## データ書き出しコントロール{#dec}

モデルによって作成された予測セ [!UICONTROL Predictive Audiences] グメントは、次のファ [ーストパーティのデータソースから](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) 、データエクスポートコントロールを継承します。

1. モデルの構築時に選択するファーストパーティデータソース。
1. お使いのターゲットオーディエンスのファーストパーティデータソース 特に、データの書き出しは、データの書き出しを構成する特性やセグメントのターゲットオーディエンス。

新しく作成された予測特性とセグメントには、上で説明したファーストパーティデータソースの和集合と同じプライバシー制限が適用されます。

セグメントのプライバシー制限に含まれない追加の制限を持つ特 [!UICONTROL Predictive Audiences] 徴は、トレーニング段階から除外され、モデルに影響を与えません。

## Role-Based Access Controls{#rbac}

個人およびオーディエンスの分類に対して選択した特性とセグメントは、オーディエンスマネージャーのロールベースの [アクセス制御の対象となりま](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)す。

オーディエンスマネージャーのユーザーは、ターゲットの権限を持つ、パーソナおよびオーディエンスの特性またはセグメントの [みを選択できます](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)。
