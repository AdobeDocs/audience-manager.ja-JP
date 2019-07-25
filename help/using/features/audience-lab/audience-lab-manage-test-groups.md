---
description: この手順では、Audience Lab でテストグループを作成、編集または削除するための方法について説明します
seo-description: この手順では、Audience Lab でテストグループを作成、編集または削除するための方法について説明します
seo-title: テストグループの管理
solution: Audience Manager
title: テストグループの管理
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# テストグループの管理{#manage-test-groups}

この手順では、[!UICONTROL Audience Lab] でテストグループを作成、編集または削除するための方法について説明します。

## セグメントテストグループの作成 {#create-test-groups}

### 前提条件

<!-- create-test-group.xml -->

* **コンバージョン特性**&#x200B;を少なくとも 1 つセットアップしておく必要があります。コンバージョン特性は、[特性ビルダー](../../features/traits/create-onboarded-rule-based-traits.md)で、Event Type に **conversion** を選択することでセットアップできます。For more information on what conversion traits are and how to set them up, we prepared a [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) for you.

   >[!IMPORTANT]
   >
   >[フォルダー特性](../../features/traits/about-folder-traits.md) は **サポート** されていません [!UICONTROL Audience Lab]。フォルダー特性の [Event Type](../../features/traits/create-onboarded-rule-based-traits.md) を **conversion** に設定すると、その特定のフォルダー特性については [!UICONTROL Audience Lab] にデータが生成されません。

* For companies using [Role-Based Access Control](../../features/administration/administration-overview.md): Assign the [!UICONTROL Audience Lab] [wildcard permission](../../features/administration/administration-overview.md#wild-card-permissions) to **[!UICONTROL User Groups]** to provide access. この権限をユーザーに付与すると、テスト結果の作成や表示をおこなえます。ユーザーは、**読み取り**&#x200B;権限および&#x200B;**宛先へのマッピング**&#x200B;権限を持っているデータソースのセグメントのみ使用できます。また、ユーザーは、**読み取り**&#x200B;権限を持っているデータソースのコンバージョン特性のみ使用できます。さらに、ユーザーは、アクセスできる宛先のみ表示できます。そのため、[!DNL Audience Lab] のワイルドカード権限をグループに追加する前に、グループが以下の権限を持っていることを確認します。
   * 関係のあるコンバージョン特性の読み取り
   * テストに関係のあるセグメントの読み取りとマッピング
   * 関係のある宛先へのアクセス

To create a new [!UICONTROL Segment Test Group]:

1. Select **[!UICONTROL Create New Test Group]** in the [!UICONTROL Audience Lab] dashboard to start the wizard.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * **[!UICONTROL Test Group Name]** aおよびaに入力 **[!UICONTROL Description]**&#x200B;します。
   * Choose the **[!UICONTROL Base Segment]** either by navigating in the file browser or by typing in the search bar, confirm by pressing **[!UICONTROL Choose Segment.]**
   * テストグループをドラフトとして保存し、後で作業を再開することができます。
   * 選択したベースセグメントが他のテストグループで既に使用されている場合は、警告が表示されます。ベースセグメントを 2 回使用すると、どちらのテストのコンバージョン結果も誤ったものになる可能性があります。

1. **[!UICONTROL Allocate Test Segments]**

   * **最大 15 個のテストセグメント**&#x200B;を作成し、デバイスの割合を任意に配分することができます。
   * テストセグメントの名前をクリックすると、編集することができます。
   * 新規のテストセグメントが割り当てられると、全体が 100% になるように、自動的に割合が均等に配分されます。その後、割合を手動で編集できます。割合を編集した後でチェックボックスをクリックし、割合が合計 100% になることを確認します。そうでない場合は、次の手順に進めません。

1. **[!UICONTROL Set a Control Segment]**

   * セグメントの特定の一部を取っておいて対照グループとして使用する場合は、対照セグメントを選択します。対照グループを使用すると、作成したテストセグメントの影響をベンチマークと比較して確認することができます。
   * ドロップダウンリストで、テストセグメントを対照セグメントとして選択できます。または、対照セグメントを使用しない場合は、「**[!UICONTROL None]**」を選択します。
   * 完了したら、「**[!UICONTROL Next]」をクリックします。**

1. **[!UICONTROL Select Conversion Traits]**

   * コンバージョン特性ウィンドウで入力して、コンバージョン特性を追加します。これは&#x200B;**必須**&#x200B;手順であり、少なくとも 1 つのコンバージョン特性を追加しない限り、次の手順には進めません。
   * 最大 5 つのコンバージョン特性を任意に追加できます。
   * 他のテストグループに既に使用されているコンバージョン特性を選択した場合は、警告が表示されます。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 希望する宛先を検索フィールドに入力するか、ドロップダウン矢印を使用します。[!UICONTROL Audience Lab] のテストセグメントは、URL、Cookie、サーバー間のいずれかの宛先に送信することができます。
   * セグメントを宛先にドラッグアンドドロップします。
   * セグメントを宛先にドロップしてから、「**[!UICONTROL Destination Mapping Value]**」に入力します。
   * 同じテストセグメントを複数の宛先に送信でき、複数のテストセグメントを単一の宛先に追加できます。
   * 宛先は、[Data Export Controls](../../features/data-export-controls.md).
   * ユーザーには、自分が属する [RBAC ユーザーグループ](../../features/administration/administration-overview.md)でアクセス権が付与されている宛先のみが表示されます。
   * 最後に、テストグループの開始日を選択する必要があります。この日付は、テストグループが宛先に公開される期間の開始を示します。テストセグメントの無期限の比較をおこなう場合は、「**No End Date**」を選択します。
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] が認証されているプロファイルは、リアルタイムの宛先でのみサポートされています。その設定のプロファイル結合ルールを持つテストセグメントがファイルベースのサーバー間宛先に送信された場合は、オーディエンスが設定されない可能性があります。

   「**[!UICONTROL Next]**」をクリックして、テストグループを確認し最終決定します。

1. **[!UICONTROL Summary & Finalize]**

   * 前の手順で追加した情報を確認し、「**[!UICONTROL Finalize Group]**」を選択します。
   * テストグループを最終決定したら、テストグループの複製や削除が可能になりますが、編集はできません。
   >[!NOTE]
   >* 作成プロセスのどの時点でもテストグループを保存でき、後でウィザードに戻ることができます。The test group status will be **[!UICONTROL Draft]** and the test group will not send any data to destinations until you finalize the segment test group.
   >* ドラフトテストの場合は、**のメイン表示でテストグループカードの「[!UICONTROL Edit]**[!UICONTROL Audience Lab]」をクリックすれば、テストグループに戻って編集することができます。


## セグメントテストグループの編集 {#edit-test-groups}

[!UICONTROL Audience Lab] では、ドラフトテストグループのみ編集できます。[!UICONTROL Create Segment Test Group] ウィザードで、テストグループをドラフトとして保存し、後で作業を再開することができます。

1. [!UICONTROL Audience Lab] メインビューに移動します。
1. ドラフトテストグループを検索し、テストグループカードの「**[!UICONTROL Edit]**」コントロールを選択します。
1. [Create Segment Test Group](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) ウィザードを再開し、作業が完了したら「**[!UICONTROL Finalize Group]**」を選択します。

## セグメントテストグループの削除 {#delete-test-groups}

1. [!UICONTROL Audience Lab] メインビューに移動します。
1. 削除するテストグループを見つけます。次のいずれかをおこないます。

   * テストグループカードの「**[!UICONTROL Delete]**」コントロールをクリックします。
   * テストグループカードのテストグループタイトルをクリックして [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) ビューに移動し、タイトルバーにある「**[!UICONTROL Delete]**」コントロールをクリックします。

1. [完了したテストセグメント](../../features/audience-lab/audience-lab.md#status)の場合は、必要であれば CSV ファイルをダウンロードしてレポートを保存するように促す警告が表示されます。
