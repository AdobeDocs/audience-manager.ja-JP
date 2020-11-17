---
description: Administration メニューのオプションを使用すると、Audience Manager ユーザーを作成してグループに割り当てることができます。また、制限（特性、セグメント、宛先、モデル）を表示することもできます。
keywords: rbac;RBAC;role based;role-based;role-based access controls
seo-description: Administration メニューのオプションを使用すると、Audience Manager ユーザーを作成してグループに割り当てることができます。また、制限（特性、セグメント、宛先、モデル）を表示することもできます。
seo-title: 管理
solution: Audience Manager
title: 管理
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 65%

---


# [!UICONTROL Administration] （RBACの制御） {#administration}

![](assets/rbac-controls.png)

[!UICONTROL Administration] メニューのオプションを使用すると、Audience Manager ユーザーを作成してグループに割り当てることができます。また、制限（特性、セグメント、宛先、モデル）を表示することもできます。

[!DNL Audience Manager] をご使用のエンタープライズのお客様が必要としているのは、すべてのデータを 1 つのデータ管理プラットフォームで管理しながら、ビジネスユニットに応じて異なるデータ要素を表示できる機能です。グループ権限を使用してこれを実現でき、[!UICONTROL Role-Based Access Control]（[!UICONTROL RBAC]）とも呼ばれます。

[!DNL Audience Manager] は権限の割り当てにグループを使用します。権限はユーザー単位では割り当てられません。Group permissions are tied to objects ([!UICONTROL traits], segments, etc.) また、これらのオブジェクトに対して実行するアクション（編集や表示など）に関連付けられます。これらのコントロールは、Audience Manager REST API からも利用できます。[ユーザー管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)、[グループ管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)、および[権限管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API メソッドを参照してください。

## ユーザーの作成 {#create-users}

<!-- t_create_users.xml -->

[!DNL Audience Manager] でユーザーを作成し、ユーザーの詳細、ログインステータスを指定し、ユーザーをグループに割り当てます。

1. クリック **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. ![](assets/icon_add.png) をクリックして、[!UICONTROL Create New User] ページを表示します。
1. 「**[!UICONTROL User Details]**」で、以下のフィールドに入力します。
   * **[!UICONTROL Username]：** Audience Manager での一意のユーザー名を指定します。
   * **[!UICONTROL First Name]:** ユーザーの名を指定します。
   * **[!UICONTROL Last Name]:** ユーザーの姓を指定します。
   * **[!UICONTROL Email Address]:** ユーザーの電子メールアドレスを指定します。 [!DNL Audience Manager] は標準の通知をユーザーに送信しません。[!DNL Audience Manager] 管理者はユーザーの電子メールアドレスにアクセスできるので、必要に応じて手動でユーザーに電子メールを送信できます。例えば、ユーザーがパスワードを忘れた場合、このフィールドに指定した電子メールアドレスを使用して、一時パスワードとパスワードのリセット手順を送信します。
   * **[!UICONTROL Phone Number]:** ユーザーの電話番号を指定します。
   * **[!UICONTROL Is Admin]:** このユーザーが [!DNL Audience Manager] 管理者かどうかを指定します。 管理ユーザーはユーザーの管理（作成や編集など）とグループの管理（作成、権限の割り当てなど）ができます。管理者でないユーザーは、自分の電子メールアドレスの編集やパスワードのリセットなど、自分のユーザープロファイルのみ制御できます。詳しくは、[アカウント設定の編集](../../features/administration/edit-account-settings.md)を参照してください。
1. 「**[!UICONTROL Login]**」の下で、目的のステータスを選択します。
   * **[!UICONTROL Active]：**[!DNL Audience Manager]アクティブなユーザーは にアクセスでき、グループメンバーシップによる権限が付与されます。
   * **[!UICONTROL Deactivated]：**[!DNL Audience Manager]非アクティブなユーザーは にアクセスできず、権限もありません。ユーザーを非アクティブ化しても、ユーザー情報は [!DNL Audience Manager] に残るので、必要があれば再アクティブ化できます。ユーザーを削除すると、そのユーザーが将来 [!DNL Audience Manager] を使用する必要が出た場合は、ユーザーを作成し直さなければなりません。
   * **[!UICONTROL Expired]：**&#x200B;ユーザーのパスワードが作成から 90 日を超えています。
   * **[!UICONTROL Pending]：**&#x200B;パスワードのリセット後、またはアカウントの新規作成時の臨時パスワードがユーザーに対して発行されており、まだ正式なパスワードが設定されていません。
   * **[!UICONTROL Locked Out]:** 5誤ったログイン試行は、ユーザーをロックアウトします。
1. 「**[!UICONTROL Assigned Groups]**」の下のドロップダウンリストから、このユーザーを割り当てるグループを選択します。グループと権限について詳しくは、[グループの作成](../../features/administration/administration-overview.md#create-group)を参照してください。
1. **[!UICONTROL Save]**&#x200B;をクリックします。

## 指標をさらに制限する [!UICONTROL Group] {#create-group}

A *group* is a collection of users that share access rights to [!UICONTROL destination], [!UICONTROL segment], and [!UICONTROL trait] objects. グループのアクセス権を 1 つのオブジェクトのみに制限することも、様々なオブジェクトの組み合わせに対して幅広く付与することもできます。

<!-- t_create_groups.xml -->

グループを作成するには：

1. クリック **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
1. ![](assets/icon_add.png) をクリックして、[!UICONTROL Group Settings] ページを開きます。
1. [!UICONTROL Group Details]：
   * グループの名前を指定します。
   * グループについての簡単な説明を入力します。
1. 「[!UICONTROL Group Members]」で、「**[!UICONTROL Add Users]**」オプションからユーザーをクリックし、グループに追加します。
1. [!UICONTROL Group Permissions] で、[ から](../../features/traits/trait-details-page.md)特性[、](../../features/segments/segments-purpose.md)セグメント[、または](../../features/destinations/destinations.md)宛先&#x200B;**[!UICONTROL Add Object]**を選択します。
選択したオブジェクトの権限ウィンドウが開きます。
1. グループメンバーに付与する権限のチェックボックスをオンにします。
1. *（オプション）*[ワイルドカード権限](../../features/administration/administration-overview.md#wild-card-permissions)をグループに割り当てます。
1. **[!UICONTROL Save Group]**&#x200B;をクリックします。

## Understanding [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

[!UICONTROL Wild Card Permissions] でグループ権限を簡略化します。

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] グループメンバーに、 、 、 、 、に関連付けられた各データソースへの自動アクセス [!UICONTROL segment]を与え [!UICONTROL destination]ま [!UICONTROL trait]す。 By comparison, regular permissions only let you assign specific [!UICONTROL data sources] to the one of these objects. And, when you add new [!UICONTROL data sources], group members don&#39;t get access to those new sources.

You have to open the group permissions and assign those new [!UICONTROL data sources] to the group. [!UICONTROL Wild Card Permissions] この手動の [!UICONTROL data source] 更新プロセスを回避できます。 Groups with [!UICONTROL Wild Card Permissions] get access to new [!UICONTROL data sources] without explicit authorization.

![](assets/wild-card.png)

Read below for a description of what each [!UICONTROL wildcard permission] means:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS`  — ユーザーは、のベースライン [!UICONTROL traits] として選択でき [!UICONTROL models]ます。
* `EDIT_ALL_TRAITS` -会社アカウント内で設定されたすべての設定を編集で [!UICONTROL traits] きます。
* `VIEW_ALL_TRAITS`  — ユーザーは、会社アカウント内ですべての設定を表示できます。 [!UICONTROL traits]
* `DELETE_ALL_TRAITS` -会社アカウント内で設定された設定をすべて削除でき [!UICONTROL traits] ます。
* `CREATE_ALL_ALGO_TRAITS`  — ユーザーは、を作成でき [!UICONTROL algorithmic traits]ます。
* `MAP_ALL_TO_SEGMENTS` -会社に属する任意のをに追加 [!UICONTROL traits] でき [!UICONTROL segments]ます。
* `CREATE_ALL_TRAITS`  — ユーザーは、を作成でき [!UICONTROL traits]ます。

**[!UICONTROL Reports]**

* `PTRREPORTS`  — これ [!UICONTROL wildcard permission] は古い機能を意味し、近日中にAudience Managerユーザーインターフェイスから削除されます。

**[!UICONTROL Models]**

* `VIEW_MODELS` -会社に属する表示に対する権限 [!UICONTROL models] を持つユーザー。

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` -会社に属するすべてのものを表示でき [!UICONTROL derived signals] ます。
* `CREATE_DERIVED_SIGNALS`  — ユーザーは、を作成でき [!UICONTROL derived signals]ます。
* `EDIT_DERIVED_SIGNALS` -会社に属するすべての要素を編集でき [!UICONTROL derived signals] ます。
* `DELETE_DERIVED_SIGNALS` -会社に属するすべてのを削除でき [!UICONTROL derived signals] ます。

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` -会社アカウント内のすべての [!UICONTROL destinations] 設定を編集できます。
* `CREATE_DESTINATIONS`  — ユーザーは、を作成でき [!UICONTROL destinations]ます。
* `VIEW_ALL_DESTINATIONS`  — ユーザーは、会社アカウント内ですべての [!UICONTROL destinations] 設定を表示できます。
* `DELETE_ALL_DESTINATIONS` -会社アカウント内のすべての [!UICONTROL destinations] 設定を削除できます。

**[!UICONTROL Tags]**

* `VIEW_TAGS`  — ユーザーは、自分のすべての操作(表示、作成、編集、削除)を実行でき [!UICONTROL Tag Containers]ます。

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS`[!UICONTROL Audience Lab]：ユーザーは、 ボテストグループですべての操作（表示、作成、編集、削除）を実行できます。

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS`：ユーザーはセグメントを作成できます。
* `DELETE_ALL_SEGMENTS`：ユーザーは、会社アカウント内で設定されているすべてのセグメントを削除できます。
* `MAP_ALL_TO_DESTINATIONS`：ユーザーは、会社に属する任意のセグメントを宛先にマッピングできます。
* `EDIT_ALL_SEGMENTS`：ユーザーは、会社アカウント内で設定されているすべてのセグメントを編集できます。
* `MAP_ALL_SEGMENTS_TO_MODELS`：ユーザーは、モデルのベースラインとしてセグメントを選択できます。
* `VIEW_ALL_SEGMENTS`：ユーザーは、会社アカウント内で設定されているすべてのセグメントを表示できます。

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS`：ユーザーは、[Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md) でキャプチャされたすべてのシグナルを表示できます。

## ユースケース {#use-cases}

### ユーザーアクセスの監視 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] は、Audience Manager インスタンスにアクセスできるユーザー像を提供し、ユーザーのログインステータスを監視する際に役立ちます。

ビジネス要件に応じて、必要なときにユーザーアカウントを有効または無効にできます。

![monitor-user-access](assets/monitor-user-access.png)

### 機密性の高いアクセス保護の確保 [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

You can configure [!UICONTROL Role-Based Access Control] at [!UICONTROL trait], segment, and [!UICONTROL destination] level, for each user group.

この機能は、特定のデータセットの表示、作成、読み取り、書き込み、編集の方法を管理する場合や、ユーザーが使用できないデータセットへのアクセスを制限する場合に役立ちます。

![access-protection](assets/access-protection.png)
