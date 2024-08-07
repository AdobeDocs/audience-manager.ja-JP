---
description: 新規データソースを作成するには、Audience Data／Data Sources／Add New の順に選択し、ここで説明している各セクションの手順を完了します。データソースを作成するには、管理者権限が必要です。
keywords: データソース; データソースの管理; Audience Manager データソース
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: データソースの管理
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 97%

---

# [!UICONTROL Data Sources]の管理  {#manage-data-sources}

## [!UICONTROL Data Source] の作成  {#create-data-source}

新しい[!UICONTROL data source]を作成するには、**[!UICONTROL Audience Data > Data Sources > Add New]** に移動して、ここに記載されているそれぞれの節の手順を完了します。[!UICONTROL data source]を作成するには、管理者権限が必要です。

<!-- create-datasource.xml -->

>[!TIP]
>
>各種コントロールの説明については、[データソースの設定とメニューオプション](../features/datasources-list-and-settings.md#settings-menu-options)を参照してください。

## [!UICONTROL Data Source] 詳細 {#details}

「[!UICONTROL Data Source Details]」セクションを完了するには：

1. [!UICONTROL data source] に名前を付けます。
1. *（オプション）*[!UICONTROL data source] の説明を入力します。簡潔な説明は、[!UICONTROL data source] の役割や目的を定義するのに役に立ちます。
1. [!UICONTROL integration code] を指定します。一般に、[!UICONTROL integration codes] はオプションです。統合コードが必要になるのは、次のいずれかの場合です。

   * [クロスデバイス対応データソースを作成](../features/profile-merge-rules/merge-rules-start.md#create-data-source)する。
   * [Adobe Experience Platform ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を使用する。
   * [プロファイル結合ルール](../features/profile-merge-rules/merge-rules-start.md)を使用する。

1. **[!UICONTROL ID Type]** を選択します。[!UICONTROL ID Type] オプションは次のとおりです。

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]**（[!UICONTROL Profile Merge Rule]を作成する場合は必要）。なお、一部のお客様では、これを選択すると **[!UICONTROL ID Definition]** オプションが表示されます。

   >[!NOTE]
   >
   >Audience Manager と Experience Platform 用にプロビジョニングされた各組織について、2 つのアプリ間でセグメント共有を設定していない場合でも、クロスデバイス対応データソースを作成すると、対応する [ID 名前空間](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ja#manage-namespaces)が Experience Platform で作成されます。

1. **[!UICONTROL ID Definition]** オプションを選択します。オプションは次のとおりです。

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[データ書き出しコントロール](../features/data-export-controls.md)は、[!UICONTROL data source] および [!UICONTROL destination] に適用できるオプションの分類ルールです。[!UICONTROL destination] へのデータ送信がデータのプライバシーや使用契約に違反する場合、データ送信を防止します。データ書き出しコントロールを使用しない場合は、「[!UICONTROL Data Export Controls]」セクションを省略してください。

## [!UICONTROL Data Source] 設定 {#settings}

これらの設定で [!UICONTROL data source] の識別、使用、共有の方法が決まります。また、受信データファイルのエラーレポートを有効にすることもできます。「[!UICONTROL Data Source Settings]」セクションを完了するには：

1. 「[!UICONTROL Data Source Setting]」チェックボックスを選択して、[!UICONTROL data source] にオプションを適用します。
2. 「**[!UICONTROL Save]**」をクリックします。

## データソースの削除 {#delete-data-source}

<!-- t_datasource_delete.xml -->

不要になった [!UICONTROL data source] データソースを削除します。

>[!NOTE]
>
>次の制限事項に注意してください。
>
>* [ アクティブオーディエンスまたはデータSource同期特性 ](../features/traits/client-activity-synced-audience-traits.md) を削除することはできません。
>* Adobe Analytics を使用しているお客様の場合： Audience Manager では、[!DNL Analytics] レポートスイートから自動的に作成されたデータソースを削除できません。これらのデータソースのマッピングを解除するには、[コアサービス](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html?lang=ja)を使用します。

1. **[!UICONTROL Audience Data]**／**[!UICONTROL Data Sources]** をクリックします。
1. 1 つ以上のデータソースの横のチェックボックスをオンにします。リストが長い場合、「[!UICONTROL Search]」のボックスを使用して、目的のデータソースを特定することができます。
1. ![](assets/icon_trash.png) をクリックして、削除を確定します。


>[!MORELIKETHIS]
>
>* [データソース設定とメニューオプション](../features/datasources-list-and-settings.md#settings-menu-options)
