---
description: フォルダー特性を作成、編集および削除します。
keywords: フォルダー特性
seo-description: フォルダー特性を作成、編集および削除します。
seo-title: フォルダー特性の管理
solution: Audience Manager
title: フォルダー特性の管理
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# フォルダー特性の管理 {#manage-folder-traits}

フォルダー特性を作成、編集および削除します。

## フォルダー特性の作成 {#create-folder-trait}

A [!UICONTROL folder trait] is created automatically when you create a new folder in your taxonomy.

<!-- create-folder-trait.xml -->

1. Go to **[!UICONTROL Audience Data > Traits]** to navigate to the **Traits** dashboard.
1. [!UICONTROL Trait Storage] ウィンドウで、次のいずれかの操作を行います。

   * 「All Traits」テキストの上にマウスポインターを当て、新規のルートレベルフォルダーを追加します。
   * 既存の親フォルダーの下に、新規のサブフォルダーを追加します。
   ![](assets/folder_traits_create.PNG)

1. 「+」アイコンをクリックして、フォルダーを作成します。分類には、最大 2.000 個のフォルダーを作成できます。詳細については、[使用制限](../../features/administration/usage-limits.md) のドキュメントを参照してください。
1. フォルダーの名前を指定して「**Save**」をクリックします。例えば、Electronics という名前のフォルダーが「Electronics Folder Trait」というフォルダー特性を持ちます。特性ダッシュボードで新規のフォルダー特性を表示したり選択したりすることができます。
1. 新規のフォルダー特性は、[!DNL Audience Manager] で生成されたデータソースに自動的に割り当てられます。[!UICONTROL ロールベースのアクセス制御（[!DNL RBAC]）]による適切な権限を持つユーザーは、フォルダー特性編集ワークフローでデータソースを変更できます。[フォルダー特性の編集](../../features/traits/manage-folder-traits.md#edit-folder-trait)を参照してください。

## フォルダー特性の編集 {#edit-folder-trait}

[!UICONTROL folder trait]a.

<!-- edit-folder-trait.xml -->

1. [!UICONTROL Traits] ダッシュボードで、編集するフォルダー特性の **[!UICONTROL Actions]** 列の上にマウスポインターを置きます。
1. 鉛筆アイコンをクリックして、特性を編集します。

   ![](assets/folder_traits_edit_border.png)

1. **[!UICONTROL Edit]** このワークフローでは、フォルダー特性のデータソースを変更できます。目的のデータソースを選択して「**[!UICONTROL Save]**」をクリックします。データソースはドロップダウンボックスで [!DNL DPID] の数値順にソートされています。

   If your company uses [!UICONTROL Role-Based Access Rights (RBAC)], you or your users need [access permissions](../../features/traits/about-folder-traits.md#role-based-access-controls) to traits data sources.

>[!NOTE]
>
>フォルダー特性の名前は直接変更できません。フォルダー特性の名前を変更するには、[関連付けられているストレージフォルダーの名前を変更](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder)します。

## フォルダー特性の削除 {#delete-folder-trait}

フォルダー特性を削除するには、その特性が属するストレージフォルダーを削除します。

<!-- delete-folder-trait.xml -->

1. **Audience Data／Traits** を選択して、**特性**&#x200B;ダッシュボードに移動します。
1. [!UICONTROL Trait Storage] ウィンドウで、フォルダーの上にマウスポインターを置いて「X」アイコンをクリックすると、そのフォルダーが削除されます。

   ![手順の結果](assets/folder_traits_create.PNG)

>[!NOTE]
>
>セグメント式で使用されている場合は、フォルダー特性を削除できません。[特性ビュー](../../features/traits/trait-details-page.md)セクションに移動すれば、どのセグメントでフォルダー特性が使用されているかがわかります。その後、セグメント名をクリックして[セグメント概要ビュー](../../features/segments/segment-summary-view.md)を開けば、セグメント式から特性を削除できます。