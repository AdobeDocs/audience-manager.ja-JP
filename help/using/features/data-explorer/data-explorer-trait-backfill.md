---
description: 特性適合のバックフィルにより、過去のオーディエンスを収集して、特性作成日前の関連データを逃してしまうことを防ぎます。
seo-description: 特性適合のバックフィルにより、過去のオーディエンスを収集して、特性作成日前の関連データを逃してしまうことを防ぎます。
seo-title: 特性適合のバックフィル
title: 特性適合のバックフィル
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
translation-type: ht
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: ht
source-wordcount: '451'
ht-degree: 100%

---


# 特性適合のバックフィル {#backfill-trait-realizations}

特性適合のバックフィルにより、過去のオーディエンスを収集して、特性作成日前の関連データを逃してしまうことを防ぎます。

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill]は、追加のユースケースをロック解除して Audience Manager を強化できるプレミアム機能です。バックフィルを使用するには追加の処理能力がかかりますが、追加料金をお支払いいただければ Audience Manager のすべてのお客様がご利用になれます。詳しくは、アドビのセールス担当者にお問い合わせください。

未使用シグナルから特性を作成するときに、指定期間における特性適合をバックフィルすることができます。[!DNL Audience Manager] は、新しく作成した特性の対象として認定されるオーディエンスの過去データを収集し、対応するプロファイルに保管します。**[!UICONTROL Backfill Options]** は、**[特性ビルダー](../../features/traits/about-trait-builder.md)** の「[!UICONTROL Trait Expression]」セクションに表示されます。

>[!NOTE]
>
>特性適合のバックフィルは、ルールベースの特性およびオンボードの特性に対しておこなうことができます。

特性適合のバックフィルの手順は次のとおりです。

1. [!UICONTROL Audience Data > Signals > Search] の順に選択し、シグナル検索を実行するか[シグナルダッシュボード](../../features/data-explorer/data-explorer-signals-dashboard.md)を使用して、新しい特性で使用するシグナルを特定します。
1. 目的のシグナルに基づいて新しい特性を作成します。
1. 「**[!UICONTROL Trait Expression]**」セクションの **[!UICONTROL Backfill Options]** を使用して、特性適合のバックフィルをおこなう期間を選択します。事前定義されているバックフィル期間は、1 日、7 日、14 日および 30 日です。30 日までの範囲でカスタムの期間を指定することもできます。

   ![trait-backfill](assets/signals-trait-backfill.png)

1. （オプション）「**[!UICONTROL Estimated Trait Realizations]**」セクションの「**[!UICONTROL Estimate Realizations]**」をクリックして、過去 7 日間にバックフィルされた特性の [!UICONTROL Unique Trait Realizations] および [!UICONTROL Total Trait Population] の推定値を表示します。

   ![estimate-trait-realizations](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >次の演算子を使用した式を含む特性に対しては、特性のバックフィルおよび推定は利用できません。
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 特性を作成します。

特性の作成が完了すると、適合の統計値にバックフィルされた適合数が表示されます。

特性のバックフィル方法に関するビデオチュートリアルについては、以下のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/25169/?captions=jpn)

## 特性バックフィルの待ち時間 {#trait-backfilling-latency}

新しく作成した特性では、作成から 2～3 時間後にオーディエンスの収集が開始されます。ただし、[!DNL Audience Manager] で 1 日あたりに処理されるデータ量は多いので、バックフィルした母集団が [!UICONTROL Unique Trait Realizations] グラフおよび [!UICONTROL Total Trait Population] グラフに反映されるまでには時間がかかります。

Audience Manager の [!UICONTROL Trait Graph] は、特性の作成時点から 48 時間以内にバックフィルした母集団で更新されます。

## 特性バックフィルの制限 {#trait-backfilling-limit}

[!UICONTROL Data Explorer] でバックフィルできる特性は 1 か月あたり 50 個までに制限されており、バックフィルの実行可能回数は毎月 1 日にリセットされます。

>[!NOTE]
>
>特性バックフィルの残り回数は、前の月から持ち越されません。例えば、今月にバックフィルした特性が 30 個であっても、翌月のバックフィルの残り回数は 70 ではなく 50 になります。

## レポートに対する影響 {#reporting-impact}

[!DNL Audience Manager] により過去のシグナルが特性適合に変換されるので、バックフィルした特性適合は、[!UICONTROL Unique Trait Realizations] 指標および [!UICONTROL Total Trait Population] 指標に反映されます。

ただし、[!UICONTROL General Reports]、[!UICONTROL Trait Graph]、[!UICONTROL Trend Reports]に、バックフィルで得られた特性作成日前の指標が遡って反映されることはありません。