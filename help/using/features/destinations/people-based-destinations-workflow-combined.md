---
description: 'このページには、新しいオーディエンスセグメントを作成するためにAudience Managerに既に存在する行動データと、そのオーディエンスセグメントを「人ベースの宛先」に送信する、オフラインCRMデータの結合方法に関する詳しい手順が含まれています。  '
seo-description: 'このページには、新しいオーディエンスセグメントを作成するためにAudience Managerに既に存在する行動データと、そのオーディエンスセグメントを「人ベースの宛先」に送信する、オフラインCRMデータの結合方法に関する詳しい手順が含まれています。   '
seo-title: ワークフローA-オフラインデータと組み合わされたすべてのオンラインアクティビティに基づくパーソナライゼーション
solution: Audience Manager
title: ワークフローA-オフラインデータと組み合わされたすべてのオンラインアクティビティに基づくパーソナライゼーション
translation-type: tm+mt
source-git-commit: d0e343e3fbaf527e9b630dc2dbc851d8f8f4c0b2

---


# ワークフローA-オフラインデータと組み合わされたすべてのオンラインアクティビティに基づくパーソナライゼーション {#workflow-a}

このページには、新しい [!DNL CRM] オーディエンスセグメントを作成するためにAudience Managerに既に存在する行動データと、これらのオーディエンスセグメントを送信するための行動データとの統合手順が含ま [!DNL People-Based Destinations]れています。

## 手順1-データソースの設定の指定 {#configure-data-source-settings}

[DPUUID](../../reference/ids-in-aam.md) が小文字で、ハッシュ化された電子メールアドレスかどうかに応じて、ハッシュされた電子メールアドレスを保存するデータソースを設定する必要があります。

 

**シナリオ1:[DPUUID](../../reference/ids-in-aam.md)は、既に小文字の電子メールアドレスです。**

この場合、対応するデータソースにラベルを付ける必要があります。

1. Go to [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources].
1. [DPUUID](../../reference/ids-in-aam.md)を含むデータソースを探してクリックします。
1. オプション [!UICONTROL Cannot be tied to personally identifiable information] が選択解除されていることを確認します。
1. データソースの設定を保存します。

 

**シナリオ2:[DpuUID](../../reference/ids-in-aam.md)は、小文字の電子メールアドレスではありません。**

この場合、ハッシュされた電子メールアドレスを保存する新しいクロスデバイスデータソースを作成する必要があります。手順は次のとおりです。

1. Audience Managerアカウントにログインし、 **[!UICONTROL Audience Data]** "&gt; **[!UICONTROL Data Sources]**」に移動して、をクリック **[!UICONTROL Add New]**&#x200B;します。
1. [!UICONTROL Name] 新しい [!UICONTROL Description] データソースを入力します。
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

## 手順2-ファイルベースのID同期経由で、DpuUIDをハッシュ化した電子メールアドレスに一致させる {#match-ids-emails}

>[!IMPORTANT]
>
> この手順は前述の [シナリオ2](people-based-destinations-workflow-combined.md#configure-data-source-settings) にのみ適用されます。既存 [のDPUUID](../../reference/ids-in-aam.md) が既にハッシュ化されている電子メールアドレスの場合は [、手順3-セグメントの結合ルールの作成をスキップ](people-based-destinations-workflow-combined.md#create-merge-rule)してください。

既存の [DPUUIDを下の表からハッシュ化された電子メールアドレス](../../reference/ids-in-aam.md) に一致させ、手順1-データソース設定の設定で [作成した新しいデータソースにハッシュ化された電子メールアドレスを保存するとし](people-based-destinations-workflow-combined.md#configure-data-source-settings)ます。

| DPUUID（CRM ID） | 電子メールアドレス | ハッシュ化された電子メールアドレス |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

10のハッシュ化された電子メールアドレスを単一 [のDPUUIDにリンク](../../reference/ids-in-aam.md)できます。これを行うには、同期ファイル内でハッシュ化された電子メールアドレスをコンマで区切ります。

この例では、データソースが2つあります。

| データソースID | データソースの内容 |
| -------------- | -------------------------- |
| 999999 | 既存のDPUUID（CRM ID） |
| 987654 | ハッシュ化された電子メールアドレス |

 

[ID同期ファイル](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) には次の内容が含まれています。

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

[ID同期ファイル](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) は、次の命名構造に従う必要があります。

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

上記の例では、ファイル名は次のようになります。`c2c_id_999999_987654_1560431657.sync`


[サンプルファイルをここにダウンロード](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)してください。

## 手順3-セグメントの結合ルールの作成 {#create-merge-rule}

次の手順では、新しい結合ルールを作成して、ユーザーベースの宛先に送信するオーディエンスセグメントを作成します。

>[!IMPORTANT]
>
> 既にまた [!UICONTROL Current Authenticated Profiles][!UICONTROL Last Authenticated Profiles] はオプションを使用してルールを定義している場合は、 [手順4-オーディエンスセグメントを作成](people-based-destinations-workflow-combined.md#create-audience-segments)することができます。

1. Audience Managerアカウントにログインして **[!UICONTROL Audience Data]** 、/ **[!UICONTROL Profile Merge Rules]**&#x200B;に移動します。
1. 「**[!UICONTROL Add New Rule]**」をクリックします。
1. プロファイル結合ルール **[!UICONTROL Name]** を入力 **[!UICONTROL Description]**&#x200B;します。
1. **[!UICONTROL Profile Merge Rule Setup]** セクションで、また **[!UICONTROL Current Authenticated Profiles]****[!UICONTROL Last Authenticated Profiles]** はオプションを選択します。
1. リストで **[!UICONTROL Cross-Device Profile Options]** 、セグメントを実行するデータソースを選択します。これらは、既存の [DPUUIDを含むデータソース](../../reference/ids-in-aam.md)です。

## 手順4-オーディエンスセグメントの作成 {#create-audience-segments}

新しいオーディエンスセグメントを作成するには [、セグメントビルダーを使用](../segments/segment-builder.md)します。送信する既存のオーディエンスセグメントがある場合は [!DNL People-Based Destinations][、手順5-人ベースのプラットフォーム認証を設定](people-based-destinations-workflow-combined.md#configure-authentication)します。

## 手順5-ユーザーベースのプラットフォーム認証の設定 {#configure-authentication}

1. Audience Managerアカウントにログインして **[!UICONTROL Administration]** 、/ **[!UICONTROL Integrated Accounts]**に移動します。以前にソーシャルプラットフォームとの統合が設定されている場合は、このページに表示されています。それ以外の場合、ページは空です。
   ![ユーザーベースの統合](assets/pbd-config.png)
1. 「**[!UICONTROL Add Account]**」をクリックします。
1. **[!UICONTROL People-Based Platform]** ドロップダウンメニューを使用して、統合を設定するプラットフォームを選択します。
   ![ユーザーベースのプラットフォーム](assets/pbd-add.png)
1. クリック **[!UICONTROL Confirm]** して、選択したプラットフォームの認証ページにリダイレクトします。
1. ソーシャルプラットフォームアカウントを認証すると、関連する広告主アカウントを表示するAudience Managerにリダイレクトされます。使用する広告主アカウントを選択し、をクリック **[!UICONTROL Confirm]**&#x200B;します。
1. Audience Managerは、ページの上部に通知を表示して、アカウントが正常に追加されたかどうかを通知します。また、ソーシャルプラットフォーム認証の有効期限が近づいている場合に通知を受信する連絡先電子メールアドレスを追加することもできます。

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
1. **[!UICONTROL Segment Mappings]** セクションで、この宛先に送信するセグメントを選択します。これは [、手順4-オーディエンスセグメントの作成で作成したセグメント](people-based-destinations-workflow-combined.md#create-audience-segments)です。
1. 宛先を保存します。
