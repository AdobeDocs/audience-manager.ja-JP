---
description: 特性レコメンデーションを利用すると、セグメントビルダーでセグメントを作成または編集する際に、セグメントルール内の特性に類似した他の特性についてのレコメンデーションが得られます。推奨特性をセグメントに追加すると、ターゲットオーディエンスを増やすことができます。
seo-description: セグメントの作成時に有効な特性レコメンデーションを取得します。
seo-title: 特性レコメンデーション
solution: Audience Manager
title: 特性レコメンデーション
uuid: null
translation-type: tm+mt
source-git-commit: e369038fbc83e28d10da24060699488faf783511

---


# 特性レコメンデーション

セグメントの作成時に有効な特性レコメンデーションを取得します。

## 概要

[!UICONTROL Trait Recommendations]がpowered by [!DNL Adobe Sensei]， powered by， data perience into your Audience Manager Day- to- day workflow.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. 推奨特性をセグメントに追加すると、ターゲットオーディエンスを増やすことができます。

![特性レコメンデーションの概要](assets/trait-recommendations-overview.png)

**要約すると、以下のような機能です。**

* Audience Manager では、現在購読しているデータフィードのファーストパーティ特性とサードパーティ特性が、推奨特性として表示されます。
* Audience Managerでは、セグメントルール内の最大50個の特徴が表示されています。
* レコメンデーションを表示する必要のないデータソースは除外できます。
* 類似性を計算する際、Audience Manager は過去 30 日間の特性の対象として認定できる [UUID](../../reference/ids-in-aam.md) を考慮に入れます。
* 「No similar traits found.Trait(s) may be too new」というエラーメッセージが表示された場合は、過去 30 日間にその特性に関するアクティビティが発生していないか、Audience Manager がその特性のレコメンデーションをまだ更新していません。24 時間後にもう一度試してみてください。

## ユースケース

With [!UICONTROL Trait Recommendations], you can improve your workflows, depending on how you use Audience Manager:

* マーケティング担当者は、類似した特性のヘルプを使用して、補完的な製品に関心のあるオーディエンスをすばやく見つけることができ、リーチを増やすことができます。
* If you use Audience Manager as a publisher, with [!UICONTROL Trait Recommendations], you can understand audience behavior and build better segments for ad sales or user acquisition.

## 特性レコメンデーションとアルゴリズムモデルの違い

### アルゴリズムモデル

[!UICONTROL Algorithmic Models] では、影響力のある特性だけでなく、それらの特性に基づいてユーザーをスコアし、各ユーザーに個々のスコアを割り当てます。次に、アルゴリズムの特性を作成してユーザーをターゲットにします。With accuracy and reach controls in the [!UICONTROL Trait Builder], you can specify which users amongst all those who have the influential traits you want to target.

[!UICONTROL Algorithmic Models] を使用すると、様々な精度レベルでユーザーを選択し、ユーザーのグループ [!UICONTROL Audience Lab] のコンバージョン率をテストできます。See the detailed use case in [Compare Models in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], the model runs every 8 days and refreshes the users qualified for algorithmic traits.

### 特性レコメンデーション

[!UICONTROL Trait Recommendations] を使用すると、セグメントで使用している他の特性に類似したインサイトを得ることができます。

You should use [!UICONTROL Trait Recommendations] when:

* セグメントの作成中に、すばやくインサイトを設定する必要があります。
* 短時間キャンペーンでセグメントを使用しているか、コンバージョンしたオーディエンスをすばやく抑制したい場合、
* リーチを最大化しようとしています。

## ワークフロー

[セグメントビルダー](segment-builder.md)でセグメントを作成または編集する際に、セグメントルール内の特性に類似した特性を調べることができます。セグメントビルダーのワークフローは、以下に示すように、新規セグメントと既存セグメントで非常によく似ています。

### 新規セグメント

1. **Audience Data／Segments** で、「**Add New**」を選択します。
1. 「**Traits**」ドロップダウンボックスで、少なくとも 1 つの特性をセグメントルールに追加します。
1. これで、セグメントルールに追加した特性に類似した推奨特性が表示されるようになりました。下にスクロールして、推奨されるすべての特性を表示します。
1. （オプション）特定のデータソースの推奨特性を除外するには、除外するデータソースの **X** 記号をクリックします。
   > [!NOTE]
   > 
   >除外したデータソースは、推奨特性のリストのすぐ上に表示されます。灰色のボックスの **X** を押すと、除外したデータソースが削除され、各データソースの結果が再度表示されます。
1. セグメントルールに推奨特性を追加するには、**+** 記号をクリックします。

### 既存セグメント

1. Go to **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, select the segment you want to edit and press ![Edit](assets/edit-button.png).
1. Scroll down to the [!UICONTROL Traits] drop-down box.
1. セグメントルールに既に含まれている特性に類似した推奨特性が表示されています。下にスクロールして、推奨されるすべての特性を表示します。
1. （オプション）特定のデータソースの推奨特性を除外するには、除外するデータソースの **X** 記号をクリックします。
   > [!NOTE]
   > 
   >除外したデータソースは、推奨特性のリストのすぐ上に表示されます。灰色のボックスの **X** を押すと、除外したデータソースが削除され、各データソースの結果が再度表示されます。
1. セグメントルールに推奨特性を追加するには、**+** 記号をクリックします。

セグメントを作成または編集し、セグメントルールに特性を追加する場合、追加したものと同様に、最大50個の推奨特性が表示されます。セグメントルールに複数の特徴が含まれている場合、Audience Managerではラウンドロビン方式を使用して、セグメントルール内の母集団ごとの最大50の特性について、各特性に最適な一致を示すラウンドロビン方式を使用します。

![3 つのベース特性](assets/three-base-traits.png)

例えば、セグメントルール内に 3 つの特性がある場合、推奨特性は以下のようになります。

1. 特性 3（母集団が最も大きい特性）に最も一致する特性
2. 特性 1 に最も一致する特性
3. 特性 2 に最も一致する特性
4. 特性 3 に 2 番目に一致する特性
5. 特徴1には第2の一致があり、特徴が50までになるまで続きます。

特定の特性に対するレコメンデーションを取得するには、セグメントルール内（1）または特性レコメンデーションビュー内（2）の特性をクリックします。

![](assets/three-base-traits-numbered.png)

下の画像に示すように、特性をクリックするとポップアップウィンドウが開きます。推奨特性がセグメントに含まれていない場合は、**+** を押すと、その特性をセグメントに追加できます。

![](assets/add_to_segments.png)

> [!TIP]
>
>メインページから除外されたデータソースは、特性情報のポップアップウィンドウ内でレコメンデーションが生成される際に、その対象として考慮されます。また、このビューでデータソースを除外すると、それがメインページに適用されます。

> [!NOTE]
>
> 推奨特性は、購読しているフィードのファーストパーティ特性の場合もあれば、サードパーティ特性の場合もあります。

## 仕組み

To produce trait recommendations, Audience Manager computes the [Jaccard similarity](https://en.wikipedia.org/wiki/Jaccard_index) between the target trait and every other trait that your account has access to, including third-party data. Audience Managerには、類似性が最も高い50個までの特性が表示されます。

## 特性類似性スコア

Audience Manager calculate the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL UUID]s and then divide the two. 2 つの特性、A と B の計算は次のようになります。

![](assets/jaccard_similarity.png)

以下の 2 つの例も確認してください。

### 例 1 - 低い特性類似性スコア

Given two traits A and B, let's say each of the traits has a population of 1,000,000 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]s of which qualify for both traits.
Using the formula above, this will result in: 25,000 / 1,975,000 = 0.012. This is a low [!UICONTROL Trait Similarity Score], the two traits are very dissimilar.

![](assets/Trait-Recommendations-Low-overlap.png)

### 例2-特徴の類似性スコア

If the same traits A and B had 400,000 [!UICONTRL UUID]s that qualify for both traits, the [!UICONTROL Trait Similarity Score] is much higher:
400,000 / 1,600,000 = 0.25

![](assets/Trait-Recommendations-High-overlap.png)

### 特性類似性スコアの解釈の方法

以下の表を、特性類似性についての大まかなガイドとして使用してください。このガイドは、ほとんどの特性にわたって観察される類似性スコアに基づいています。

| [!UICONTROL Trait Similarity Score] | 有意性 |
---------|----------|
| 0.1 以上 | 特性間の類似性が高い |
| 0.03～0.1 | 特性間の類似性が中程度 |
| 0.01～0.03 | 特性間の類似性が低い |
| 0～0.01 | 特性間の類似性が非常に低い |

## ロールベースのアクセス制御（RBAC）

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), you need to have permission to create and edit segments in order to see recommended traits. And, the recommended traits you see are only the ones from data sources that you have access to via [!UICONTROL RBAC]. [!UICONTROL RBAC] コントロール [について](../administration/administration-overview.md)詳しくは、こちらを参照してください。

## 制限事項

* 現在、Audience Manager では、推奨特性としてフォルダー特性は表示されません。フォルダー特性について詳しくは、[こちら](../traits/manage-folder-traits.md)を参照してください。
* When displaying Trait Recommendations, Audience Manager does not take into account [!DNL Boolean] operators ([!DNL AND], [!DNL OR], [!DNL NOT]) in segment rules.