---
description: 新規データソースを作成するには、Audience Data／Data Sources／Add New の順に選択し、ここで説明している各セクションの手順を完了します。データソースを作成するには、管理者権限が必要です。
keywords: data sources;manage data source;audience manager data source
seo-description: 新規データソースを作成するには、Audience Data／Data Sources／Add New の順に選択し、ここで説明している各セクションの手順を完了します。データソースを作成するには、管理者権限が必要です。
seo-title: データソースの作成
solution: Audience Manager
title: データソースの管理
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: ht
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f
workflow-type: ht
source-wordcount: '408'
ht-degree: 100%

---


# データソースの管理 {#manage-data-sources}

## データソースの作成 {#create-data-source}

新しいデータソースを作成するには、**[!UICONTROL Audience Data > Data Sources > Add New]** の順に選択して、ここに記載されているそれぞれの節の手順を完了します。データソースを作成するには、管理者権限が必要です。

<!-- create-datasource.xml -->

>[!TIP]
>
>各種コントロールの説明については、[データソースの設定とメニューオプション](../features/datasources-list-and-settings.md#settings-menu-options)を参照してください。

## Data Source Details {#details}

「[!UICONTROL Data Source Details]」セクションを完了するには：

1. データソースの名前を入力します。
1. *（オプション）*&#x200B;データソースの説明を入力します。データソースの役割や目的を定義するのに、簡潔な説明が役に立ちます。
1. 統合コードを指定します。一般に、統合コードはオプションです。統合コードが必要になるのは、次のいずれかの場合です。

   * [クロスデバイス対応データソースを作成](../features/profile-merge-rules/merge-rules-start.md#create-data-source)する。
   * [Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を使用する。
   * [プロファイル結合ルール](../features/profile-merge-rules/merge-rules-start.md)を使用する。

1. **[!UICONTROL ID Type]** を選択します。「ID Type」のオプションは以下のとおりです。

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]**（[!UICONTROL Profile Merge Rule]を作成する場合は必要）。なお、一部のお客様では、これを選択すると **[!UICONTROL ID Definition]** オプションが表示されます。

1. **[!UICONTROL ID Definition]** オプションを選択します。オプションは次のとおりです。

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## データ書き出しコントロール {#export-controls}

[データ書き出しコントロール](../features/data-export-controls.md)は、データソースおよび宛先に適用できるオプションの分類ルールです。宛先へのデータ送信がデータのプライバシーや使用契約に違反する場合、データ送信を防止します。データ書き出しコントロールを使用しない場合は、「[!UICONTROL Data Export Controls]」セクションを省略してください。

## Data Source Settings {#settings}

これらの設定で、データソースの識別、使用、共有の方法が決まります。また、受信データファイルのエラーレポートを有効にすることもできます。「[!UICONTROL Data Source Settings]」セクションを完了するには：

1. 「[!UICONTROL Data Source Setting]」チェックボックスを選択して、データソースにオプションを適用します。
2. 「**[!UICONTROL Save]**」をクリックします。

>[!MORELIKETHIS]
>
>* [データソース設定とメニューオプション](../features/datasources-list-and-settings.md#settings-menu-options)


## データソースの削除 {#delete-data-source}

<!-- t_datasource_delete.xml -->

不要になったデータソースを削除します。

>[!NOTE]
>
>次の制限事項に注意してください。
>
>* [アクティブなオーディエンスやデータソースと同期された特性](../features/traits/client-activity-synced-audience-traits.md)は削除できません。
>* Adobe Analytics を使用しているお客様の場合： Audience Manager では、[!DNL Analytics] レポートスイートから自動的に作成されたデータソースを削除できません。これらのデータソースのマッピングを解除するには、[コアサービス](https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/core-services-landing.html)を使用します。


1. **[!UICONTROL Audience Data]**／**[!UICONTROL Data Sources]** をクリックします。
1. 1 つ以上のデータソースの横のチェックボックスをオンにします。リストが長い場合、「[!UICONTROL Search]」のボックスを使用して、目的のデータソースを特定することができます。
1. ![](assets/icon_trash.png) をクリックして、削除を確定します。