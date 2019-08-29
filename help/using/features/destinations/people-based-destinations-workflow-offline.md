---
description: 'このページには、オフラインのみの顧客データからオーディエンスセグメントを構築し、それらを「人ベースの宛先」に送信する方法に関する手順が記載されています。  '
seo-description: 'このページには、オフラインのみの顧客データからオーディエンスセグメントを構築し、それらを「人ベースの宛先」に送信する方法に関する手順が記載されています。  '
seo-title: ワークフローB-オフラインのみのデータに基づくパーソナライゼーション
solution: Audience Manager
title: ワークフローB-オフラインのみのデータに基づくパーソナライゼーション
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# ワークフローB-オフラインのみのデータに基づくパーソナライゼーション {#workflow-b}

このページには、オフラインのみの顧客データからオーディエンスセグメントを構築し、それらを「人ベースの宛先」に送信する方法に関する手順が記載されています。

## ステップ1-オフラインの特徴を埋め込む {#step-1-onboard-traits}

このシナリオでオーディエンスセグメントを作成する最初の手順は、オフラインの顧客データをAudience Managerに取り込むことです。

>[!IMPORTANT]
>
> 継続する前に、対応する顧客アクティビティが、対応する [オンボーブの特性を持つAudience Managerで既に定義されていることを確認](../traits/trait-qualification-reference.md)してください。

既存のAudience Manager顧客ID（[DPUUID](../../reference/ids-in-aam.md)）がハッシュ電子メールかどうかにかかわらず、 [DPUUIDを含むデータソースに対して特性onboardingを実行する必要](../../reference/ids-in-aam.md)があります。

### 例

対応するonboarded特性IDについて、下の表から顧客IDを修飾したい。[DPUUID](../../reference/ids-in-aam.md) は、ID999999のデータソースに格納され、Audience ManagerパートナーIDは123とします。

|顧客ID（DPUUID）|Onboarded Trait ID|
|--|--|
|680799827656731985040526560744546039|12345，23456|
|67412682083411995725538770443620307584|45678|
|89159024796760343733111707646026765593|11223，93342，27341|

対応するオンボーブの特性について、上記の例の顧客IDを修飾するには、 [受信データファイルを次の内容](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) でアップロードする必要があります。

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

ファイル名は次のようになります。 `ftp_dpm_999999_123_TIMESTAMP.sync.gz`を参照してください。
ファイル名構造について詳しくは、受信データファイルの [Amazon](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) S3NameおよびFile Size Requirementsを参照してください。

## 手順2-データソースの設定の指定 {#configure-data-source-settings}

[DPUUID](../../reference/ids-in-aam.md) が小文字で、ハッシュ化された電子メールアドレスかどうかに応じて、ハッシュされた電子メールアドレスを保存するデータソースを設定する必要があります。

**シナリオ1:[DPUUID](../../reference/ids-in-aam.md)は、既に小文字の電子メールアドレスです。**

この場合、対応するデータソースにラベルを付ける必要があります。

1. Go to **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**.
1. [DPUUID](../../reference/ids-in-aam.md)を含むデータソースを探してクリックします。
1. オプション **[!UICONTROL Cannot be tied to personally identifiable information]** が選択解除されていることを確認します。
1. データソースの設定を保存します。

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

## 手順3-ファイルベースのID同期経由で、DpuUIDにハッシュ化された電子メールアドレスを一致させる {#match-ids-emails}

>[!IMPORTANT]
>
> この手順は前述の [シナリオ2](people-based-destinations-workflow-offline.md#configure-data-source-settings) にのみ適用されます。既存 [のDPUUID](../../reference/ids-in-aam.md) が既にハッシュ化された電子メールアドレスである場合は [、手順4-セグメントの結合ルールの作成を参照](#create-profile-merge-rule)してください。

例えば、手順1の例の既存 [のDPUUID](../../reference/ids-in-aam.md) を下の表からハッシュ化した電子メールアドレスに一致させ、 [手順2-データソースの設定で作成した新しいデータソースにハッシュ化された電子メールアドレスを保存するとし](#configure-data-source-settings)ます。

リマインダーとして、2つのデータソースが表示されるようになりました。

| データソースID | データソースの内容 |
|---|---|
| 999999 | 既存のDPUUID（CRM ID） |
| 987654 | ハッシュ化された電子メールアドレス |

| DPUUID（CRM ID） | 電子メールアドレス | ハッシュ化された電子メールアドレス |
|---|---|---|
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

[ID同期ファイル](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) には次の内容が含まれています。

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

[ID同期ファイル](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) は、次の命名構造に従う必要があります。

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

上記の例では、ファイル名は次のようになります。 `c2c_id_999999_987654_1560431657.sync`

[サンプルファイルをここにダウンロード](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)してください。

## 手順4-セグメントの結合ルールの作成 {#create-profile-merge-rule}

次の手順では、新しい結合ルールを作成して、送信するオーディエンスセグメントを作成 [!DNL People-Based Destinations]します。

1. Audience Managerアカウントにログインし、-&gt;に **[!UICONTROL Audience Data]** 移動 **[!UICONTROL Profile Merge Rules]**&#x200B;します。
2. 「[!UICONTROL Add New Rule]」をクリックします。
3. プロファイル結合ルール **[!UICONTROL Name]** を入力 **[!UICONTROL Description]**&#x200B;します。
4. **[!UICONTROL Profile Merge Rule Setup]** セクションで、リストから **[!UICONTROL All Cross-Device Profiles]****[!UICONTROL Cross-Device Options]** ルールを選択します。
5. リストで **[!UICONTROL Cross-Device Profile Options]** 、特性がオンになっているデータソースを選択します。
   ![merge- rule- setup](assets/pbd-pmr.png)

## 手順5-オーディエンスセグメントの作成 {#create-audience-segments}

オフラインのみのデータから新しいセグメントを作成するには [、セグメントビルダー](../segments/segment-builder.md) を使用して、セグメントの作成時に前の手順で作成した新しいプロファイル結合ルールを使用してください。

## 手順6-ユーザーベースのプラットフォーム認証の設定 {#configure-authentication}

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

## 手順7-人物ベースの宛先の作成 {#create-destination}

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
1. **[!UICONTROL Segment Mappings]** セクションで、この宛先に送信するセグメントを選択します。これは、手順5-オーディエンスセグメントの作成で [作成したセグメント](people-based-destinations-workflow-offline.md#create-audience-segments)です。
1. 宛先を保存します。
