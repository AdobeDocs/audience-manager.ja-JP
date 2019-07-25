---
description: フォルダー特性を使用すると、同じフォルダーとそのすべての子フォルダーに存在する特性を自動的に集計して、ターゲット設定可能なセグメントにすることができます。
keywords: セグメントサイズの見積もり;SSE
seo-description: フォルダー特性を使用すると、同じフォルダーとそのすべての子フォルダーに存在する特性を自動的に集計して、ターゲット設定可能なセグメントにすることができます。
seo-title: フォルダー特性について
solution: Audience Manager
title: フォルダー特性について
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# フォルダー特性：詳細 {#folder-traits-about}

[!UICONTROL Folder traits] を使用すると、同じフォルダーおよびすべての子フォルダーにある特性を、ターゲットセグメントに自動的に集約できます。

## フォルダー特性{#benefits}を使用するメリット 

A [!UICONTROL folder trait] contains all the traits in a parent folder and its associated child folders. これにより、異なるフォルダーレベルのユーザーを自動でセグメント化し、ターゲットにできます。例えば、次のようなフォルダー構造があったとします。

`*`電子機器（親）

`*` ラップトップ（子）

`*` ブランド（孫）

[!UICONTROL Folder traits] （親フォルダの名前に基づいて）自動的に作成 [!DNL Electronics][!UICONTROL Folder Trait] されたフォルダー内のすべてのユーザーを資格設定します。また、同じプロセスがファイル構造の下のレベルに向かって繰り返されます。In this case, folder traits capture all of the users in the Laptops and Brands folders in an automatically created Laptops [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] は、セグメント式で選択可能です。Selecting a [!UICONTROL folder trait] is equivalent to selecting all the traits within that folder and its subfolders with an [!UICONTROL OR] grouping.

![](assets/folder-traits-compare-border.jpg)

## フォルダー特性の適合 - 最新性と頻度 {#folder-traits-realization}

フォルダー特性の頻度は、そのフォルダーおよびサブフォルダー内の特性が適合した合計数となります。下の図は、自動車フォルダー内の特性 A、B および C を示します。各特性の適合数は以下とおりであるとします。

* 特性 A：5
* 特性 B：1
* 特性 C：1

In this case, the [!DNL ]Automobile [!UICONTROL Folder Trait] has 7 realizations.

![](assets/folder_traits_rollup_border.png)

## フォルダー特性のレポート {#folder-traits-reporting}

[!UICONTROL Folder traits] その下のフォルダー構造の特性からすべてのユーザーを取り込みます。あるフォルダーから別のフォルダーに特性を移動すると、その変更は、特性ルールの変更と同様に、[データ収集サーバー](../../reference/system-components/components-data-collection.md)に反映されます。次のレポート実行のタイミングで、すべての日付範囲（1、7、14、30、60、90、全期間）にわたってこの変更が反映されるようレポートが更新されます。これより前にレポートされた数値は変更されません。

## ロールベースのアクセス制御（RBAC）権限 {#role-based-access-controls}

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), your users with the appropriate [!UICONTROL RBAC] permissions are able to change the data source associated to the [!UICONTROL folder trait]. ユーザーは以下のいずれかを持つグループに属している必要があります。

* 特性のデータソースに対する `READ` および `WRITE` グループ権限。
* 特性のデータソースに対する `VIEW_ALL_TRAITS` および `EDIT_ALL_TRAITS` ワイルドカード権限。

[!UICONTROL RBAC] 権限の割り当て方法については、[管理に関するドキュメント](../../features/administration/administration-overview.md#create-group)を参照してください。

## 制限およびその他の考慮事項 {#limits}

| 項目 | 説明 |
|---|---|
| 特性タイプ | [!UICONTROL Onboarded traits] また、最大1回 [!UICONTROL algorithmic traits] の実現により、最大1回の実現 [!UICONTROL folder trait]に貢献しています。 |
| フォルダー間での特性の移動 | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second [!UICONTROL folder trait]. つまり、フォルダーから特性を削除または移動した場合、その特性の母集団のユーザーは、セグメントの式でそのフォルダー特性を使用しているセグメントから解除されます。<br> Adobe AnalyticsセグメントまたはレポートスイートをExperience Cloud組織にマッピングする場合、Audience Managerは、対応する新しい、対応する、読み取り専用のセグメントおよび特性を自動的に作成します。Audience Managerからこれらの特性の記憶場所を編集または変更することはできません。ただし、マッピングされたAdobe Analyticsセグメントまたはレポートスイートで実行する変更は、Audience Managerに反映されます。 |
| システム変数 | [!UICONTROL Folder traits]`d_sid` パラメーターを使用したイベント呼び出しでは実現できません。 |
| レポート | [!UICONTROL Folder traits] は自動計算された特性であり、表示 **[!UICONTROL Overlap Reports]**&#x200B;されません。 |