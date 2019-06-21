---
description: プロファイル結合ルールを使用すると、セグメンテーションに使用するデータセットを管理できます。また、複数のデバイスにわたって個人を正確にターゲットに設定することができます。
seo-description: プロファイル結合ルールを使用すると、セグメンテーションに使用するデータセットを管理できます。また、複数のデバイスにわたって個人を正確にターゲットに設定することができます。
seo-title: プロファイル結合ルールの概要
solution: Audience Manager
title: プロファイル結合ルールの概要
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# プロファイル結合ルールの概要 {#profile-merge-rules-overview}

With [!UICONTROL Profile Merge Rules] you get control over the data sets used for segmentation and can target a person accurately across multiple devices.

## 匿名プロファイルと認証済みプロファイルによるデータ収集とターゲット設定 {#data-collection-targeting}

通常、オーディエンスのセグメント化とターゲット設定は、デバイス上のすべてのユーザーから収集されたデータに基づいておこないます。デバイスレベルのデータに基づくデータ収集とターゲット設定には、いくつかのデメリットがあります。例えば、デバイスを共有する複数のユーザーを区別したり、複数のデバイスにまたがるユーザーを正確にターゲット化することができません。デバイスに基づくデータ収集は、デジタルマーケティングキャンペーンやクロスデバイスターゲティングには十分ではありません。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] を根本的に変更することで、データ [!DNL Audience Manager] を収集し、ターゲット設定するユーザーをセグメント化できます。これにより、デバイスプロファイルと認証済みプロファイルの 2 種類のプロファイルを操作できるようになります。

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> プロファイルタイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> デバイスプロファイル </td> 
   <td colname="col2"> <p>デバイスプロファイルは、特定のデバイスの ID（Cookie ID やモバイルデバイス ID など）に関連付けられています。以下のようなものがあります。 </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">ユーザーが認証されていない状態で認識された、ルールベースの特性。 </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Cookie ベースのサードパーティデータなどのデバイス ID に関連付けられた、オンボードの特性。 </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> 認証済みプロファイル </td> 
   <td colname="col2"> <p>認証済みプロファイルは、ユーザーがサイトにログインした時点で渡されるユーザー ID に関連付けられています。以下のようなものがあります。 </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">ユーザーが認証されている状態でデバイス間で収集された、ルールベースの特性。 </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">オンボードの特性は、同じユーザー ID にリンクされているオフラインのファイルです。 </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

これらの各種のプロファイルにより、セグメント化に使用できるデータを制御します。例えば、認証済みプロファイルを使用すると、複数のデバイスから収集した 1 人のユーザーに関するデータに基づいて正確なセグメントを生成できます。これにより、複数のデバイスにまたがってユーザーに対し一貫したブランドエクスペリエンスを提供できるようになります。さらに、クロスデバイス認証により、[!DNL Audience Manager] はユーザーがオンラインアクティビティで使用する各種のプラットフォームをマッピングできます。[!UICONTROL Profile Link Device Graph]これを呼び出します。

![](assets/authenticated2.png)

## メリット {#advantages}

With [!UICONTROL Profile Merge Rules] you can:

* 認証済みプロファイル、匿名プロファイル、またはその両方の組み合わせに基づいて、ユーザーをターゲット化する。
* デバイス間で特定の顧客をターゲット化する。
* 決定論的データに基づいてデバイスグラフを作成する。
* 各種のプロファイルに基づいてセグメントのデータを微調整する。
* オーディエンスに関する詳細なインサイトを得る。

## はじめに {#getting-started}

See the following sections and the [FAQ](../../faq/faq-profile-merge.md) for more information about [!UICONTROL Profile Merge Rules].

* [プロファイル結合ルールの導入](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [プロファイル結合ルールダッシュボード](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [定義済みのプロファイルの結合ルールオプション](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [プロファイル結合ルールの一般的なユースケース](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [プロファイルリンクデバイスグラフのユースケース](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [ 外部デバイスグラフのユースケース](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [プロファイル結合ルールのレポート指標](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [プロファイル結合ルールとデバイスセグメント化解除プロセス](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [Instant Cross-Device Suppression](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [デバイスグラフを伴うプロファイル結合ルールの重要な考慮事項](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
