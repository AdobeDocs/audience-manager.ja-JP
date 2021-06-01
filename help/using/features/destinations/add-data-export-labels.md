---
description: データ書き出しラベルは、データソースに設定する書き出しコントロールと連携して動作します。データ書き出しラベルによって、セグメントへの制限された特性の追加や、宛先へのセグメントデータの送信が防止されます。Cookie や URL の新規または既存の宛先に複数の書き出しラベルを設定できます。
seo-description: データ書き出しラベルは、データソースに設定する書き出しコントロールと連携して動作します。データ書き出しラベルによって、セグメントへの制限された特性の追加や、宛先へのセグメントデータの送信が防止されます。Cookie や URL の新規または既存の宛先に複数の書き出しラベルを設定できます。
seo-title: 宛先へのデータ書き出しコントロールの追加
solution: Audience Manager
title: 宛先へのデータ書き出しコントロールの追加
feature: データ書き出しコントロール
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 100%

---

# 宛先へのデータ書き出しラベルの追加 {#add-data-export-labels}

[!DNL Data Export Labels]はデータソースで設定された [!DNL Export Controls] と連携します。[!DNL Data Export Labels] によって、セグメントへの制限された特性の追加や、宛先へのセグメントデータの送信が防止されます。[!DNL cookie] や [!DNL URL] の新規または既存の宛先に複数の書き出しラベルを設定できます。

>[!NOTE]
>
>書き出しラベルを追加するには、管理者権限&#x200B;*または*&#x200B;宛先の作成や編集をおこなうための十分な権限が必要です。

<!-- t_export_labels.xml -->

書き出しラベルを宛先に追加するには：

1. クリック **[!UICONTROL Audience Data]**:
   * 新しい宛先の場合：**[!UICONTROL Create New Destination]**&#x200B;をクリックします。データ書き出しラベルを選択する前に、「[!UICONTROL Basic Information]」セクションに入力します。[Cookie の宛先の作成](../../features/destinations/create-cookie-destination.md)または [URL 宛先の作成](../../features/destinations/create-url-destination.md)を参照してください。
   * 既存の宛先の場合：「[!DNL Search]」ボックスで宛先を検索するか、リストをスクロールし、宛先名をクリックして開きます。
1. 「[!DNL Data Export Label]」を選択します。書き出し制限を設定しない場合は、チェックボックスをオフにします。書き出しラベルには次のようなオプションがあります。
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >書き出し制限は、データソースに[書き出しコントロールの照合](../../features/data-export-controls.md)が設定されていないと機能しません。
1. 「**[!UICONTROL Save]**」をクリックします。

>[!MORELIKETHIS]
>
>* [データソースの作成](../../features/manage-datasources.md#create-data-source)

