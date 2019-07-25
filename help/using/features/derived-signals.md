---
description: 派生シグナルは、認識済みの特性に基づいてサイト訪問者を追加の特性の対象として認定されます。つまり、追加の特性認定は、現在認定されている特性から派生させることができます。これは、ユーザーにとってその別の特性がまったくの新規特性である場合でも同様です。
seo-description: 派生シグナルは、認識済みの特性に基づいてサイト訪問者を追加の特性の対象として認定されます。つまり、追加の特性認定は、現在認定されている特性から派生させることができます。これは、ユーザーにとってその別の特性がまったくの新規特性である場合でも同様です。
seo-title: 派生シグナル
solution: Audience Manager
title: 派生シグナル
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# 派生シグナル {#derived-signals}

A [!UICONTROL derived signal] qualifies site visitors for additional traits based on a trait they've already seen. つまり、追加の特性認定は、現在認定されている特性から派生させることができます。これは、ユーザーにとってその別の特性がまったくの新規特性である場合でも同様です。

<!-- c_tb_derived_signal.xml -->

## 派生シグナルの目的

[!DNL Audience Manager] では、指定された他のシグナルまたは特性に対するイベント呼び出し中に渡されたシグナル（または特性ルール）間の関係を作成できます。For example, assume an event call passes in a signal composed of the key-value [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] は、その信号を [!UICONTROL derived signals] ツールで作成した他のものに接続します。Although the associated signals can be any key-values you specify, they are most useful when linked to existing signals already set up as [!UICONTROL Trait Builder] rules. For example, in the illustration below, when a user action fires the signal [!DNL "product = new car"] that user can also qualify for traits defined by the target key and value signals.

![](assets/derived_signal_example.png)

## 派生シグナルの場所

Create and manage [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** from the sidebar navigation.

## 派生シグナルの作成 {#create}

<!-- t_tb_create_derived.xml -->

To create a [!UICONTROL derived signal]:

1. Select **[!UICONTROL Derived Signals]** from the [!UICONTROL Tools] menu.
1. 以下の項目を指定します。
   * *（オプション）*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. **[!UICONTROL Add Signal]**&#x200B;をクリックします。

>[!NOTE]
>
>[!UICONTROL Source Key][!UICONTROL Source Value]、 [!UICONTROL Target Key][!UICONTROL Target Value] およびフィールドの文字制限は228文字です。

## 派生シグナルの編集 {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. シグナルにカーソルを移動し、「**[!UICONTROL Edit]**」をクリックします。
2. 必要なコード、キーまたは値を変更してから、「**[!UICONTROL Save]**」をクリックします。

## 派生シグナルの削除 {#delete}

<!-- t_tb_delete_derived.xml -->

To delete a [!UICONTROL derived signal], hover over the signal, then click **[!UICONTROL Delete]**.
