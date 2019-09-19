---
description: Administration メニューのオプションを使用すると、Audience Manager ユーザーを作成してグループに割り当てることができます。また、制限（特性、セグメント、宛先、モデル）を表示することもできます。
keywords: rbac;RBAC;役割に基づく;ロールベース;ロールベースのアクセス制御
seo-description: Administration メニューのオプションを使用すると、Audience Manager ユーザーを作成してグループに割り当てることができます。また、制限（特性、セグメント、宛先、モデル）を表示することもできます。
seo-title: 管理
solution: Audience Manager
title: 管理
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: ht
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# 管理（RBACコントロール）{#administration}

![](assets/rbac-controls.png)

[!UICONTROL Administration] メニューのオプションを使用すると、Audience Manager ユーザーを作成してグループに割り当てることができます。また、制限（特性、セグメント、宛先、モデル）を表示することもできます。

[!DNL Audience Manager] をご使用のエンタープライズのお客様が必要としているのは、すべてのデータを 1 つのデータ管理プラットフォームで管理しながら、ビジネスユニットに応じて異なるデータ要素を表示できる機能です。グループ権限を使用してこれを実現でき、[!UICONTROL Role-Based Access Control]（[!UICONTROL RBAC]）とも呼ばれます。

[!DNL Audience Manager] は権限の割り当てにグループを使用します。権限はユーザー単位では割り当てられません。グループ権限はオブジェクト（特性やセグメントなど）、また、これらのオブジェクトに対して実行するアクション（編集や表示など）に関連付けられます。これらのコントロールは、Audience Manager REST API からも利用できます。[ユーザー管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)、[グループ管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)、および[権限管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API メソッドを参照してください。

## ユーザーの作成 {#create-users}

<!-- t_create_users.xml -->

[!DNL Audience Manager] でユーザーを作成し、ユーザーの詳細、ログインステータスを指定し、ユーザーをグループに割り当てます。

1. **[!UICONTROL Administration]**／**[!UICONTROL Users]** をクリックします。
1. ![](assets/icon_add.png) をクリックして、[!UICONTROL Create New User] ページを表示します。
1. 「**[!UICONTROL User Details]**」で、以下のフィールドに入力します。
   * **Username：** Audience Manager での一意のユーザー名を指定します。
   * **First Name：**&#x200B;ユーザーの名を指定します。
   * **Last Name：**&#x200B;ユーザーの姓を指定します。
   * **Email Address：**&#x200B;ユーザーの電子メールアドレスを指定します。[!DNL Audience Manager] は標準の通知をユーザーに送信しません。[!DNL Audience Manager] 管理者はユーザーの電子メールアドレスにアクセスできるので、必要に応じて手動でユーザーに電子メールを送信できます。例えば、ユーザーが自分のパスワードを忘れてしまった場合、このフィールドで指定された電子メールアドレスに、臨時のパスワードと、パスワードをリセットするための手順が送信されます。
   * **Phone Number：**&#x200B;ユーザーの電話番号を指定します。
   * **Is Admin：**[!DNL Audience Manager]このユーザーが 管理者であるかどうかを指定します。管理ユーザーはユーザーの管理（作成や編集など）とグループの管理（作成、権限の割り当てなど）ができます。管理者でないユーザーは、自分の電子メールアドレスの編集やパスワードのリセットなど、自分のユーザープロファイルのみ制御できます。詳しくは、[アカウント設定の編集](../../features/administration/edit-account-settings.md)を参照してください。
1. 「**[!UICONTROL Login]**」の下で、目的のステータスを選択します。
   * **Active：**[!DNL Audience Manager]アクティブなユーザーは にアクセスでき、グループメンバーシップによる権限が付与されます。
   * **Deactivated：**[!DNL Audience Manager]非アクティブなユーザーは にアクセスできず、権限もありません。ユーザーを非アクティブ化しても、ユーザー情報は [!DNL Audience Manager] に残るので、必要があれば再アクティブ化できます。ユーザーを削除すると、そのユーザーが将来 [!DNL Audience Manager] を使用する必要が出た場合は、ユーザーを作成し直さなければなりません。
   * **Expired：**&#x200B;ユーザーのパスワードが作成から 90 日を超えています。
   * **Pending：**&#x200B;パスワードのリセット後、またはアカウントの新規作成時の臨時パスワードがユーザーに対して発行されており、まだ正式なパスワードが設定されていません。
   * **Locked Out：**&#x200B;ログインの試行に 5 回失敗したので、ユーザーがロックアウトされています。
1. 「**[!UICONTROL Assigned Groups]**」の下のドロップダウンリストから、このユーザーを割り当てるグループを選択します。グループと権限について詳しくは、[グループの作成](../../features/administration/administration-overview.md#create-group)を参照してください。
1. 「**[!UICONTROL Save]**」をクリックします。

## グループの作成 {#create-group}

*グループ*&#x200B;とは、宛先、セグメントおよび特性の各オブジェクトに対するアクセス権を共有するユーザーの集まりです。グループのアクセス権を 1 つのオブジェクトのみに制限することも、様々なオブジェクトの組み合わせに対して幅広く付与することもできます。

<!-- t_create_groups.xml -->

グループを作成するには：

1. **[!UICONTROL Administration]**／**[!UICONTROL Groups]** をクリックします。
1. ![](assets/icon_add.png) をクリックして、[!UICONTROL Group Settings] ページを開きます。
1. [!UICONTROL Group Details]：
   * グループの名前を指定します。
   * グループについての簡単な説明を入力します。
1. 「[!UICONTROL Group Members]」で、「**[!UICONTROL Add Users]**」オプションからユーザーをクリックし、グループに追加します。
1. [!UICONTROL Group Permissions] で、**[!UICONTROL Add Object]** から[特性](../../features/traits/trait-details-page.md)、[セグメント](../../features/segments/segments-purpose.md)、または[宛先](../../features/destinations/destinations.md)を選択します。
選択したオブジェクトの権限ウィンドウが開きます。
1. グループメンバーに付与する権限のチェックボックスをオンにします。
1. *（オプション）*[ワイルドカード権限](../../features/administration/administration-overview.md#wild-card-permissions)をグループに割り当てます。
1. 「**[!UICONTROL Save Group]**」をクリックします。

## ワイルドカード権限{#wild-card-permissions}について 

[!UICONTROL Wild Card Permissions] でグループ権限を簡略化します。

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] では、セグメント、宛先、特性のいずれかに関連付けられた各データソースにグループメンバーが自動的にアクセスできます。比較すると、通常の権限では、特定のデータソースをこれらのオブジェクトのいずれかに割り当てることができるだけです。新規データソースを追加しても、グループメンバーはこれらの新規ソースにアクセスできません。

グループ権限を開き、これらの新規データソースをグループに割り当てる必要があります。[!UICONTROL Wild Card Permissions] を使用すると、手動によるこのデータソースの更新プロセスを回避できます。[!UICONTROL Wild Card Permissions] を持つグループは、明示的な認証をおこなわずに新規データソースにアクセスできます。

![](assets/wild-card.png)

以下に、各ワイルドカード権限について説明します。

**特性**

* `MAP_ALL_TRAITS_TO_MODELS`：ユーザーは、モデルのベースラインとして特性を選択できます。
* `EDIT_ALL_TRAITS`：ユーザーは、会社アカウント内で設定されているすべての特性を編集できます。
* `VIEW_ALL_TRAITS`：ユーザーは、会社アカウント内で設定されているすべての特性を閲覧できます。
* `DELETE_ALL_TRAITS`：ユーザーは、会社アカウント内で設定されているすべての特性を削除できます。
* `CREATE_ALL_ALGO_TRAITS`：ユーザーはアルゴリズムの特性を作成できます。
* `MAP_ALL_TO_SEGMENTS`： ユーザーは、会社に属する任意の特性をセグメントに追加できます。
* `CREATE_ALL_TRAITS`：ユーザーは特性を作成できます。

**レポート**

* `PTRREPORTS`：このワイルドカード権限は、まもなく Audience Manager UI から削除される、古くなった機能を表します。

**モデル**

* `VIEW_MODELS`：ユーザーは、会社に属するモデルを表示する権限を持っています。

**派生シグナル**

* `VIEW_DERIVED_SIGNALS`：ユーザーは、会社に属するすべての派生シグナルを表示できます。
* `CREATE_DERIVED_SIGNALS`：ユーザーは派生シグナルを作成できます。
* `EDIT_DERIVED_SIGNALS`：ユーザーは、会社に属するすべての派生シグナルを編集できます。
* `DELETE_DERIVED_SIGNALS`：ユーザーは、会社に属する任意の派生シグナルを削除できます。

**宛先**

* `EDIT_ALL_DESTINATIONS`：ユーザーは、会社アカウント内で設定されているすべての宛先を編集できます。
* `CREATE_DESTINATIONS`：ユーザーは宛先を作成できます。
* `VIEW_ALL_DESTINATIONS`：ユーザーは、会社アカウント内で設定されているすべての宛先を表示できます。
* `DELETE_ALL_DESTINATIONS`：ユーザーは、会社アカウント内で設定されているすべての宛先を削除できます。

**タグ**

* `VIEW_TAGS`：ユーザーはタグコンテナですべての操作（表示、作成、編集、削除）をおこなうことができます。

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS`：ユーザーは、Audience Lab ボテストグループですべての操作（表示、作成、編集、削除）を実行できます。

**セグメント**

* `CREATE_ALL_SEGMENTS`：ユーザーはセグメントを作成できます。
* `DELETE_ALL_SEGMENTS`：ユーザーは、会社アカウント内で設定されているすべてのセグメントを削除できます。
* `MAP_ALL_TO_DESTINATIONS`：ユーザーは、会社に属する任意のセグメントを宛先にマッピングできます。
* `EDIT_ALL_SEGMENTS`：ユーザーは、会社アカウント内で設定されているすべてのセグメントを編集できます。
* `MAP_ALL_SEGMENTS_TO_MODELS`：ユーザーは、モデルのベースラインとしてセグメントを選択できます。
* `VIEW_ALL_SEGMENTS`：ユーザーは、会社アカウント内で設定されているすべてのセグメントを表示できます。

**シグナル**

* `VIEW_ALL_SIGNALS`：ユーザーは、[Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md) でキャプチャされたすべてのシグナルを表示できます。