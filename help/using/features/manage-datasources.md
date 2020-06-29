---
description: 新規データソースを作成するには、Audience Data／Data Sources／Add New の順に選択し、ここで説明している各セクションの手順を完了します。データソースを作成するには、管理者権限が必要です。
keywords: data sources;manage data source;audience manager data source
seo-description: 新規データソースを作成するには、Audience Data／Data Sources／Add New の順に選択し、ここで説明している各セクションの手順を完了します。データソースを作成するには、管理者権限が必要です。
seo-title: データソースの作成
solution: Audience Manager
title: データソースの管理
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 73%

---


#  [!UICONTROL Data Sources]{#manage-data-sources}

## 指標をさらに制限する [!UICONTROL Data Source] {#create-data-source}

To create a new [!UICONTROL data source], go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. Administrator permissions are required to create a [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>各種コントロールの説明については、[データソースの設定とメニューオプション](../features/datasources-list-and-settings.md#settings-menu-options)を参照してください。

## [!UICONTROL Data Source] 詳細 {#details}

「[!UICONTROL Data Source Details]」セクションを完了するには：

1. [!UICONTROL data source] に名前を付けます。
1. *（オプション）*[!UICONTROL data source] の説明を入力します。A concise description helps you define the role or purpose of the [!UICONTROL data source].
1. を指定し [!UICONTROL integration code]ます。 一般に、 [!UICONTROL integration codes] はオプションです。 統合コードが必要になるのは、次のいずれかの場合です。

   * [クロスデバイス対応データソースを作成](../features/profile-merge-rules/merge-rules-start.md#create-data-source)する。
   * [Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を使用する。
   * [プロファイル結合ルール](../features/profile-merge-rules/merge-rules-start.md)を使用する。

1. **[!UICONTROL ID Type]** を選択します。[!UICONTROL ID Type] 次のオプションがあります。

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]**（[!UICONTROL Profile Merge Rule]を作成する場合は必要）。なお、一部のお客様では、これを選択すると **[!UICONTROL ID Definition]** オプションが表示されます。

1. **[!UICONTROL ID Definition]** オプションを選択します。オプションは次のとおりです。

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[データエクスポートコントロール](../features/data-export-controls.md) (Data Export Controls [!UICONTROL data source] )は、およびに適用できるオプションの分類ルール [!UICONTROL destination]です。 They prevent you from sending data to a [!UICONTROL destination] when that action violates a data privacy or use agreement. データ書き出しコントロールを使用しない場合は、「[!UICONTROL Data Export Controls]」セクションを省略してください。

## [!UICONTROL Data Source] 設定 {#settings}

These settings determine how a [!UICONTROL data source] is identified, used, and shared. また、受信データファイルのエラーレポートを有効にすることもできます。「[!UICONTROL Data Source Settings]」セクションを完了するには：

1. Select a [!UICONTROL Data Source Setting] check box to apply an option to your [!UICONTROL data source].
2. 「**[!UICONTROL Save]**」をクリックします。

## データソースの削除 {#delete-data-source}

<!-- t_datasource_delete.xml -->

Delete a [!UICONTROL data source] that you no longer need.

>[!NOTE]
>
>次の制限事項に注意してください。
>
>* 削除できない[アクティブなオーディエンスやデータソースと同期された特性](../features/traits/client-activity-synced-audience-traits.md)は削除できません。
>* Adobe Analytics を使用しているお客様の場合： Audience Manager では、[!DNL Analytics] レポートスイートから自動的に作成されたデータソースを削除できません。これらのデータソースのマッピングを解除するには、[コアサービス](https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/core-services-landing.html)を使用します。


1. **[!UICONTROL Audience Data]**／**[!UICONTROL Data Sources]** をクリックします。
1. 1 つ以上のデータソースの横のチェックボックスをオンにします。リストが長い場合、「[!UICONTROL Search]」のボックスを使用して、目的のデータソースを特定することができます。
1. ![](assets/icon_trash.png) をクリックして、削除を確定します。


>[!MORELIKETHIS]
>
>* [データソース設定とメニューオプション](../features/datasources-list-and-settings.md#settings-menu-options)