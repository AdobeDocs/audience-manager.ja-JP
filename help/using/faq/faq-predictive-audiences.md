---
description: Predictive Audiences は、データサイエンスを使用して、リアルタイムに不明なオーディエンスを個別のペルソナに分類するのに役立ちます。
seo-description: Predictive Audiences は、データサイエンスを使用して、リアルタイムに不明なオーディエンスを個別のペルソナに分類するのに役立ちます。
seo-title: Predictive Audiences に関する FAQ
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 71e129a39cf85d5f07979ede8f3aa862f93b6512
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 67%

---


# Predictive Audiences に関する FAQ

[!UICONTROL Predictive Audiences] に関するよくある質問です。

 

**[!UICONTROL Look-alike modeling]に対して、[!UICONTROL Predictive Audiences]はいつ使用する必要がありますか？**

[!UICONTROL Predictive Audiences] と [!UICONTROL Look-alike modeling] では、異なるユースケースを提供します。2 つのアルゴリズムの主な違いを次に示します。

1. [!UICONTROL Look-alike modeling] は、少数のオーディエンスを入力として取り、それを拡張します。[!UICONTROL Predictive Audiences] は、多数のオーディエンスを入力として取り、ペルソナによって定義された、より少数の個別のオーディエンスに分割します。
1. ベースセグメントの数は、アルゴリズムごとに異なります。[!UICONTROL Predictive Audiences] では少なくとも 2 つのベースラインが必要なのに対して、[!UICONTROL Look-alike modeling] で使用するベースラインは、最大で 1 つです。
1. [!UICONTROL Predictive Audiences] はリアルタイムセグメント評価を実行するのに対して、[!UICONTROL Look-alike modeling] は実行しません。

お客様のユースケースに基づいて、どちらのモデルがより適切かを判断する必要があります。

複数のベースラインの [!UICONTROL Predictive Audiences] モデルの構築は、リアルタイム評価のみを除いた、同じ数の類似（look-alike）モデルの構築と同等と考えることができます。また、1 つの個別のペルソナではなく、複数の異なるペルソナに属する訪問者を含む可能性が非常に高くなります。

 

**ペルソナ／モデルはいくつ作成できますか？**

最大 10 個の [!UICONTROL Predictive Audiences] モデルを作成できます。各モデルについて、最大 50 個のベースライン特性またはセグメントを定義できます。

 

**[!UICONTROL Predictive Audiences]セグメントから新しいセグメントを構築するにはどうしたらいいですか？**

**[!UICONTROL Audience Data]**／**[!UICONTROL Segments]** に移動して、**[!UICONTROL Predictive Audiences]** フォルダーをクリックします。目的のセグメントを見つけて、複製し、必要に応じて編集します。

 

**オンボーディングされた訪問者の一部が分類されないのはなぜですか？**

現在、オーディエンスの分類は、[!UICONTROL Profile Merge Rules] の一部として定義された認証済みのユーザーを除き、リアルタイム選定に対してのみ機能します。

オンボーディングされたデータの完全なサポートは、将来のアップデートで追加される予定です。

 

**モデルで生成される最初の結果はいつ確認できますか？**

[!UICONTROL Predictive Audiences] モデルが正常に実行されている場合、モデルの結果は、モデル作成後 24 時間以内に利用できます。

モデルが 24 時間以内に結果を生成しない場合は、アドビの担当者にお問い合わせください。

 

**モデルが結果を生成しなかったり警告ステータスが表示されたりするのはなぜですか？**

[!UICONTROL Predictive Audiences] モデルは、いくつかの理由で結果の生成に失敗する可能性があります。

1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough user profiles. We recommend choosing your [!UICONTROL traits] or [!UICONTROL segments] so that each persona has at least a few hundred user profiles.
1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough data in their user profiles (not enough traits to analyze).
1. ターゲットオーディエンスの特性／セグメントに、過去 30 日以内のアクティブなユーザーやオンボーディングされたユーザーが含まれていなかった。
1. 過去 30 日以内のアクティブまたはオンボーディングされたターゲットオーディエンスユーザーのユーザープロファイルに、十分なデータがない（分析するのに十分な特性がない）。
1. ターゲットオーディエンスセグメントでは、モデルに対して選択したものとは異な [!UICONTROL Profile Merge Rule] る値が使用されます。
1. ターゲットオーディエンス特性のデータソースが、モデルに選択したに含まれ [!UICONTROL Profile Merge Rule] ていない場合があります。

To produce relevant results, the [!UICONTROL Predictive Audiences] algorithm evaluates trait and segment realizations based on real-time user activity seen by the [!DNL DCS]. まだ十分なユーザー数を含んでいない新しいベース特性およびセグメントを選択する場合、アルゴリズムによってオーディエンスが分類されるまで数日かかることがあります。

最適な結果を得るには、[ペルソナの選択条件](../features/algorithmic-models/predictive-audiences.md#selection-personas)および[ターゲットオーディエンスの選択条件](../features/algorithmic-models/predictive-audiences.md#selection-audience)に記載されている推奨ガイドラインに従ってください。

 

**モデルにステータスが表示されるのはなぜで[!UICONTROL Error]すか。**

モデルが実行に失敗しました。In such cases, please reach out to your [!DNL Adobe] representative.

 

**AのIDを変更するには、ど[!UICONTROL Profile Merge Rule]うすればよいでし[!UICONTROL Predictive Audiences]ょう[!UICONTROL segment]か。**

以前のモデルと同じ人物およびターゲットオーディエンスを選択して、新しいモデルを作成します。 モデルの作成時に、別のを割り当て [!UICONTROL Profile Merge Rule]ます。

>[!WARNING]
> または、 [セグメントビルダーを使用して](../features/segments/segment-builder.md) 、既存の予測を使用し [!UICONTROL segment] たセグメントを手動で作成し、任意の予測を割り当てるこ [!UICONTROL trait][!UICONTROL Profile Merge Rule] ともできます。
> 
> ただし、予測は、その属するモデル [!UICONTROL traits] の継承を [!UICONTROL Profile Merge Rule] 自動的に行い、モデルの影響力に準拠したものから構築されるので、この方法 [!UICONTROL traits] はお勧めしません [!UICONTROL Profile Merge Rule] 。

 

**私は何[!UICONTROL Profile Merge Rule]を選べばいいですか？**

モデルに対してを選択 [!UICONTROL Profile Merge Rule] する場合は、使用事例を詳細に分析します。

ターゲットオーディエンスが、認証済みのプロファイルと [!UICONTROL segment] プロファイルに基づいて [!UICONTROL Profile Merge Rule] 値を使用し、予測に同じ値 [!DNL Device Graph] を選択したと [!UICONTROL Profile Merge Rule][!UICONTROL segments]します。 この場合、デバイスレベルとデバイス間のレベル [!UICONTROL traits] は、モデルのトレーニングや、ユーザーの予測への配置に使用され [!UICONTROL segment]ます。

ただし、デバイスのプロファイルのみを基にしてを選択した場合、クロスデバイスに影響を与えるこ [!UICONTROL Profile Merge Rule] とはなく、ユーザーの予測への配置には貢献しません [!UICONTROL traits][!UICONTROL segment]。 これは、モデルの精度とリーチに悪影響を与える可能性があります。

使用事例を慎重に分析し、モデルに学習させる [!UICONTROL trait] タイプと分類に使用するデータのタイプを決定します。

**どのペルソナの特性／セグメントにも属さないターゲットオーディエンスのユーザーは、分類されないことがありますか？**

プロファイルにどの特性も含まないユーザーの場合、分類されないことがあります。その場合、ユーザーは、すべてのペルソナの特性／セグメントで 0 に相当するスコアを獲得し、その結果、どの予測セグメントにも分類されません。

 

**予測セグメントのいずれかに分類されたユーザーは、異なる[!UICONTROL Predictive Audiences]セグメントに分類できますか？**

はい。アルゴリズムは、日々学習を重ねるので、特性スコアに関して各ペルソナに変更が適用されます。[!UICONTROL Predictive Audiences] セグメントに属するユーザーがアクティブである場合、その特性スコアの変更により、過去 30 日間のアクティビティに基づいて分類が変更される可能性があります。

 

**どのオーディエンスの分類がおこなわれているかによって、特性を確認できますか？**

はい、モデルレポートページのすべてのベースラインについて、影響力の大きいすべての特性を確認できます。[Influential Traits](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits) を参照してください。

 

**ベースライン特性またはセグメントの 1 つを編集すると、モデルはどうなりますか？**

モデルは、1 日に 1 回、特性またはセグメントを評価します。更新の翌日に、更新された分類を確認する必要があります。

 

**モデルが学習するデータソースを選択できますか？**

いいえ、データソースの選択はサポートされていません。[!UICONTROL Predictive Audiences] アルゴリズムは、すべてのファーストパーティ特性から学習します。