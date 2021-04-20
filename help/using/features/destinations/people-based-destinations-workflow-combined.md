---
description: 'このページでは、オフラインの CRM データと Audience Manager に既に存在する行動データを組み合わせて新しいオーディエンスセグメントを作成し、そのオーディエンスセグメントを People-Based Destinations に送信する方法について、順を追って説明します。  '
seo-description: 'このページでは、オフラインの CRM データと Audience Manager に既に存在する行動データを組み合わせて新しいオーディエンスセグメントを作成し、そのオーディエンスセグメントを People-Based Destinations に送信する方法について、順を追って説明します。   '
seo-title: ワークフロー A - すべてのオンラインアクティビティとオフラインデータの組み合わせに基づいたパーソナライゼーション
solution: Audience Manager
title: ワークフロー A - すべてのオンラインアクティビティとオフラインデータの組み合わせに基づいたパーソナライゼーション
feature: People-based Destinations
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 99%

---

# ワークフロー A - すべてのオンラインアクティビティとオフラインデータの組み合わせに基づいたパーソナライゼーション {#workflow-a}

>[!IMPORTANT]
>この記事には、この機能の設定と使用方法を説明する製品ドキュメントが含まれています。法的なアドバイスは何も含まれません。法律に関するガイダンスについては、御社の顧問弁護士にアドバイスを求めてください。

このページには、オフラインの [!DNL CRM] データと Audience Manager に既に存在する行動データを組み合わせて新しいオーディエンスセグメントを作成し、そのオーディエンスセグメントを[!DNL People-Based Destinations]に送信する方法に関する詳しい手順が含まれています。

## 手順 1 - データソースの設定 {#configure-data-source-settings}

[DPUUID](../../reference/ids-in-aam.md) が小文字かどうか、ハッシュ化された電子メールアドレスであるかどうかに応じて、ハッシュされた電子メールアドレスを保存するデータソースを設定する必要があります。

 

**シナリオ 1：[DPUUID](../../reference/ids-in-aam.md) が、既に小文字のハッシュ化された電子メールアドレスになっている。**

この場合、以下のように、対応するデータソースにラベルを付ける必要があります。

1. [!UICONTROL Audience Data]／[!UICONTROL Data Sources] に移動します。
1. [DPUUID](../../reference/ids-in-aam.md) を含むデータソースを見つけてクリックします。
1. **[!UICONTROL ID Type]** ドロップダウンメニューで、「**[!UICONTROL Cross Device]**」を選択します。
1. オプション [!UICONTROL Cannot be tied to personally identifiable information] が選択解除されていることを確認します。
1. **[!UICONTROL Data Source Settings]** セクションで、**[!UICONTROL Inbound]** と **[!UICONTROL Outbound]** のオプションを両方選択し、**[!UICONTROL Share associated cross-device IDs in people-based destinations]** オプションを有効にします。
1. ドロップダウンメニューを使用して、このデータソースの **[!UICONTROL Emails(SHA256, lowercased)]** ラベルを選択します。
   >[!IMPORTANT]
   >
   >このオプションは、データソースに、特定のアルゴリズムでハッシュ化されたデータを含んでいるというラベルのみを付けます。Audience Manager は、この手順ではデータをハッシュ化しません。このデータソースに保存する予定の電子メールアドレスが、[!DNL SHA256] アルゴリズムで既にハッシュ化されていることを確認してください。それ以外の場合は、[!DNL People-Based Destinations] では使用できません。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. データソースの設定を保存します。

 

**シナリオ 2：[DPUUID](../../reference/ids-in-aam.md) が、小文字のハッシュ化された電子メールアドレスになっていない。**

この場合、ハッシュ化された電子メールアドレスを保存する新しいクロスデバイスデータソースを作成する必要があります。手順は次のとおりです。

1. Audience Managerアカウントにログインし、**[!UICONTROL Audience Data]**／**[!UICONTROL Data Sources]** に移動して、**[!UICONTROL Add New]**&#x200B;をクリックします。
1. 新しいデータソースに、[!UICONTROL Name] と [!UICONTROL Description] を入力します。
1. **[!UICONTROL ID Type]** ドロップダウンメニューで、「**[!UICONTROL Cross Device]**」を選択します。
1. **[!UICONTROL Data Source Settings]** セクションで、**[!UICONTROL Inbound]** と **[!UICONTROL Outbound]** のオプションを両方選択し、**[!UICONTROL Share associated cross-device IDs in people-based destinations]** オプションを有効にします。
1. ドロップダウンメニューを使用して、このデータソースの **[!UICONTROL Emails(SHA256, lowercased)]** ラベルを選択します。
   >[!IMPORTANT]
   >
   >このオプションは、データソースに、特定のアルゴリズムでハッシュ化されたデータを含んでいるというラベルのみを付けます。Audience Manager は、この手順ではデータをハッシュ化しません。このデータソースに保存する予定の電子メールアドレスが、[!DNL SHA256] アルゴリズムで既にハッシュ化されていることを確認してください。それ以外の場合は、[!DNL People-Based Destinations] では使用できません。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. データソースの設定を保存します。

[!UICONTROL People-Based Destinations] のデータソースの作成方法に関するビデオチュートリアルについては、以下のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> People-Based Destinations 用にオフラインデータを Audience Manager に取り込む方法については、「[データのオンボーディング](people-based-destinations-prerequisites.md#data-onboarding)」を参照してください。

## 手順 2 -ファイルベースの ID 同期経由で、DPUUID と ハッシュ化した電子メールアドレスを照合する {#match-ids-emails}

>[!IMPORTANT]
>
> この手順は前述の[シナリオ 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) にのみ適用されます。既存の [DPUUID](../../reference/ids-in-aam.md) がハッシュ化された電子メールアドレスの場合は、[手順 3 - セグメントの結合ルールの作成](people-based-destinations-workflow-combined.md#create-merge-rule)をスキップしてください。

既存の [DPUUID](../../reference/ids-in-aam.md) を下の表のハッシュ化された電子メールアドレスと照合し、ハッシュ化された電子メールアドレスを「[手順 1 - データソースの設定](people-based-destinations-workflow-combined.md#configure-data-source-settings)」で作成した新しいデータソースに保存するとします。

| DPUUID（CRM ID） | 電子メールアドレス | ハッシュ化された電子メールアドレス |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

最大 10 個のハッシュ化された電子メールアドレスを 1 つの [DPUUID](../../reference/ids-in-aam.md) にリンクさせることができます。これをおこなうには、同期ファイル内で、ハッシュ化された電子メールアドレスを `<TAB>` で区切ります。

この例では、データソースが 2 つあります。

| データソース ID | データソースの内容 |
| -------------- | -------------------------- |
| 999999 | 既存の DPUUID（CRM ID） |
| 987654 | ハッシュ化された電子メールアドレス |

 

[ID 同期ファイル](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) には次の内容が含まれています。

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

[ID 同期ファイル](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) は、次の命名構造に従う必要があります。

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

上記の例では、ファイル名は `c2c_id_999999_987654_1560431657.sync` となります。


[サンプルファイルをここにダウンロードしてください](assets/c2c_id_999999_987654_1560431657.sync)。

ID 同期ファイルを作成したら、[!DNL Amazon S3] バケットにアップロードする必要があります。ID 同期ファイルのアップロード方法について詳しくは、[Audience Manager へのバッチデータの送信](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)を参照してください。

## 手順 3 - セグメントのプロファイル結合ルールを作成する {#create-merge-rule}

次の手順では、オーディエンスセグメントを作成してユーザーベースの宛先に送信するのに役立つ、新しい結合ルールを作成します。

>[!IMPORTANT]
>
> [!UICONTROL Current Authenticated Profiles] または [!UICONTROL Last Authenticated Profiles] オプションを使用して既にルールを定義している場合は、スキップして「[手順 4 - オーディエンスセグメントの作成](people-based-destinations-workflow-combined.md#create-audience-segments)」に進むことができます。

1. Audience Manager アカウントにログインして、**[!UICONTROL Audience Data]**／**[!UICONTROL Profile Merge Rules]** に移動します。
1. 「**[!UICONTROL Add New Rule]**」をクリックします。
1. プロファイル結合ルール **[!UICONTROL Name]** および **[!UICONTROL Description]** を入力します。
1. **[!UICONTROL Profile Merge Rule Setup]** セクションで、**[!UICONTROL Current Authenticated Profiles]** または **[!UICONTROL Last Authenticated Profiles]** オプションを選択します。
1. **[!UICONTROL Cross-Device Profile Options]** リストで、セグメントを実行するデータソースを選択します。これらは、既存の [DPUUID](../../reference/ids-in-aam.md) を含むデータソースです。

## 手順 4 - オーディエンスセグメントを作成する {#create-audience-segments}

新しいオーディエンスセグメントを作成するには、[セグメントビルダー](../segments/segment-builder.md)を使用します。[!DNL People-Based Destinations] に送信する既存のオーディエンスセグメントがある場合は、スキップして「[手順 5 - ユーザーベースのプラットフォーム認証を設定する](people-based-destinations-workflow-combined.md#configure-authentication)」に進みます。

## 手順 5 - ユーザーベースのプラットフォーム認証を設定する {#configure-authentication}

1. Audience Manager アカウントにログインして、**[!UICONTROL Administration]**／**[!UICONTROL Integrated Accounts]** に移動します。ソーシャルプラットフォームとの統合を設定したことがある場合は、このページに表示されます。それ以外の場合、ページは空になります。
   ![ユーザーベースの統合](assets/pbd-config.png)
1. 「**[!UICONTROL Add Account]**」をクリックします。
1. **[!UICONTROL People-Based Platform]** ドロップダウンメニューを使用して、統合を設定するプラットフォームを選択します。
   ![ユーザーベースのプラットフォーム](assets/pbd-add.png)
1. **[!UICONTROL Confirm]**&#x200B;をクリックすると、選択したプラットフォームの認証ページにリダイレクトされます。
1. ソーシャルプラットフォームアカウントを認証すると、Audience Manager にリダイレクトされ、関連する広告主アカウントが表示されます。使用する広告主アカウントを選択し、「**[!UICONTROL Confirm]**」をクリックします。
1. Audience Manager のページ上部に通知が表示され、アカウントが正常に追加されたかどうかがわかります。また、連絡先電子メールアドレスを追加して、ソーシャルプラットフォーム認証の有効期限が近づいたら通知を受け取ることもできます。

>[!IMPORTANT]
>
>Audience Manager は、一定期間後に期限切れになる認証トークンを介して、ソーシャルプラットフォームとの統合を処理します。期限切れトークンの更新方法について詳しくは、「認証トークンの更新」を参照してください。

## 手順 6 - People-Based Destinations を作成する {#create-destination}

1. Audience Manager アカウントにログインし、**[!UICONTROL Audience Data]**／**[!UICONTROL Destinations]** に移動して、**[!UICONTROL Create Destination]**&#x200B;をクリックします。
1. **[!UICONTROL Basic Information]** セクションで、新しいデータソースに **[!UICONTROL Name]** と **[!UICONTROL Description]** を入力し、次の設定を使用します。
   * **[!UICONTROL Category]**：統合プラットフォーム
   * **[!UICONTROL Type]**：ユーザーベース
   * **[!UICONTROL Platform]**：オーディエンスセグメントを送信するユーザーベースのプラットフォームを選択します。
   * **[!UICONTROL Account]**：選択したプラットフォームに関連付けられている広告主アカウントを選択します。
      ![create-destination](assets/pbd-create-destination.png)
1. 「**[!UICONTROL Next]**」をクリックします。
1. この宛先に設定する **[!UICONTROL Data Export Labels]** を選択します。
1. **[!UICONTROL Configuration]** セクションで、ハッシュ化されたデータソースを含むデータソースを選択します。
1. **[!UICONTROL Segment Mappings]** セクションで、この宛先に送信するセグメントを選択します。これは、「[手順 4 - オーディエンスセグメントを作成する](people-based-destinations-workflow-combined.md#create-audience-segments)」で作成したセグメントです。
1. 宛先を保存します。
