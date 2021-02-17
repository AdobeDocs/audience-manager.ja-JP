---
description: 'このページでは、オフラインの CRM データと、認証済みユーザーのリアルタイムの行動データを組み合わせてオーディエンスセグメントを作成し、そのオーディエンスセグメントを People-Based Destinations に送信する方法について、順を追って説明します。 '
seo-description: 'このページでは、オフラインの CRM データと、認証済みユーザーのリアルタイムの行動データを組み合わせてオーディエンスセグメントを作成し、そのオーディエンスセグメントを People-Based Destinations に送信する方法について、順を追って説明します。  '
seo-title: ワークフロー C - 認証済みアクティビティとオフラインデータの組み合わせに基づいたパーソナライゼーション
solution: Audience Manager
title: ワークフロー C - 認証済みアクティビティとオフラインデータの組み合わせに基づいたパーソナライゼーション
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 100%

---


# ワークフロー C - 認証済みアクティビティとオフラインデータの組み合わせに基づいたパーソナライゼーション {#workflow-c}

>[!IMPORTANT]
>この記事には、この機能の設定と使用方法を説明する製品ドキュメントが含まれています。法的なアドバイスは何も含まれません。法律に関するガイダンスについては、御社の顧問弁護士にアドバイスを求めてください。

このページでは、オフラインの [!DNL CRM] データと、認証済みユーザーのリアルタイムの行動データを組み合わせてオーディエンスセグメントを作成し、そのオーディエンスセグメントを [!DNL People-Based Destinations] に送信する方法について、順を追って説明します。

## 手順 1 - データソースの設定 {#configure-data-source-settings}

[DPUUID](../../reference/ids-in-aam.md) が小文字かどうか、ハッシュ化された電子メールアドレスであるかどうかに応じて、ハッシュされた電子メールアドレスを保存するデータソースを設定する必要があります。

 

**シナリオ 1：[DPUUID](../../reference/ids-in-aam.md) が、既に小文字のハッシュ化された電子メールアドレスになっている。**

この場合は、スキップして「[手順 5 - ユーザーベースのプラットフォーム認証を設定する](#configure-authentication)」に進みます。

 

**シナリオ 2：[DPUUID](../../reference/ids-in-aam.md) が、小文字のハッシュ化された電子メールアドレスになっていない。**

この場合、ハッシュ化された電子メールアドレスを保存する新しいクロスデバイスデータソースを作成する必要があります。手順は次のとおりです。

1. Audience Managerアカウントにログインし、**[!UICONTROL Audience Data]**／**[!UICONTROL Data Sources]** に移動して、**[!UICONTROL Add New]**&#x200B;をクリックします。
1. 新しいデータソースに、**[!UICONTROL Name]** と **[!UICONTROL Description]** を入力します。
1. **[!UICONTROL ID Type]** ドロップダウンメニューで、「**[!UICONTROL Cross Device]**」を選択します。
1. **[!UICONTROL Data Source Settings]** セクションで、**[!UICONTROL Inbound]** と **[!UICONTROL Outbound]** のオプションを両方選択し、**[!UICONTROL Share associated cross-device IDs in people-based destinations]** オプションを有効にします。
1. ドロップダウンメニューを使用して、このデータソースの **[!UICONTROL Emails(SHA256, lowercased)]** ラベルを選択します。
   >[!IMPORTANT]
   >
   >このオプションは、データソースに、特定のアルゴリズムでハッシュ化されたデータを含んでいるというラベルのみを付けます。Audience Manager は、この手順ではデータをハッシュ化しません。このデータソースに保存する予定の電子メールアドレスが、[!DNL SHA256] アルゴリズムで既にハッシュ化されていることを確認してください。それ以外の場合は、[!DNL People-Based Destinations] では使用できません 。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > People-Based Destinations 用にオフラインデータを Audience Manager に取り込む方法については、「[データのオンボーディング](people-based-destinations-prerequisites.md#data-onboarding)」を参照してください。

[!UICONTROL People-Based Destinations] のデータソースの作成方法に関するビデオチュートリアルについては、以下のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 手順 2 - 宣言された ID を使用して DPUUID をハッシュ化された電子メールアドレスと照合する場合と、リアルタイムの HTTP 呼び出しと照合する場合 {#match-email-addresses}

認証されたユーザーをルールベースの特性で絞り込むには、[宣言された ID](../declared-ids.md) を通して特性認定を送信する必要があります。

### 例

次の 2 つのデータソースを作成したとします。

| データソース ID | データソースの内容 |
| -------------- | -------------------------- |
| 999999 | 既存の DPUUID（CRM ID） |
| 987654 | ハッシュ化された電子メールアドレス |

 

次に、テーブルの特性について以下の CRM ID を絞り込みます。

| DPUUID（CRM ID） | 電子メールアドレス | ハッシュ化された電子メールアドレス | 特性 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

宣言された ID は次の構文に従う必要があります。

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

上記の例では、宣言された ID 呼び出しは次のようになります。

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## 手順 3 - セグメントのプロファイル結合ルールを作成する {#create-profile-merge-rule-segmentation}

次の手順では、オーディエンスセグメントを作成して [!DNL People-Based Destinations] に送信するのに役立つ、新しい結合ルールを作成します。

>[!IMPORTANT]
>
>**[!UICONTROL Current Authenticated Profiles]** または **[!UICONTROL Last Authenticated Profiles]** オプションを使用して既にルールを定義している場合は、スキップして「[手順 4 - オーディエンスセグメントの作成](#create-audience-segments)」に進むことができます。

1. Audience Manager アカウントにログインして、**[!UICONTROL Audience Data]**／**[!UICONTROL Profile Merge Rules]** に移動します。
2. 「**[!UICONTROL Add New Rule]**」をクリックします。
3. プロファイル結合ルール **[!UICONTROL Name]** および **[!UICONTROL Description]** を入力します。
4. **[!UICONTROL Profile Merge Rule Setup]** セクションで、**[!UICONTROL Current Authenticated Profiles]** または **[!UICONTROL Last Authenticated Profiles]** ルールを **[!UICONTROL Cross-Device Options]** リストから選択します。
5. **[!UICONTROL Cross-Device Profile Options]** リストで、セグメントを実行するデータソースを選択します。これらは、既存の DPUUID を含むデータソースです。
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## 手順 4 - オーディエンスセグメントを作成する {#create-audience-segments}

新しいセグメントを作成するには、[セグメントビルダー](../segments/segment-builder.md)を使用します。[!DNL People-Based Destinations] に送信する既存のオーディエンスセグメントがある場合は、スキップして「[手順 5 - ユーザーベースのプラットフォーム認証を設定する](#configure-authentication)」に進みます。

## 手順 5 - ユーザーベースのプラットフォーム認証を設定する {#configure-authentication}

1. Audience Manager アカウントにログインして、**[!UICONTROL Administration]**／**[!UICONTROL Integrated Accounts]** に移動します。ソーシャルプラットフォームとの統合を設定したことがある場合は、このページに表示されます。それ以外の場合、ページは空になります。
   ![ユーザーベースの統合](assets/pbd-config.png)
2. 「**[!UICONTROL Add Account]**」をクリックします。
3. **[!UICONTROL People-Based Platform]** ドロップダウンメニューを使用して、統合を設定するプラットフォームを選択します。
   ![ユーザーベースのプラットフォーム](assets/pbd-add.png)
4. **[!UICONTROL Confirm]**&#x200B;をクリックすると、選択したプラットフォームの認証ページにリダイレクトされます。
5. ソーシャルプラットフォームアカウントを認証すると、Audience Manager にリダイレクトされ、関連する広告主アカウントが表示されます。使用する広告主アカウントを選択し、「**[!UICONTROL Confirm]**」をクリックします。
6. Audience Manager のページ上部に通知が表示され、アカウントが正常に追加されたかどうかがわかります。また、連絡先電子メールアドレスを追加して、ソーシャルプラットフォーム認証の有効期限が近づいたら通知を受け取ることもできます。

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
1. **[!UICONTROL Segment Mappings]** セクションで、この宛先に送信するセグメントを選択します。これは、「[手順 4 - オーディエンスセグメントを作成する](#create-audience-segments)」で作成したセグメントです。
1. 宛先を保存します。
