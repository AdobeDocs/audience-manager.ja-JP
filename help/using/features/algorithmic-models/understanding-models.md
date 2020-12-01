---
description: 類似（look-alike）モデリングで使用する特性やセグメントを作成および管理します。
keywords: relative weight, lookalike
seo-description: 類似（look-alike）モデリングで使用する特性やセグメントを作成および管理します。
seo-title: 類似（look-alike）モデリングについて
solution: Audience Manager
title: 類似（look-alike）モデリングについて
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1590'
ht-degree: 100%

---


# [!UICONTROL Look-Alike Modeling]について {#about-algorithmic-models}

## [!UICONTROL Look-Alike Modeling]で新しいユーザーを見つける {#find-new-users}

[!UICONTROL Look-Alike Modeling] を使用すると、自動データ分析により、新しいユニークオーディエンスを発見できます。このプロセスは、[!UICONTROL trait]または[!UICONTROL segment]、時間間隔、ファーストパーティおよびサードパーティの[!UICONTROL data sources]を選択した時点で開始します。この選択が、アルゴリズムモデルの入力となります。分析処理が実行されると、選択した母集団と共有する特徴に基づいて、該当するユーザーを検索します。完了すると、このデータは[特性ビルダー](../../features/traits/about-trait-builder.md)で使用可能になります。ここでは、このデータを使用して[精度とリーチ](../../features/traits/trait-accuracy-reach.md)に基づいて特性を作成できます。さらに、アルゴリズム特性と[!UICONTROL rules-based traits]を結合するセグメントを作成し、[!DNL Boolean]式や比較演算子を使用して他の認定要件を追加することができます。[!UICONTROL Look-Alike Modeling] を使用すると、使用可能なすべての特性データから価値を動的に抽出できます。

## メリット {#advantages}

[!UICONTROL Look-Alike Modeling] を使用する主なメリットには、次のようなものがあります。

* **データの精度：**&#x200B;アルゴリズムは定期的に実行されるので、結果は常に最新で関連性の高いものになります。
* **自動化：**&#x200B;大規模な静的ルールのセットを管理する必要はありません。アルゴリズムがオーディエンスを特定します。
* **時間の短縮と労力の削減：**&#x200B;モデリングプロセスにより、どの[!UICONTROL traits]や[!UICONTROL segments]が機能するか推測する必要はなくなり、また新しいオーディエンスを特定するためにキャンペーンに時間をかける必要もなくなります。この作業はモデルによりおこなうことができます。
* **信頼性：**&#x200B;モデリングでは、サーバー側の特定および認証プロセスにより、自分のデータと、選択したアクセス可能なサードパーティデータを評価します。このため、特性についてサイトの訪問者を認定する場合、その全員を把握する必要はありません。

## ワークフロー {#workflow}

**[!UICONTROL Audience Data > Models]**&#x200B;でモデルを管理します。全体的なワークフローとして、以下の処理をおこないます。

* アルゴリズムにより評価するベースラインデータを選択する。これには、[!UICONTROL trait]、または[!UICONTROL segment]、時間範囲、および[!UICONTROL data sources]（自分のデータや、[!DNL Audience Manager] からアクセス可能なサードパーティデータ）が含まれます。モデルの作成ワークフローでは、モデルの邪魔になる[!UICONTROL traits]を除外できます。
* モデルを保存する。保存したアルゴリズム評価プロセスは、自動的に実行されます。この処理が完了するまで最大 7 日かかります。アルゴリズムが完了し、結果を使用して[!UICONTROL trait]を作成できるようになると、[!DNL Audience Manager] から電子メールが送信されます。
* [!UICONTROL Trait Builder] でアルゴリズムによる[!UICONTROL traits]を作成します。
* [!UICONTROL Segment Builder]で[!UICONTROL traits]を[!UICONTROL segments]に組み合わせます。
* [!UICONTROL segment]データを作成し、[!UICONTROL destination]に送信します。

## トラブルシューティング {#troubleshooting}

データの生成に 3 回連続で失敗した [!UICONTROL Look-Alike Model] は、非アクティブ化されます。後でモデルのステータスを「Active」に戻すことはできません。モデルがデータを生成するようにするには、データを蓄積するために十分な量の[!UICONTROL traits]を持つデータソースからモデルを作成することが推奨されます。

## [!UICONTROL TraitWeight]について {#understanding-traitweight}

[!UICONTROL TraitWeight] は、新しい[!UICONTROL traits]を自動的に検出するように設計された独自のアルゴリズムです。現在の[!UICONTROL traits]および[!UICONTROL segments]の[!UICONTROL trait]データを、[!DNL Audience Manager] を通じてアクセスできる他のあらゆるファーストパーティおよびサードパーティデータと比較します。この節では、[!UICONTROL TraitWeight] アルゴリズムの検出プロセスについて説明します。

![](assets/algo_model.png)

次の手順は、[!UICONTROL TraitWeight] による評価プロセスを示しています。

### 手順 1：[!UICONTROL Trait]比較のベースラインを作成する

[!UICONTROL TraitWeight] はベースラインを作成するために、オーディエンスと関連付けられているすべての[!UICONTROL traits]を 30 日、60 日、90 日の間隔で測定します。その後、頻度と相関関係に基づいて[!UICONTROL traits]をランク付けします。頻度では一般性が測定されます。相関関係では、ベースラインオーディエンスのみにおける[!UICONTROL trait]の出現頻度が測定されます。出現頻度が高い[!UICONTROL Traits]は一般性が高いと見なされます。これは、選択した[!UICONTROL data sources]で検出された[!UICONTROL traits]と組み合わせて重み付けスコアを設定するために使用する、重要な特徴です。

### 手順 2：[!UICONTROL Data Source]で同じ[!UICONTROL Traits]を見つける

比較のためのベースラインを作成した後、アルゴリズムは選択した[!UICONTROL data sources]内で同じ[!UICONTROL traits]を検索します。この手順では、[!UICONTROL TraitWeight] は、見つかったすべての[!UICONTROL traits]の頻度を計上し、ベースラインと比較します。しかし、ベースラインとは異なり、一般的でない[!UICONTROL traits]は出現頻度が高い特性よりランクが高くなります。出現頻度が低い[!UICONTROL traits]は、特異性が高いと見なされます。[!UICONTROL TraitWeight] は、一般的なベースライン[!UICONTROL traits]と一般的でない（特異性が高い）[!UICONTROL data source] [!UICONTROL traits]の組み合わせを、両方のデータセットに共通する[!UICONTROL traits]より影響力が大きく望ましいと評価します。アドビのモデルでは、このような大規模で一般的な[!UICONTROL traits]が認識され、相関関係が強いデータセットに過剰な優先度は割り当てられません。一般的でない[!UICONTROL traits]の優先度が高くなるのは、このような[!UICONTROL traits]のほうが、ボード全体で一般性の高い特性よりも、新しい個別ユーザーを表していると考えられるからです。

### 手順 3：重みを割り当てる

この手順では、[!UICONTROL TraitWeight] は新しく見つかった[!UICONTROL traits]を、影響力や望ましさの順にランク付けします。重みの基準は、0%～100% の割合です。[!UICONTROL Traits]のランクが 100% に近づくと、基準となる母集団のオーディエンスに似ていることを意味します。また、重みの大きい[!UICONTROL traits]は高く評価されます。これは、このような特性が、確立されたベースラインオーディエンスと同様に行動する可能性がある、新しい個別ユーザーを表しているためです。[!UICONTROL TraitWeight] は、ベースラインで一般性が高く、比較対象のデータで特異性が高い[!UICONTROL traits]を、各データセットで共通の[!UICONTROL traits]よりも高く評価します。

### 手順 4：ユーザーにスコアを割り当てる

選択した[!UICONTROL data sources]に含まれる各ユーザーに、ユーザーのプロファイルにおいて影響力を持つ[!UICONTROL traits]の重みの合計に等しいユーザースコアが割り当てられます。その後、各ユーザースコアが 0～100％の範囲で正規化されます。

### 手順 5：結果を表示して操作する

[!DNL Audience Manager] は重み付けモデルの結果を[!UICONTROL Trait Builder]に表示します。[!UICONTROL algorithmic trait]を作成する場合、[!UICONTROL Trait Builder]を使用すると、データ実行時にアルゴリズムにより生成された重み付けスコアに基づいて[!UICONTROL traits]を作成できます。選択する精度を高くするほど、ユーザースコアが高いユーザー、つまり他のオーディエンスよりもベースラインオーディエンスに近いユーザーのみを認定できます。精度を低くすると、オーディエンス（リーチ）を広げることができます。

### 手順 6：処理サイクルをまたいで[!UICONTROL Trait]の重要性を再評価する

[!UICONTROL TraitWeight] は、[!UICONTROL trait]の母集団のサイズと変更に基づいて、[!UICONTROL trait]の重要性を定期的に再評価します。この処理は、その[!UICONTROL trait]について認定されたユーザーの数が時間の経過とともに増減するとおこなわれます。この動作は、非常に大規模になる特性で最も明確に見られます。例えば、アルゴリズムが[!UICONTROL trait A]をモデリングに使用しているとします。[!UICONTROL trait A] の母集団が増加すると、[!UICONTROL TraitWeight] はこの[!UICONTROL trait]を再評価し、低いスコアを割り当てたり、無視する場合があります。この場合、[!UICONTROL trait A]は一般的すぎる、または大きすぎるので、母集団について重要性が高いとは言えません。[!UICONTROL TraitWeight]で[!UICONTROL trait A]の価を減らす（またはモデル内で無視する）と、アルゴリズム特性の母集団が小さくなります。影響力のある[!UICONTROL traits]のリストは、ベースライン母集団の増加を反映しています。影響力のある[!UICONTROL traits]のリストを使用すると、これらの変化がなぜ発生しているかがわかります。

関連リンク：

* [モデルビルダー](../../features/algorithmic-models/create-model.md)
* [精度とリーチ](../../features/traits/trait-accuracy-reach.md)

## [!UICONTROL Look-Alike Models]および[!UICONTROL Traits] のスケジュールを更新する {#update-schedule}

新規または既存の[!UICONTROL algorithmic models]および[!UICONTROL traits]のスケジュールを作成および更新します。

### [!UICONTROL Look-Alike Model]スケジュールの作成と更新

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> アクティビティのタイプ </th>
   <th colname="col2" class="entry"> 説明 </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>モデルの作成または複製</b> </td>
   <td colname="col2"> <p>新規または複製した [!UICONTROL Look-Alike Models] について、作成プロセスは毎日次の時間に 1 回実行されます。 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 午後 5 時 EST（11 月～3 月） </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 午後 6 時 EDT（3 月～11 月） </li> 
     </ul> </p> <p>作成期日後に構築または複製されたモデルは、翌日に処理されます。 </p> <p>モデルの最初の実行でデータが生成されない場合、2 回目は次の日に実行されます。2 回目でもデータが生成されない場合、3 回目がその次の日に実行されます。3 回目の試行でもデータが生成されない場合、モデルは実行を停止します。この場合、モデルは非アクティブ化されます。詳しくは、<a href="../../features/algorithmic-models/understanding-models.md#troubleshooting">類似（look-alike）モデルのトラブルシューティング</a>を参照してください。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>モデルの更新</b> </td> 
   <td colname="col2"> <p>理想的な状況では、既存のモデルは、少なくとも 7 日に 1 回、平日に実行されます。例えば、モデルを月曜日に作成する（期限により）と、遅くとも翌週の月曜日には更新されます。 </p> <p>以下の条件のいずれかを満たした場合に、モデルは再実行されます。 </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">その最後の実行が成功しなかった。 </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">以前に実行が成功し、かつ、過去 7 日間にまったく実行されておらず、かつ、モデルに少なくとも 1 つのアクティブな特性が添付されている。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait]スケジュールの作成と更新

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> アクティビティのタイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>特性の作成</b> </td> 
   <td colname="col2"> <p>特性作成プロセスは、月曜日から金曜日まで、毎日実行されます。通常、新しいアルゴリズム特性は、48 時間以内に UI に表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>特性の更新</b> </td> 
   <td colname="col2"> <p>既存の特性は、少なくとも 7 日に 1 回は更新され、モデル更新のスケジュールに従います。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## モデルのリスト表示 {#models-list-view}

リスト表示は、モデルを作成、確認および管理するのに役立つ一元的なワークスペースです。

[!UICONTROL Models]リストページには、以下をおこなうために役立つ機能およびツールが含まれています。

* 新しいモデルの作成。
* 既存のモデルの管理（編集、一時停止、削除または複製）。
* 名前によるモデルの検索。
* 任意のモデルを使用して [!UICONTROL algorithmic traits] を作成します。

## モデルの概要表示 {#models-summary-view}

概要ページには、名前、リーチ／精度、処理履歴、モデルから作成された[!UICONTROL traits]などの、モデルの詳細が表示されます。このページにはまた、モデルを作成および管理するための設定も含まれています。概要リストでモデル名をクリックすると、モデルの詳細が表示されます。

モデル概要ページには、以下のセクションが含まれています。

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> セクション </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> 基本情報</span> </p> </td>
   <td colname="col2"> <p>名前および最終実行日など、モデルに関する基本情報が含まれます。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Model Reach and Accuracy</span> </p> </td> 
   <td colname="col2"> <p>前回のモデル実行の<a href="../../features/traits/trait-accuracy-reach.md">精度とリーチ</a>のデータを表示します。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Model Processing History</span> </p> </td> 
   <td colname="col2"> <p>過去 10 回の実行の処理日時と、データがそれらの実行で生成されたかどうかを表示します。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Influential Traits</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">Influential Traits</span> テーブルには以下が含まれます。 </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> モデルの基準となる母集団で最もよく表される上位 50 個の影響力のある特性のリスト。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E"><span class="wintitle">Relative Weight</span> ランクの順に各特性をランク付けします。<span class="wintitle">Relative Weight</span> は、新しく検出された特性を影響力または望ましさの順で並べ替えます。重みの基準は、0%～100% の割合です。特性のランクが 100% に近づくと、基準となる母集団のオーディエンスに似ていることを意味します。詳しくは、<a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> TraitWeight について</a>を参照してください。 </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">特性ごとに 30 日間の個別および合計特性母集団を表示します。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Traits Using Model</span> </p> </td>
   <td colname="col2"> <p>選択したモデルに基づいて、アルゴリズム特性のリストを表示します。特性名または特性 ID をクリックすると、特性に関する詳細情報が表示されます。「<b><span class="uicontrol">Create New Trait with Model</span></b>」を選択すると、アルゴリズム特性作成プロセスに移動します。 </p> <p>セクションラベルは、モデルの名前に基づいて変更されます。例えば、モデルを作成して名前をモデル A にしたとします。概要ページを読み込むと、このセクションの名前が <span class="wintitle">Traits Using Model A</span> に変更されます。 </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [宛先](../../features/destinations/destinations.md)
>* [特性](../../features/traits/trait-details-page.md)
>* [セグメント](../../features/segments/segments-purpose.md)

