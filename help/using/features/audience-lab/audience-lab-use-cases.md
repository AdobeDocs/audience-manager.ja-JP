---
description: Audience Lab は、ベースラインセグメントを使用してテストグループを作成することで、いくつかの用途に使用できます。テストグループを重複のない複数のテストセグメントに分割し、それぞれを異なる宛先にマッピングした後、コンバージョンを推進するうえでどのセグメントが最も効果的かを判断することができます。
seo-description: Audience Lab は、ベースラインセグメントを使用してテストグループを作成することで、いくつかの用途に使用できます。テストグループを重複のない複数のテストセグメントに分割し、それぞれを異なる宛先にマッピングした後、コンバージョンを推進するうえでどのセグメントが最も効果的かを判断することができます。
seo-title: Audience Lab のユースケース
solution: Audience Manager
title: Audience Lab のユースケース
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 100%

---


# Audience Lab のユースケース {#audience-lab-use-cases}

[!UICONTROL Audience Lab] では、テストグループを作成するためのベースラインセグメントを使用できるようになっているので、複数のユースケースが可能です。テストグループを重複のない複数のテストセグメントに分割し、それぞれを異なる宛先にマッピングした後、コンバージョンを推進するうえでどのセグメントが最も効果的かを判断することができます。

## Audience Lab でのモデルの比較 {#compare-models}

[!DNL Audience Manager] では、複数の異なるタイプおよびソースのモデルを使用できます。[!UICONTROL Audience Lab] では、すべてのアクティブモデルにわたって顧客のコンバージョン率を簡単に比較できます。

<!-- audience-lab-compare-models.xml -->

このユースケースでは、異なるモデルの比較をおこないます。社内データウェアハウスで作成したモデルを[オンボードの特性](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)として [!DNL Audience Manager] にインポートして使用するか、[!DNL Audience Manager] の[アルゴリズムモデル](../../features/algorithmic-models/understanding-models.md)機能を使用できます。

1. [Model Builder](../../features/algorithmic-models/create-model.md) または外部プラットフォームでモデルを 2 つ作成します。
1. [アルゴリズムの特性](../../features/traits/create-algorithmic-traits.md)を作成するか、オンボードの特性として独自のモデルをインポートします。
1. どちらのモデルのユーザーも重複しないよう、相互に排他的なセグメントを作成します。

   * *モデル 1 のセグメント*&#x200B;と&#x200B;*モデル 2 のセグメント*&#x200B;を作成します。
   * *モデル 1 のセグメント*&#x200B;のセグメントルールを、モデル 1 の特性 [!DNL AND NOT] モデル 2 の特性とし、*モデル 2 のセグメント*&#x200B;についてはその逆とします。

1. [!UICONTROL Audience Lab] で、一方は&#x200B;*モデル 1 のセグメント*、もう一方は&#x200B;*モデル 2 のセグメント*&#x200B;をベースラインとする[ 2 つのセグメントテストグループを作成](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)します。

   * どちらのテストグループも、宛先、クリエイティブ、コンバージョン特性の条件を同じにします。
   * テストセグメントのユーザー数が大きく違わないようにしてください（例えば、160 万人に対して 180 万人の場合は問題ありませんが、160 万人に対して 1600 万人の場合は問題となります）。
   * 各テストセグメントのテストグループで対照群を用意します。そうすることで、各セグメントのごく一部を切り離し、それらを明示的にテストのターゲット対象から外すことができます。

1. 結果の確認

   * [Audience Lab のレポート表示](../../features/audience-lab/audience-lab-reporting-view.md)には、各モデルが達成したコンバージョン数が示されます。コンバージョンベースのキャンペーンでは、コンバージョン率が最も高いテストセグメントのモデルが最も優れたパフォーマンスを示したことになります。
   * 用意しておいた対照群を使用して、「標準のターゲティング」に対するモデルのパフォーマンスを評価することもできます。モデル同士を比較してテストするだけでなく、「モデルのパフォーマンスが通常時よりも上がっているか」という疑問を確認するためのテストが可能です。

## すべての宛先をまたいだクリエイティブのテスト {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

[!UICONTROL Audience Lab] を使用すると、クリエイティブが様々な宛先で推進しているコンバージョンの数を測定できます。このユースケースでは、自然発生しているコンバージョンに対してクリエイティブが創出しているコンバージョンを測定できます。

1. クリエイティブをテストするセグメントをベースラインセグメントとして選択し、[セグメントテストグループを作成します。](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)
1. ベースラインセグメントをテストセグメントと対照群に分割します。
1. テストする様々な宛先とテストセグメントをマッピングします。
1. 対照群はどの宛先にもマッピングしないでおきます。自然発生しているコンバージョン結果のベースラインとするために、対照群は、テストするクリエイティブのターゲット対象にしないでおきます。
1. テストの開始日と終了日を指定します。
1. セグメントとクリエイティブを宛先に設定します。
1. [Audience Lab のレポート表示](../../features/audience-lab/audience-lab-reporting-view.md)には、宛先全体でクリエイティブが達成したコンバージョン数が示されます。
1. 対照群を作成しておいたので、自然発生しているコンバージョンに対してクリエイティブが創出しているコンバージョンを評価することもできます。「このクリエイティブは通常のやり方の場合よりも高いコンバージョン率を創出しているだろうか」という疑問に対する答えが得られます。
