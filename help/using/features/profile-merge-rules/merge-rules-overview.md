---
description: プロファイル結合ルールを使用すると、セグメンテーションに使用するデータセットを管理できます。また、複数のデバイスにわたって個人を正確にターゲットに設定することができます。
seo-description: プロファイル結合ルールを使用すると、セグメンテーションに使用するデータセットを管理できます。また、複数のデバイスにわたって個人を正確にターゲットに設定することができます。
seo-title: プロファイル結合ルールの概要
solution: Audience Manager
title: プロファイル結合ルールの概要
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# プロファイル結合ルールの概要 {#profile-merge-rules-overview}

セグメ [!UICONTROL Profile Merge Rules] ント化に使用するデータセットを制御し、複数のデバイスにわたって正確にユーザーをターゲット設定できます。

>[!VIDEO](https://video.tv.adobe.com/v/28974?captions=jpn)

## 匿名プロファイルと認証済みプロファイルによるデータ収集とターゲティング {#data-collection-targeting}

通常、オーディエンスのセグメント化とターゲティングは、デバイス上のすべてのユーザーから収集されたデータに基づいておこないます。デバイスレベルのデータに基づくデータ収集とターゲティングには、いくつかのデメリットがあります。例えば、デバイスを共有する複数のユーザーを区別したり、複数のデバイスにまたがるユーザーを正確にターゲット化することができません。デバイスに基づくデータ収集は、デジタルマーケティングキャンペーンやクロスデバイスターゲティングには十分ではありません。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules]プロを使用すれば、[!DNL Audience Manager] がデータを収集してユーザーをターゲット化のためにセグメント化する方法が根本的に変わります。It lets you work with 2 distinct types of profiles, a device profile and an [authenticated profile](../../reference/visitor-authentication-states.md).

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

これらの各種のプロファイルにより、セグメント化に使用できるデータを制御します。For example, with an [authenticated profile](../../reference/visitor-authentication-states.md), you can build accurate segments based on data from multiple devices for a single user. これにより、複数のデバイスにまたがってユーザーに対し一貫したブランドエクスペリエンスを提供できるようになります。Audience Managerは、個人がオンラインアクティビティに使用する様々なデバイスのマッピングを認証済みプロファイルに保存することで、これを実 [現します](../../reference/visitor-authentication-states.md)。 これらのマッピングは、と呼ばれま [!UICONTROL Profile Link Device Graph]す。

![](assets/authenticated2.png)

## メリット {#advantages}

[!UICONTROL Profile Merge Rules] では、以下のことが可能です。

* Target users based on [authenticated profile](../../reference/visitor-authentication-states.md), anonymous profiles, or combinations of both.
* デバイス間で特定の顧客をターゲット化する。
* 決定論的データに基づいてデバイスグラフを作成する。
* 各種のプロファイルに基づいてセグメントのデータを微調整する。
* オーディエンスに関する詳細なインサイトを得る。
