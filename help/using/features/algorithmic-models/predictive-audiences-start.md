---
description: 予測オーディエンスを使用すると、不明なオーディエンスをリアルタイムで別の人物に分類し、データサイエンスを使用できます。
seo-description: 予測オーディエンスを使用すると、不明なオーディエンスをリアルタイムで別の人物に分類し、データサイエンスを使用できます。
seo-title: 予測オーディエンス
solution: Audience Manager
title: オーディエンスマネージャーの予測オーディエンス
translation-type: tm+mt
source-git-commit: 8259f07c91efa0efd88e8f7c87cb1829ffadd77d

---


# 予測オーディエンス {#predictive-audiences-getting-started}

>[!IMPORTANT]
>この記事には、この機能の設定と使用方法を説明する製品ドキュメントが含まれています。法的なアドバイスは何も含まれません。法律に関するガイダンスについては、御社の顧問弁護士にアドバイスを求めてください。

## 予測オーディエンスモデルの作成 {#create-predictive-audiences}

モデルを作成する前 [!UICONTROL Predictive Audiences] に、特性とセグメントを割り当てるファーストパーティデータソースを決定する [!UICONTROL Predictive Audiences] 必要があります。 既存のファーストパーティデータソースを使用するか、新しいデータソースを作成できます。 新しいフ [ァーストパーティデータソースの作成方法について詳しくは](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/features/data-sources/manage-datasources.html) 、「データソースの管理」を参照してください。

使用するデータソースがわかったら、次の手順に従います。

1. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. [!UICONTROL Predictive Audiences] セクションで、「**[!UICONTROL Add New]**」をクリックします。

   ![スマートパーソナ追加](assets/predictive-audiences-add.png)

1. 次に、分類の基準となる個人をオーディエンスします。 これを行うには、人物を作成する特性またはセグメントを選択します。 画面の左 [!UICONTROL Traits] 上隅 [!UICONTROL Segments] にあるタブとタブを使用して、特性カタログとセグメントカタログを切り替えます。 パーソナとして使用する特性またはセグメントを特定したら、列の対応するアイコ **[!UICONTROL Add]** ンをクリックし [!UICONTROL Action] ます。
   ![スマートパーソナセレクトパーソナ](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >ベースラインの個人に対しては、最低でも2つの特性または2つのセグメントを選択する必要があります。 特性とセグメントの両方を組み合わせて使用することはできません。
1. 個人を **[!UICONTROL Next]** 定義したら、をクリックします。
1. 次に、分類するファーストパーティオーディエンスを選択し、このオーディエンスのファーストパーティの特性またはセグメントを選択します。 画面の左 [!UICONTROL Traits] 上隅 [!UICONTROL Segments] にあるタブとタブを使用して、特性とセグメントカタログを切り替えます。 モデルに追加するファーストパーティの特性またはセグメントをオーディエンスとして選択します。
   ![スマートパーソナ選択オーディエンス](assets/predictive-audiences-audience.png)
1. 選択し **[!UICONTROL Next]** た後、をクリックします。オーディエンス
1. モデルの詳細を入力します。
   1. **[!UICONTROL Model Name]**:後でモデルを識別するのに役立つ、モデルを説明する名前を入力します。 モデルによって生成されたセグメントの名前は、開始の名前と共に表示されます。
   2. **[!UICONTROL Description]**:使用事例の特定に役立つモデルの説明を入力します。
   3. **[!UICONTROL Data Source]**:このモデルのセグメントを割り当てるファー [!UICONTROL Predictive Audiences] ストパーティデータソースを選択します。
      ![予測オーディエンス保存](assets/predictive-audiences-save.png)
1. 「**[!UICONTROL Save]**」をクリックします。

## 予測オーディエンス {#edit-predictive-audiences}

オーディエンスマネージャーは、既存のモデルの編集をサポートし [!UICONTROL Predictive Audiences] ていません。 モデルの設定を変更するには、新しいモデルを作成する必要があります。 10モデルの上限に達し、モデルの1つを [!UICONTROL Predictive Audiences] 編集する必要がある場合は、モデルを削除して新しいモデルを作成する必要があります。

## 予測オーディエンス {#delete-predictive-audiences}

モデルを削 [!UICONTROL Predictive Audiences] 除するには、 **[!UICONTROL Audience Data]** /に移 **[!UICONTROL Models]**&#x200B;動し、削除するモデルを見つけて、アイコンをクリックし **[!UICONTROL Delete]** ます。
