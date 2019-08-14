---
description: Administration メニューのオプションを使用すると、Audience Manager ユーザーを作成してグループに割り当てることができます。また、制限（特性、セグメント、宛先およびモデル）も表示できます。
keywords: rbac;RBAC;役割に基づく;ロールベース;ロールベースのアクセス制御
seo-description: Administration メニューのオプションを使用すると、Audience Manager ユーザーを作成してグループに割り当てることができます。また、制限（特性、セグメント、宛先およびモデル）も表示できます。
seo-title: 管理
solution: Audience Manager
title: 管理
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# 管理（RBACコントロール） {#administration}

![](assets/rbac-controls.png)

[!UICONTROL Administration] メニューのオプションを使用すると、Audience Manager ユーザーを作成してグループに割り当てることができます。また、制限（特性、セグメント、宛先およびモデル）も表示できます。

[!DNL Audience Manager] をご使用のエンタープライズのお客様が必要としているのは、すべてのデータを 1 つのデータ管理プラットフォームで管理しながら、ビジネスユニットに応じて異なるデータ要素を表示できる機能です。これを行うには、グループ権限（ [!UICONTROL Role-Based Access Control] （[!UICONTROL RBAC]）とも呼ばれます）を使用します。

[!DNL Audience Manager] は権限の割り当てにグループを使用します。権限はユーザー単位では割り当てられません。グループ権限はオブジェクト（特性やセグメントなど）、また、これらのオブジェクトに対して実行するアクション（編集や表示など）に関連付けられます。これらのコントロールは、Audience Manager REST APIからも利用できます。[User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)、 [Group Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)および [Permissions Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) APIメソッドを参照してください。

## ユーザーの作成 {#create-users}

<!-- t_create_users.xml -->

[!DNL Audience Manager] でユーザーを作成し、ユーザーの詳細、ログインステータスを指定し、ユーザーをグループに割り当てます。

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Click ![](assets/icon_add.png) to display the [!UICONTROL Create New User] page.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Username：** Audience Manager での一意のユーザー名を指定します。
   * **First Name：**&#x200B;ユーザーの名を指定します。
   * **Last Name：**&#x200B;ユーザーの姓を指定します。
   * **電子メールアドレス：**&#x200B;ユーザーの電子メールアドレスを指定します。[!DNL Audience Manager] は標準の通知をユーザーに送信しません。[!DNL Audience Manager] 管理者はユーザーの電子メールアドレスにアクセスできるので、必要に応じて手動でユーザーに電子メールを送信できます。例えば、ユーザーが自分のパスワードを忘れてしまった場合、このフィールドで指定された電子メールアドレスに、臨時のパスワードと、パスワードをリセットするための手順が送信されます。
   * **Phone Number：**&#x200B;ユーザーの電話番号を指定します。
   * **Is Admin：**[!DNL Audience Manager]このユーザーが 管理者であるかどうかを指定します。管理ユーザーはユーザーの管理（作成や編集など）とグループの管理（作成、権限の割り当てなど）ができます。管理者でないユーザーは、自分の電子メールアドレスの編集やパスワードのリセットなど、自分のユーザープロファイルのみ制御できます。詳しくは、[アカウント設定の編集](../../features/administration/edit-account-settings.md)を参照してください。
1. 「**[!UICONTROL Login]**」の下で、目的のステータスを選択します。
   * **Active：**[!DNL Audience Manager]アクティブなユーザーは にアクセスでき、グループメンバーシップによる権限が付与されます。
   * **Deactivated：**[!DNL Audience Manager]非アクティブなユーザーは にアクセスできず、権限もありません。ユーザーを非アクティブ化しても、ユーザー情報は [!DNL Audience Manager] に残るので、必要があれば再アクティブ化できます。ユーザーを削除すると、そのユーザーが将来 [!DNL Audience Manager] を使用する必要が出た場合は、ユーザーを作成し直さなければなりません。
   * **Expired：**&#x200B;ユーザーのパスワードが作成から 90 日を超えています。
   * **Pending：**&#x200B;パスワードのリセット後、またはアカウントの新規作成時の臨時パスワードがユーザーに対して発行されており、まだ正式なパスワードが設定されていません。
   * **Locked Out：**&#x200B;ログインの試行に 5 回失敗したので、ユーザーがロックアウトされています。
1. 「**[!UICONTROL Assigned Groups]**」の下のドロップダウンリストから、このユーザーを割り当てるグループを選択します。グループと権限について詳しくは、[グループの作成](../../features/administration/administration-overview.md#create-group)を参照してください。
1. **[!UICONTROL Save]**&#x200B;をクリックします。

## グループの作成 {#create-group}

*グループ*&#x200B;とは、送信先、セグメントおよび特性の各オブジェクトに対するアクセス権を共有するユーザーの集まりです。グループのアクセス権を 1 つのオブジェクトのみに制限することも、様々なオブジェクトの組み合わせに対して幅広く付与することもできます。

<!-- t_create_groups.xml -->

グループを作成するには：

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Click  ![](assets/icon_add.png) to open the [!UICONTROL Group Settings] page.
1.  [!UICONTROL Group Details]:
   * グループの名前を指定します。
   * グループについての簡単な説明を入力します。
1. In [!UICONTROL Group Members], click a user from **[!UICONTROL Add Users]** options to add them to the group.
1. In [!UICONTROL Group Permissions], select a [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md), or [destination](../../features/destinations/destinations.md) from **[!UICONTROL Add Object]**.
選択したオブジェクトの権限ウィンドウが開きます。
1. グループメンバーに付与する権限のチェックボックスをオンにします。
1. *（オプション）*[ワイルドカード権限](../../features/administration/administration-overview.md#wild-card-permissions)をグループに割り当てます。
1. **[!UICONTROL Save Group]**&#x200B;をクリックします。

## ワイルドカード権限{#wild-card-permissions}について 

グループ権限管理を簡略化 [!UICONTROL Wild Card Permissions]します。

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] グループメンバーに、セグメント、宛先または特性に関連付けられている各データソースへの自動アクセス権を付与します。これにより、通常の権限では、特定のデータソースをこれらのオブジェクトの1つに割り当てることしかできません。新規データソースを追加しても、グループメンバーはこれらの新規ソースにアクセスできません。

グループ権限を開き、これらの新規データソースをグループに割り当てる必要があります。[!UICONTROL Wild Card Permissions] を使用すると、この手動データソースの更新プロセスを回避できます。Groups with [!UICONTROL Wild Card Permissions] get access to new data sources without explicit authorization.

![](assets/wild-card.png)

以下に、各ワイルドカード権限について説明します。

**特性**

* `MAP_ALL_TRAITS_TO_MODELS` - ユーザーは、モデルのベースラインとして特性を選択できます。
* `EDIT_ALL_TRAITS` - ユーザーは、会社アカウント内で設定されているすべての特性を編集できます。
* `VIEW_ALL_TRAITS` - ユーザーは、会社アカウント内で設定されているすべての特性を表示できます。
* `DELETE_ALL_TRAITS` - ユーザーは、会社アカウント内で設定されているすべての特性を削除できます。
* `CREATE_ALL_ALGO_TRAITS` - ユーザーはアルゴリズムの特性を作成できます。
* `MAP_ALL_TO_SEGMENTS` - ユーザーは、会社に属する特性のいずれかをセグメントに追加できます。
* `CREATE_ALL_TRAITS` - ユーザーは特性を作成できます。

**レポート**

* `PTRREPORTS` - このワイルドカード権限は、古くなった機能を指し、まもなくAudience Manager UIから削除されます。

**モデル**

* `VIEW_MODELS` - ユーザーは、会社に属するモデルを表示する権限を持っています。

**派生シグナル**

* `VIEW_DERIVED_SIGNALS` - ユーザーは、会社に属するすべての派生シグナルを表示できます。
* `CREATE_DERIVED_SIGNALS` - ユーザーは派生シグナルを作成できます。
* `EDIT_DERIVED_SIGNALS` - ユーザーは、会社に属するすべての派生シグナルを編集できます。
* `DELETE_DERIVED_SIGNALS` - ユーザーは、会社に属する派生シグナルを削除できます。

**送信先**

* `EDIT_ALL_DESTINATIONS` - ユーザーは、会社アカウント内で設定されているすべての宛先を編集できます。
* `CREATE_DESTINATIONS` - ユーザーは宛先を作成できます。
* `VIEW_ALL_DESTINATIONS` - ユーザーは、会社アカウント内で設定されているすべての宛先を表示できます。
* `DELETE_ALL_DESTINATIONS` - ユーザーは、会社アカウント内で設定されているすべての宛先を削除できます。

**タグ**

* `VIEW_TAGS` - ユーザーはタグコンテナですべての操作（表示、作成、編集、削除）を行うことができます。

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - ユーザーは、オーディエンスラボテストグループですべて（表示、作成、編集、削除）を実行できます。

**セグメント**

* `CREATE_ALL_SEGMENTS` - ユーザーはセグメントを作成できます。
* `DELETE_ALL_SEGMENTS` - ユーザーは、会社アカウント内で設定されているすべてのセグメントを削除できます。
* `MAP_ALL_TO_DESTINATIONS` - ユーザーは、会社に属する任意のセグメントを宛先にマップできます。
* `EDIT_ALL_SEGMENTS` - ユーザーは、会社アカウント内で設定されているすべてのセグメントを編集できます。
* `MAP_ALL_SEGMENTS_TO_MODELS` - ユーザーは、モデルのベースラインとしてセグメントを選択できます。
* `VIEW_ALL_SEGMENTS` - ユーザーは、会社アカウント内で設定されているすべてのセグメントを表示できます。

**シグナル**

* `VIEW_ALL_SIGNALS` - ユーザーは、Data Explorerで [キャプチャされたすべてのシグナルを表示](/help/using/features/data-explorer/data-explorer-overview.md)できます。