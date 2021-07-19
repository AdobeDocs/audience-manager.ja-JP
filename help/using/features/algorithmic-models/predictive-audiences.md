---
description: Predictive Audiences は、データサイエンスを使用して、リアルタイムに不明なオーディエンスを個別のペルソナに分類するのに役立ちます。
seo-description: Predictive Audiences は、データサイエンスを使用して、リアルタイムに不明なオーディエンスを個別のペルソナに分類するのに役立ちます。
seo-title: Predictive Audiences の概要
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: アルゴリズムモデル
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 100%

---

# [!UICONTROL Predictive Audiences] 概要 {#predictive-audiences}

[!UICONTROL Predictive Audiences] は、高度なデータサイエンス技法を使用して、リアルタイムに不明なオーディエンスを個別のペルソナに分類するのに役立ちます。

>[!IMPORTANT]
>この記事には、この機能の設定と使用方法を説明する製品ドキュメントが含まれています。法的なアドバイスは何も含まれません。法律に関するガイダンスについては、御社の顧問弁護士にアドバイスを求めてください。

マーケティングにおいて、ペルソナとは、人口統計、閲覧傾向、買い物履歴など、特定の特性のセットを共有する、訪問者、ユーザーまたは見込み客別に定義されたオーディエンスセグメントです。

[!UICONTROL Predictive Audiences] モデルは、この概念をさらに一歩進めて、Audience Manager の機械学習機能を使用して不明なオーディエンスを個別のペルソナに分類できるようにします。Audience Manager は、既知のファーストパーティオーディエンスのセットに関する不明なファーストパーティオーディエンスの傾向を計算することで、これを実現します。

[!UICONTROL Predictive Audiences] モデルを作成する場合、最初のステップは、ターゲットオーディエンスを分類するためのベースライン特性またはセグメントを選択することです。これらの特性またはセグメントは、ペルソナを定義します。

評価フェーズの間、モデルは、ベースラインとして定義した特性またはセグメントごとに新しい [!UICONTROL Predictive Audiences] セグメントを作成します。次回 Audience Manager がペルソナに分類されていない（どのベースライン特性またはセグメントの条件も満たさなかった）ターゲットオーディエンスの訪問者を確認したら、[!UICONTROL Predictive Audiences] モデルは、その訪問者が属する予測セグメントを決定して、訪問者をそのセグメントに追加します。

[!UICONTROL Segments] ページで、モデルによって作成された予測セグメントを識別できます。各 [!UICONTROL Predictive Audiences] モデルには、[!UICONTROL Predictive Audiences] フォルダーの下に独自のフォルダーがあり、モデルフォルダーをクリックすることで、各モデルのセグメントを確認できます。

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## ユースケース {#use-cases}

[!UICONTROL Predictive Audiences] をいつどのように使用できるかを理解しやすくするために、Audience Manager のお客様がこの機能を使用して解決できる、いくつかのユースケースを次に示します。

### ユースケース 1

e コマース会社のマーケティング担当者の場合、ユーザーエクスペリエンスをパーソナライズできるように、すべての Web およびモバイル訪問者を様々なブランド志向カテゴリに分類したい。

### ユースケース 2

メディア会社のマーケティング担当者の場合、すべてのチャネルにわたってパーソナライズされたコンテンツを提案できるように、未認証の Web およびモバイル訪問者を好きなジャンルごとに分類したい。

### ユースケース 3

航空会社向けの広告主の場合、短いリターゲティング期間内にリアルタイムに広告を提示できるように、旅行先への関心に基づいてオーディエンスを確実に分類したい。

### ユースケース 4

広告主の場合、トレンドニュースにすばやく反応できるように、リアルタイムにファーストパーティオーディエンスを分類したい。

### ユースケース 5

マーケティング担当者の場合、フェーズに応じてターゲティングできるように、Web サイト訪問者がいるカスタマージャーニーフェーズ（ディスカバリー、エンゲージメント、購入、定着など）を予測したい。

### ユースケース 6

メディア会社の場合、訪問者に関連性のある広告を提供すると同時に、広告スペースをプレミアム価格で販売できるように、オーディエンスを分類したい。

## [!UICONTROL Predictive Audiences] モデルの動作  {#how-predictive-audiences-models-work}

[!UICONTROL Predictive Audiences] モデルを作成する場合、次の 3 つの手順を実行します。

1. 最初に、最低でもペルソナを定義する 2 つの特性または 2 つのセグメントを選択します。
1. 次に、分類したいターゲットオーディエンスを定義する特性またはセグメントを選択します。
1. 最後に、モデルの名前、予測セグメントを保存するデータソース、およびモデルの[!UICONTROL Profile Merge Rule]を選択します。

### ペルソナの選択条件 {#selection-personas}

ペルソナを定義するための任意のファーストパーティ特性またはセグメントを選択できます。ただし、最適な結果を得るには、次に示すベストプラクティスに従ってください。

* 各ペルソナが少なくとも数百の[デバイス ID](../../reference/ids-in-aam.md) を含むようにペルソナの特性またはセグメントを選択します。
* 特性が[クロスデバイス ID](../../reference/ids-in-aam.md) に基づいている場合、[!UICONTROL Device Graph] のように、[デバイス ID](../../reference/ids-in-aam.md) を使用する[プロファイル結合ルール](../profile-merge-rules/merge-rules-overview.md)で特性をセグメントにラップできます。これにより、アルゴリズムが学習するのに十分な[デバイス ID](../../reference/ids-in-aam.md) が確保されます。
* ペルソナ用に特性またはシンプルなセグメント（1 ～ 3 個の特性で構成）を選択することをお勧めします。
* 重複が最小のベースライン特性またはセグメントを選択します。
* デジタルプロパティをまたいで詳細な特性をキャプチャしていることを確認します。

### ターゲットオーディエンスの選択条件 {#selection-audience}

ユースケースに応じて、ユーザーをリアルタイム、バッチまたはその両方のどれで分類するかに応じて、リアルタイム母数または合計母数が大きなターゲットオーディエンス（[!UICONTROL trait]または[!UICONTROL segment]）を選択します。ペルソナの選択と同様に、ターゲットのオーディエンス[!UICONTROL trait]を使用するか、豊富なプロファイル（[!UICONTROL traits]の豊富なセット）を持つ[!UICONTROL segment]を使用することをお勧めします。

ターゲットオーディエンスを選択する場合は、ユースケースを分析し、分類する ID のタイプ（[!UICONTROL device IDs]または[!UICONTROL cross-device IDs]）を選択します。モデルの作成時に選択した[!UICONTROL Profile Merge Rule]によって、各ユーザーを予測[!UICONTROL segments]に配置するために使用されるデータが定義されます。

ベストプラクティスとして、ターゲットオーディエンス[!UICONTROL Profile Merge Rule]と同じ設定 の[!UICONTROL Profile Merge Rule]を選択するか、ターゲットオーディエンスのプロファイルタイプ（デバイスプロファイルまたは認証済みプロファイル）を含むものを選択することをお勧めします。

### [!UICONTROL Predictive Audiences] モデルトレーニングフェーズ {#model-training}

アルゴリズムがファーストパーティオーディエンスを適切なペルソナに分類できるようにするには、事前にお客様のデータでアルゴリズム自体をトレーニングする必要があります。

アルゴリズムは、定義するペルソナごとに各オーディエンスを分析し、過去 30 日間のユーザーのリアルタイムの特性アクティビティやオンボーディングされた特性アクティビティを評価します。この手順は、ファーストパーティオーディエンスの変更を考慮して、24 時間ごとに実行されます。

### [!UICONTROL Predictive Audiences] モデル分類フェーズ {#model-classification}

リアルタイムおよびバッチでのオーディエンス分類の場合、モデルはまず、ユーザーがターゲットオーディエンスに属しているかどうかを確認します。ユーザーがターゲットオーディエンスに適合し、どのペルソナにも属していない場合、モデルは、そのユーザーにペルソナ認定スコアを割り当てます。

ファーストパーティオーディエンスを評価してスコアを割り当てると同時に、モデルはお客様のアカウントに定義されたデフォルトの **[!UICONTROL Profile Merge Rule]** を使用します。最後に、訪問者が最も高いスコアを獲得したペルソナに分類されます。

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## 考慮事項と制限 {#considerations}

>[!IMPORTANT]
> 実装フェーズに進む前に、この節をよくお読みください。

[!UICONTROL Predictive Audiences] モデルを設定する場合、次の考慮事項および制限に注意してください。

* 最大 10 個の [!UICONTROL Predictive Audiences] モデルを作成できます。
* 各モデルについて、最大 50 個のベース特性／セグメントを選択できます。
* セカンドおよびサードパーティデータは、現在、[!UICONTROL Predictive Audiences] でサポートされていません。
* [!UICONTROL Predictive Audiences] は、すべてのファーストパーティデータソースからのファーストパーティ特性に基づいて、オーディエンスの分類を実行します。
* [!UICONTROL Predictive Audiences]のセグメント評価では、モデル作成時に選択した&#x200B;**[!UICONTROL Profile Merge Rule]**&#x200B;が使用されます。[!UICONTROL Profile Merge Rules] について詳しくは、該当する[ドキュメント](../profile-merge-rules/merge-rules-overview.md)を参照してください。
* 一部の特性およびセグメントは、ベースラインオーディエンスまたはターゲットオーディエンスとしてサポートされません。[!UICONTROL Predictive Audiences] モデルは、次のいずれかをベースラインオーディエンスまたはターゲットオーディエンスとして選択すると、保存に失敗します。
   * 予測特性および予測特性を使用して作成されたセグメント
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) の特性またはセグメント
   * アルゴリズム特性
   * セカンドおよびサードパーティ特性
* [!UICONTROL Predictive Audience] [!UICONTROL segments] を[!UICONTROL Audience Lab] で使用することはできません。

## [!UICONTROL Data Export Controls] {#dec}

[!UICONTROL Predictive Audiences] モデルで作成された予測セグメントは、次のファーストパーティデータソースから[データ書き出しコントロール](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/features/data-export-controls.html)を継承します。

1. モデルを構築する際に選択するファーストパーティデータソース。
1. ターゲットオーディエンスのファーストパーティデータソース。特に、ターゲットオーディエンスを構成する[!UICONTROL traits]または[!UICONTROL segments]のデータ書き出しコントロール。
1. モデルに対して選択した[!UICONTROL Profile Merge Rule]の[データ書き出しコントロール](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)。

新しく作成した予測[!UICONTROL traits]および[!UICONTROL segments]には、前述のファーストパーティデータソースと同じプライバシー制限が課されます。

[!UICONTROL Predictive Audiences] セグメントのプライバシー制限に含まれない追加の制限を持つ特性は、トレーニングフェーズから除外され、モデルに対して影響力を持つことはありません。

## [!UICONTROL Profile Merge Rules] {#pmr}

すべての予測セグメントに、モデルの作成時に選択した[!UICONTROL Profile Merge Rule]が割り当てられます。次の理由により、選択した[!UICONTROL Profile Merge Rule]は重要です。

* ユーザーを予測[!UICONTROL segment]に分類する際には、[!UICONTROL traits]の影響力を分析するときに、どのデバイスや認証済みプロファイルを考慮に入れるかを定義します。
* モデルトレーニング手順で使用し、影響力のある [!UICONTROL trait] タイプとして表示される[!UICONTROL traits]タイプ（デバイスレベルまたはデバイス間レベル）を管理します。予測[!UICONTROL segments]は、ターゲットオーディエンスのサブセットです。
   * ターゲットオーディエンスがセグメントの場合は、ターゲットオーディエンスに割り当てられたものと同じ[!UICONTROL Profile Merge Rule]をモデルに選択するか、ターゲットオーディエンスのプロファイルタイプを含む[!UICONTROL Profile Merge Rule]を選択することをお勧めします。
   * ターゲットオーディエンスが[!UICONTROL trait]の場合は、ターゲットオーディエンス特性と同じタイプのデータにアクセスできる[!UICONTROL Profile Merge Rule]（デバイスプロファイルデータまたはクロスデバイスプロファイルデータのいずれか）を選択することをお勧めします。
* [!UICONTROL Current Authenticated Profiles]および[!UICONTROL No Device Profile]オプションを使用する[!UICONTROL Profile Merge Rules]は、リアルタイムオーディエンスの分類に対してのみサポートされます。詳しくは、[定義済みのプロファイル結合ポリシーのオプション](../profile-merge-rules/merge-rule-definitions.md)を参照してください。

デバイスデータとクロスデバイスデータ  の両方を使用する[!UICONTROL Profile Merge Rule]を選択すると、モデルトレーニングや予測[!UICONTROL segments]へのユーザー分類に使用できる[!UICONTROL traits]の数が最大になります。

## [!UICONTROL Role-Based Access Controls] {#rbac}

ペルソナおよびオーディエンスの分類用に選択する特性およびセグメントは、Audience Manager の[ロールベースのアクセス制御](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/features/administration/administration-overview.html)の影響を受けます。

Audience Manager ユーザーは、[表示権限](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)を持つペルソナおよびターゲットオーディエンス用の特性またはセグメントのみ選択できます。
