---
description: このレポートは、選択した日付より前の 30 日間に 10,000 回以上認識され、同じ期間での標準偏差がどちらの方向にも 1.7 以上であった特性のリストを返します。このレポートを使用すると、特性においてユニークユーザーからのインプレッション数が時間の経過によってどのように変動するかを評価できます。
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: Daily Trait Variation レポート
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 99%

---

# Daily Trait Variation レポート {#daily-trait-variation-report}

このレポートは、選択した日付より前の 30 日間に 10,000 回以上認識され、同じ期間での標準偏差がどちらの方向にも 1.7 以上であった特性のリストを返します。このレポートを使用すると、特性においてユニークユーザーからのインプレッション数が時間の経過によってどのように変動するかを評価できます。

>[!NOTE]
>
>Audience Manager の Daily Trait Variation レポートは、RBAC の原則に従います。自分が属している [RBAC ユーザーグループ](/help/using/features/administration/administration-overview.md) に基づき、自分がアクセスできるデータソースからの特性のみを確認できます。

標準偏差は、平均からの変動または分散の量（または平均／期待値）を測定します。低い標準偏差は、データポイントが平均に非常に近くなる傾向があることを示します。高い標準偏差は、データポイントが幅広い値に分散していることを示します。

![](assets/daily_trait_variation.png)

[!UICONTROL Date] リストを使用して、レポート用の 1 つ以上の日付を選択します。選択したすべての日付にわたるすべての特性の標準偏差の範囲を視覚的に表す、色分けされた棒グラフがリストの下部に表示されます。黒い縦の線は平均を示します。

中央の列には、[!UICONTROL Trait ID] と [!UICONTROL Trait Name] で識別される、特性のリストが含まれます。任意の特性をクリックすると、ポップアップダイアログボックスが表示され、以下のオプションから選択できます。

* **Keep Only：**&#x200B;レポートから他のすべての特性を削除し、この特性のデータのみを表示します。
* **Exclude：**&#x200B;レポートからこの特性を削除し、他のすべての特性のデータを表示します。複数の特性を除外できます。
* **View Data：**&#x200B;その表示のデータを表示できます。また、すべての行をテキストファイルとしてダウンロードできます。

[!UICONTROL Standard Deviation] 列には、選択した期間における各特性の標準偏差を示す、色分けされた棒グラフが表示されます。赤い棒は、負の標準偏差の特性を示します（データポイントが平均を下回る傾向がある）。緑の棒は、正の標準偏差の特性を示します（データポイントが平均を上回る傾向がある）。任意の棒にマウスポインターを置くと、詳細情報と、その特性を維持または除外して詳細を表示するオプションを含むポップアップダイアログボックスが表示されます。

アイコンがレポートの下に表示され、様々な形式でデータを書き出したり、レポートに対しておこなった変更（特性の除外など）を元に戻したり、自動更新を有効または無効にしたり、レポートのデータを更新したりできます。[ レポートアイコンとツールの説明 ](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained) を参照してください。

## ユースケース {#use-cases}

**例 1**：このレポートは、季節性が高い特性がある状況で非常に役に立つことがあります。例えば、オンラインストアで、様々なタイプや価格の季節限定プロモーションをテストしているとしましょう。[!DNL Audience Manager] に次の特性が定義されています。

* `productPage == "December Promotion"`
* `price > "500"`

12 月 20 日に [!UICONTROL Daily Trait Variation] レポートを実行し、過去 30 日間で上記特性に確かな正の偏差があることに気がついたとしましょう。これは、季節限定プロモーションで言及している製品を訪問者が探していることを示唆している可能性があります。このトレンドを生かすには、その特定製品カテゴリ向けのクリエイティブを、それらに興味を持つ訪問者にターゲティングすることに、より多くの労力を注ぐことができます。

**例 2**：このレポートは、タグ付けの問題や特性の設定ミスに関係するターゲティングの異常を特定するのに役に立つことがあります。オンラインストアのカテゴリに基づいて、次の特性を定義したとしましょう。

* `productPage == "smartphones"`

ストアの再設定の影響で、スマートフォンページをブランド名に基づいて複数のページに分割しようとしています。しかし、[!DNL Audience Manager] に定義した特性を更新するのを忘れました。

1 か月後、[!UICONTROL Daily Trait Variation] レポートを実行し、サイト分析によれば訪問者数が増加しているにもかかわらず、`productPage == "smartphones"` 特性に関して大きい負の偏差があることに気がつきます。この情報に基づいて、新しい製品ページに対応するように [!DNL Audience Manager] 内の特性を更新していないことに気がつきます。そこで、次の特性を作成する必要があることがわかります。

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

これをおこなえば、オーディエンスが、新しく作成した特性の対象に認定されるようになります。
