---
description: 'このページには、認証されたユーザーがオーディエンスセグメントを作成するために、オフラインのCRMデータとリアルタイムの行動データを組み合わせて、これらのオーディエンスセグメントを人ベースの宛先に送信する方法に関する詳しい手順が含まれています。 '
seo-description: 'このページには、認証されたユーザーがオーディエンスセグメントを作成するために、オフラインのCRMデータとリアルタイムの行動データを組み合わせて、これらのオーディエンスセグメントを人ベースの宛先に送信する方法に関する詳しい手順が含まれています。  '
seo-title: ワークフローC-オフラインデータと組み合わされた認証済みアクティビティに基づくパーソナライゼーション
solution: Audience Manager
title: ワークフローC-オフラインデータと組み合わされた認証済みアクティビティに基づくパーソナライゼーション
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# ワークフローC-オフラインデータと組み合わされた認証済みアクティビティに基づくパーソナライゼーション {#workflow-c}

このページには、認証されたユーザーがオーディエンスセグメントを作成して、次にオーディエンスセグメントを送信するための、オフライン [!DNL CRM] データとリアルタイムの行動データとの結合方法に関する手順が含まれ [!DNL People-Based Destinations]ています。

## 手順1-データソースの設定の指定 {#configure-data-source-settings}

[DPUUID](../../reference/ids-in-aam.md) が小文字で、ハッシュ化された電子メールアドレスかどうかに応じて、ハッシュされた電子メールアドレスを保存するデータソースを設定する必要があります。

**シナリオ1:[DPUUID](../../reference/ids-in-aam.md)は、既に小文字の電子メールアドレスです。**

この場合、 [手順5-人ベースのプラットフォーム認証を設定](#configure-authentication)します。

**シナリオ2:[DpuUID](../../reference/ids-in-aam.md)は、小文字の電子メールアドレスではありません。**

この場合、ハッシュされた電子メールアドレスを保存する新しいクロスデバイスデータソースを作成する必要があります。手順は次のとおりです。

1. Audience Managerアカウントにログインし **[!UICONTROL Audience Data]** 、-&gt; **[!UICONTROL Data Sources]**&#x200B;に移動して、をクリック **[!UICONTROL Add New]**&#x200B;します。
1. **[!UICONTROL Name]** 新しい **[!UICONTROL Description]** データソースを入力します。
1. **[!UICONTROL ID Type]** ドロップダウンメニューで、を選択 **[!UICONTROL Cross Device]**&#x200B;します。
1. **[!UICONTROL Data Source Settings]** セクションで、 **[!UICONTROL Inbound]** 両方のオプションと **[!UICONTROL Outbound]** オプションを選択し、 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** オプションを有効にします。
1. ドロップダウンメニューを使用して、このデータソースの **[!UICONTROL Emails(SHA256, lowercased)]** ラベルを選択します。
   >[!IMPORTANT]
   >
   >このオプションは、特定のアルゴリズムでハッシュ化されたデータを含むデータソースにのみラベルを付けます。Audience Managerは、この手順でデータをハッシュしません。このデータソースに保存する予定の電子メールアドレスが [!DNL SHA256] 、アルゴリズムで既にハッシュ化されていることを確認してください。それ以外の場合は、使用できません [!DNL People-Based Destinations]。

   ![pbd- datasource- settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > ユーザーベースの宛先について、オフラインデータをAudience Managerに取り込む方法については [、Data Onboarding](people-based-destinations-prerequisites.md#data-onboarding) を参照してください。

## 手順2-リアルタイムHTTP呼び出し経由で、DPUUIDをハッシュ化された電子メールアドレスに一致させる {#match-email-addresses}

認証されたユーザーをルールベースの特性で修飾するには、宣言済みIDを通し [て特性選定を送信する必要](../declared-ids.md)があります。

### 例

次の2つのデータソースを作成したとします。

| データソースID | データソースの内容 |
|---|---|
| 999999 | 既存のDPUUID（CRM ID） |
| 987654 | ハッシュ化された電子メールアドレス |

次に、テーブルの特性について以下のCRM IDを指定します。

| DPUUID（CRM ID） | 電子メールアドレス | ハッシュ化された電子メールアドレス | 特性 |
|---|---|---|---|
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location= US |

宣言されたIDは次の構文に従う必要があります。

`https://yourDomain.demdex.net/event?d_cid_ic=myHashedEmailDataSourceID%01myHashedEmail&d_cid_ic=myCrmDataSourceID%01myCRMID&key=value`

上記の例では、宣言されたID呼び出しは次のようになります。

`https://yourDomain.demdex.net/event?d_cid_ic=987654%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=999999%0168079982765673198504052656074456196039&location=US`

## 手順3-セグメントの結合ルールの作成 {#create-profile-merge-rule-segmentation}

次の手順では、新しい結合ルールを作成して、送信するオーディエンスセグメントを作成 [!DNL People-Based Destinations]します。

>[!IMPORTANT]
>
>既にまた **[!UICONTROL Current Authenticated Profiles]****[!UICONTROL Last Authenticated Profiles]** はオプションを使用してルールを定義している場合は、 [手順4-オーディエンスセグメントを作成](#create-audience-segments)することができます。

1. Audience Managerアカウントにログインし、-&gt;に **[!UICONTROL Audience Data]** 移動 **[!UICONTROL Profile Merge Rules]**&#x200B;します。
2. 「**[!UICONTROL Add New Rule]**」をクリックします。
3. プロファイル結合ルール **[!UICONTROL Name]** を入力 **[!UICONTROL Description]**&#x200B;します。
4. **[!UICONTROL Profile Merge Rule Setup]** セクションで、リストから **[!UICONTROL All Cross-Device Profiles]****[!UICONTROL Cross-Device Options]** ルールを選択します。
5. リストで **[!UICONTROL Cross-Device Profile Options]** 、セグメントを実行するデータソースを選択します。これらは、既存のDPUUIDを含むデータソースです。
   ![merge- rule- setup](assets/pbd-pmr-combined.png)

## 手順4-オーディエンスセグメントの作成 {#create-audience-segments}

新しいセグメントを作成するには [、セグメントビルダーを使用](../segments/segment-builder.md)します。送信する既存のオーディエンスセグメントがある場合は [!DNL People-Based Destinations][、手順5-人ベースのプラットフォーム認証を設定](#configure-authentication)します。

## 手順5-ユーザーベースのプラットフォーム認証の設定 {#configure-authentication}

1. Audience Managerアカウントにログインして **[!UICONTROL Administration]** 、/ **[!UICONTROL Integrated Accounts]**に移動します。以前にソーシャルプラットフォームとの統合が設定されている場合は、このページに表示されています。それ以外の場合、ページは空です。
   ![ユーザーベースの統合](assets/pbd-config.png)
2. 「**[!UICONTROL Add Account]**」をクリックします。
3. **[!UICONTROL People-Based Platform]** ドロップダウンメニューを使用して、統合を設定するプラットフォームを選択します。
   ![ユーザーベースのプラットフォーム](assets/pbd-add.png)
4. クリック **[!UICONTROL Confirm]** して、選択したプラットフォームの認証ページにリダイレクトします。
5. ソーシャルプラットフォームアカウントを認証すると、関連する広告主アカウントを表示するAudience Managerにリダイレクトされます。使用する広告主アカウントを選択し、をクリック **[!UICONTROL Confirm]**&#x200B;します。
6. Audience Managerは、ページの上部に通知を表示して、アカウントが正常に追加されたかどうかを通知します。また、ソーシャルプラットフォーム認証の有効期限が近づいている場合に通知を受信する連絡先電子メールアドレスを追加することもできます。

>[!IMPORTANT]
>
>udience Managerは、一定期間後に期限切れになる認証トークンを介してソーシャルプラットフォームと統合します。期限切れトークンの更新方法について詳しくは、認証トークンの更新を参照してください。

## 手順6-人物ベースの宛先の作成 {#create-destination}

1. Audience Managerアカウントにログインし、 **[!UICONTROL Audience Data]** "&gt; **[!UICONTROL Destinations]**」に移動して、をクリック **[!UICONTROL Create Destination]**&#x200B;します。
1. **[!UICONTROL Basic Information]** セクションで **[!UICONTROL Name]** 、および **[!UICONTROL Description]** 新しいデータソースを入力し、次の設定を使用します。
   * **[!UICONTROL Category]**:統合プラットフォーム;
   * **[!UICONTROL Type]**:人物ベース;
   * **[!UICONTROL Platform]**:オーディエンスセグメントを送信する人ベースのプラットフォームを選択します。
   * **[!UICONTROL Account]**:選択したプラットフォームに関連付けられている広告主アカウントを選択します。
      ![create- destination](assets/pbd-create-destination.png)
1. 「**[!UICONTROL Next]**」をクリックします。
1. この宛先 **[!UICONTROL Data Export Labels]** に設定する項目を選択します。
1. **[!UICONTROL Configuration]** セクションで、ハッシュデータソースを含むデータソースを選択します。
1. **[!UICONTROL Segment Mappings]** セクションで、この宛先に送信するセグメントを選択します。これは [、手順4-オーディエンスセグメントの作成で作成したセグメント](#create-audience-segments)です。
1. 宛先を保存します。
