---
description: プロファイル結合ルールを使用すると、セグメンテーションに使用するデータセットを管理できます。また、複数のデバイスにわたって個人を正確にターゲットに設定することができます。
seo-description: プロファイル結合ルールを使用すると、セグメンテーションに使用するデータセットを管理できます。また、複数のデバイスにわたって個人を正確にターゲットに設定することができます。
seo-title: プロファイル結合ルールの概要
solution: Audience Manager
title: プロファイル結合ルールの概要
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: a077726fe4878aeb7722586654c27769e92e0665
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 72%

---


# [!UICONTROL Profile Merge Rules] 概要 {#profile-merge-rules-overview}

[!UICONTROL Profile Merge Rules] を使用すれば、セグメント化に使用するデータセットを制御し、複数のデバイスにわたって正確にユーザーをターゲット設定できます。

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## 匿名プロファイルと認証済みプロファイルによるデータ収集とターゲティング {#data-collection-targeting}

通常、オーディエンスのセグメント化とターゲティングは、デバイス上のすべてのユーザーから収集されたデータに基づいておこないます。デバイスレベルのデータに基づくデータ収集とターゲティングには、いくつかのデメリットがあります。例えば、デバイスを共有する複数のユーザーを区別したり、複数のデバイスにまたがるユーザーを正確にターゲット化することができません。デバイスに基づくデータ収集は、デジタルマーケティングキャンペーンやクロスデバイスターゲティングには十分ではありません。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules]プロを使用すれば、[!DNL Audience Manager] がデータを収集してユーザーをターゲット化のためにセグメント化する方法が根本的に変わります。これにより、デバイスプロファイルと[認証済みプロファイル](../../reference/visitor-authentication-states.md)の 2 種類のプロファイルを操作できるようになります。

| プロファイルタイプ | 説明 |
|---|---|
| [!UICONTROL Device Profile] | A [!UICONTROL device profile] is tied to an ID for a given device such as a [!UICONTROL cookie] ID or mobile device ID.<br><br>以下のようなものがあります。<ul><li>[!UICONTROL Rule-based traits] ユーザが認証されない場合に実現。</li><li>[!UICONTROL Onboarded traits] を、サードパーティデータなどのデバイスIDに関連付け [!UICONTROL cookie-based]ることができます。</li></ul> |
| [!UICONTROL Authenticated Profile] | The [!UICONTROL authenticated profile] is tied to a user ID passed in when a person logs in to your site.<br><br>以下のようなものがあります。<ul><li>[!UICONTROL Rule-based traits] ユーザーが認証されたときに、デバイス間で収集されます。</li><li>[!UICONTROL Onboarded traits] 」が同じユーザーIDにリンクされているオフラインファイルに含まれていることを確認します。</li></ul> |

これらの各種のプロファイルにより、セグメント化に使用できるデータを制御します。For example, with an [authenticated profile](../../reference/visitor-authentication-states.md), you can build accurate [!UICONTROL segments] based on data from multiple devices for a single user. これにより、複数のデバイスにまたがってユーザーに対し一貫したブランドエクスペリエンスを提供できるようになります。[!DNL Audience Manager] は、個人がオンラインアクティビティに使用する様々なデバイスのマッピングを[認証済みプロファイル](../../reference/visitor-authentication-states.md)に保存することで、これを実現します。これらのマッピングは、[!UICONTROL Profile Link Device Graph] と呼ばれます。

![](assets/authenticated2.png)

## メリット {#advantages}

[!UICONTROL Profile Merge Rules] では、以下のことが可能です。

* [認証済みプロファイル](../../reference/visitor-authentication-states.md)、匿名プロファイル、またはその両方の組み合わせに基づいて、ユーザーをターゲット化する。
* デバイス間で特定の顧客をターゲット化する。
* 決定論的データに基づいてデバイスグラフを作成する。
* Fine tune the data in your [!UICONTROL segments] based on different profiles.
* オーディエンスに関する詳細なインサイトを得る。
