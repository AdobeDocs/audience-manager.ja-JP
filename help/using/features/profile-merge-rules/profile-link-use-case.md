---
description: プロファイルリンクデバイスグラフを使用したセグメントのリターゲティングと、パーソナライズされたセグメント認定の推奨事項およびユースケース。
seo-description: プロファイルリンクデバイスグラフを使用したセグメントのリターゲティングと、パーソナライズされたセグメント認定の推奨事項およびユースケース。
seo-title: プロファイルリンクデバイスグラフのユースケース
solution: Audience Manager
title: プロファイルリンクデバイスグラフのユースケース
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# プロファイルリンクデバイスグラフのユースケース {#profile-link-device-graph-use-cases}

Recommendations and use cases for segment retargeting and personalized segment qualification with the [!UICONTROL Profile Link Device Graph].

## 推奨事項 {#recommendations}

[!UICONTROL Profile Link] デバイスグラフは、以下に該当するキャンペーンで使用してください。

* デジタルプロパティ間で高度な認証をおこなっている。認証済みユーザーの数が少ない場合に[外部デバイスグラフオプション](merge-rule-definitions.md#device-options)を使用している。
* 既知のオーディエンスについて正確なターゲット化が必要である。[!UICONTROL Profile Link Device Graph] は、認証済みファーストパーティデータを使用して構築されます。
* 認証済み状態と未認証状態の既知のオーディエンスをリアルタイムでターゲット化する。

![](assets/merge-rule-triangle2.png)

## デバイス間のターゲット設定 {#cross-device-personalization}

例えば、ジョンが定期的に使用する3つのデバイスを所有して、休暇中のパッケージの掘り出し物を検索しているとします。パソコン[!DNL Device 1]()、スマートフォン([!DNL Device 2])、タブレット([!DNL Device 3])。 しかし、Johnは自分のデバイスを使ってパッケージの詳細を探します。

* 彼はノートパソコンを使って飛行機を探し、
* 彼はスマートフォンを使ってホテルを探す。
* 彼はタブレットを使ってガイドツアーを探します。

上記の3つのデバイスのすべてでJohnが認証されていない場合でも、 **[!UICONTROL Last Authenticated Profiles]****[!UICONTROL Profile Link Device Graph]** +ルールを使用すると、休日パッケージプロバイダーは、これらのデバイスをJohnの認証済みプロファイルに関連付けることができます（3つのデバイスすべてで最後に認証された人物であると仮定）。

![最終デバイスグラフ](assets/last-device-graph.png)

Audience Managerは、プロファイルの結合に参加したすべてのデバイスプロファイルをセグメントに対して修飾するので、3つのデバイスプロファイルはすべてセグメント化されます。 これによ [!UICONTROL Profile Link Device Graph] り、Audience Managerは3つすべてのデバイスにわたる行動を調べ、1つのデバイスプロファイルがそれ自体で適用されないセグメントをすべてのデバイスに適用することができます。

これによ [!UICONTROL Profile Merge Rule] り、マーケティング担当者は、個々のデバイスアクティビティではなく、ユーザーアクティビティに基づいて、1人のユーザーが所有するすべてのデバイスに一貫したエクスペリエンスを提供できます。

![デバイス間パーソナライゼーション](assets/cross-device-personalization.png)

>[!MORE_LIKE_THIS]
>
>* [ 外部デバイスグラフのユースケース](external-graph-use-cases.md)
>* [プロファイル結合ルールの一般的なユースケース](merge-rule-targeting-options.md)
>* [プロファイル結合ルール FAQ](../../faq/faq-profile-merge.md)

