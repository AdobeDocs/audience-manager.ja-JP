---
description: フォルダー特性を作成、編集および削除します。
keywords: フォルダー特性;フォルダー特性;フォルダー特性;フォルダー特性
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: フォルダー特性の管理
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
TQID: https://experienceleague.adobe.com/YScTXBbG6HeRUviBsC2Rl9L7QdOXe-ciVwWBQfbPOzs
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 100%

---

# フォルダー特性の管理 {#manage-folder-traits}

フォルダー特性を作成、編集および削除します。

## フォルダー特性の作成 {#create-folder-trait}

分類に新規フォルダーを作成すると、[!UICONTROL folder trait] が自動的に作成されます。

<!-- create-folder-trait.xml -->

1. **[!UICONTROL Audience Data > Traits]** へ進み、**Traits** ダッシュボードに移動します。
1. [!UICONTROL Trait Storage] ウィンドウで、

   * 「All Traits」テキストの上にマウスポインターを当て、新規のルートレベルフォルダーを追加します。
   * 既存の親フォルダーの下に、新規のサブフォルダーを追加します。

   ![](assets/folder_traits_create.PNG)

1. 「+」アイコンをクリックして、フォルダーを作成します。分類には、最大 2000 個のフォルダーを作成できます。詳細については、[使用制限](../../features/administration/usage-limits.md) のドキュメントを参照してください。
1. フォルダーの名前を指定して「**Save**」をクリックします。例えば、Electronics という名前のフォルダーが「Electronics Folder Trait」というフォルダー特性を持ちます。特性ダッシュボードで新規のフォルダー特性を表示したり選択したりすることができます。
1. 新規のフォルダー特性は、[!DNL Audience Manager] で生成されたデータソースに自動的に割り当てられます。適切な[!UICONTROL Role-Based Access Control]（[!DNL RBAC]）権限を持つユーザーは、フォルダー特性編集ワークフローでデータソースを変更できます。[フォルダー特性の編集](../../features/traits/manage-folder-traits.md#edit-folder-trait)を参照してください。

## フォルダー特性の編集 {#edit-folder-trait}

[!UICONTROL folder trait] の編集方法について説明します。

<!-- edit-folder-trait.xml -->

1. [!UICONTROL Traits] ダッシュボードで、編集するフォルダー特性の **[!UICONTROL Actions]** 列の上にマウスポインターを置きます。
1. 鉛筆アイコンをクリックして、特性を編集します。

   ![](assets/folder_traits_edit_border.png)

1. **[!UICONTROL Edit]**&#x200B;ワークフローでは、フォルダー特性のデータソースを変更できます。目的のデータソースを選択して「**[!UICONTROL Save]**」をクリックします。データソースはドロップダウンボックスで [!DNL DPID] の数値順にソートされています。

   [!UICONTROL Role-Based Access Rights (RBAC)]を使用している企業の場合は、ユーザーは特性データソースへの[アクセス権限](../../features/traits/about-folder-traits.md#role-based-access-controls)が必要になります。

>[!NOTE]
>
>フォルダー特性の名前は直接変更できません。フォルダー特性の名前を変更するには、[関連付けられているストレージフォルダーの名前を変更](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder)します。

## フォルダー特性の削除 {#delete-folder-trait}

フォルダー特性を削除するには、その特性が属するストレージフォルダーを削除します。

<!-- delete-folder-trait.xml -->

1. **Audience Data／Traits** を選択して、**Traits** ダッシュボードに移動します。
1. [!UICONTROL Trait Storage] ウィンドウで、フォルダーの上にマウスポインターを置いて「X」アイコンをクリックすると、そのフォルダーが削除されます。

   ![手順の結果](assets/folder_traits_create.PNG)

>[!NOTE]
>
>セグメント式で使用されている場合は、フォルダー特性を削除できません。[特性ビュー](../../features/traits/trait-details-page.md)セクションに移動すれば、どのセグメントでフォルダー特性が使用されているかがわかります。その後、セグメント名をクリックして[セグメント概要ビュー](../../features/segments/segment-summary-view.md)を開けば、セグメント式から特性を削除できます。
