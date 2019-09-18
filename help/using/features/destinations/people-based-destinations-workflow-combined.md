---
description: 'このページには、オフラインCRMデータとAudience Managerで既に存在する行動データを組み合わせて新しいオーディエンスセグメントを作成し、これらのオーディエンスセグメントを人物ベースの宛先に送信する方法に関する手順説明が含まれています。  '
seo-description: 'このページには、オフラインCRMデータとAudience Managerで既に存在する行動データを組み合わせて新しいオーディエンスセグメントを作成し、これらのオーディエンスセグメントを人物ベースの宛先に送信する方法に関する手順説明が含まれています。   '
seo-title: ワークフローA — オフラインデータと組み合わされたすべてのオンラインアクティビティに基づくパーソナライゼーション
solution: Audience Manager
title: ワークフローA — オフラインデータと組み合わされたすべてのオンラインアクティビティに基づくパーソナライゼーション
translation-type: tm+mt
source-git-commit: 455c198d7a096a620a2cf7c8b728b67335eadc8d

---


# ワークフローA — オフラインデータと組み合わされたすべてのオンラインアクティビティに基づくパーソナライゼーション {#workflow-a}

このページには、オフラインデータとAudience Managerで既に存在する行動データを組み合わせて新しいオーディエンスセグメントを作成し、これらのオーディエンスセグメントをに送信する方法に関する手順説明が含まれていま [!DNL CRM][!DNL People-Based Destinations]す。

## 手順1 — データソースの設定 {#configure-data-source-settings}

DPUUIDが小文字のハッシ [ュ化された電子メールアドレスであるかどうかに応じて](../../reference/ids-in-aam.md) 、ハッシュ化された電子メールアドレスを格納するデータソースを設定する必要が生じる場合があります。

 

**シナリオ1:dpuuidは既に小[文字で](../../reference/ids-in-aam.md)、ハッシュ化された電子メールアドレスです。**

この場合、対応するデータソースに次のようにラベルを付ける必要があります。

1. Go to [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources].
1. DPUUIDを含むデータソースを探 [し](../../reference/ids-in-aam.md)、クリックします。
1. ドロップダウ **[!UICONTROL ID Type]** ンメニューで、を選択しま **[!UICONTROL Cross Device]**&#x200B;す。
1. このオプションがオフになってい [!UICONTROL Cannot be tied to personally identifiable information] ることを確認します。
1. セクション **[!UICONTROL Data Source Settings]** で、との両方のオプション **[!UICONTROL Inbound]** を選 **[!UICONTROL Outbound]** 択し、このオプションを有効に **[!UICONTROL Share associated cross-device IDs in people-based destinations]** します。
1. ドロップダウンメニューを使用して、このデータソ **[!UICONTROL Emails(SHA256, lowercased)]** ースのラベルを選択します。
   >[!IMPORTANT]
   >
   >このオプションは、特定のアルゴリズムでハッシュ化されたデータを含むデータソースとしてのみラベル付けします。 Audience Managerでは、この手順ではデータをハッシュ化しません。 このデータソースに保存する予定の電子メールアドレスが、アルゴリズムで既にハッシュ化されていることを確認し [!DNL SHA256] ます。 そうしないと、それを使用できなくなります [!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. データソースの設定を保存します。

 

**シナリオ2:dpuuidは小文[字ではなく](../../reference/ids-in-aam.md)、ハッシュ化された電子メールアドレスです。**

この場合、ハッシュされた電子メールアドレスを保存する新しいデバイス間データソースを作成する必要があります。 手順は次のとおりです。

1. Audience Managerアカウントにログインし、/に移動して、 **[!UICONTROL Audience Data]** をクリ **[!UICONTROL Data Sources]**&#x200B;ックします **[!UICONTROL Add New]**。
1. 新しいデー [!UICONTROL Name] タソー [!UICONTROL Description] スの「および」を入力します。
1. ドロップダウ **[!UICONTROL ID Type]** ンメニューで、を選択しま **[!UICONTROL Cross Device]**&#x200B;す。
1. セクション **[!UICONTROL Data Source Settings]** で、との両方のオプション **[!UICONTROL Inbound]** を選 **[!UICONTROL Outbound]** 択し、このオプションを有効に **[!UICONTROL Share associated cross-device IDs in people-based destinations]** します。
1. ドロップダウンメニューを使用して、このデータソ **[!UICONTROL Emails(SHA256, lowercased)]** ースのラベルを選択します。
   >[!IMPORTANT]
   >
   >このオプションは、特定のアルゴリズムでハッシュ化されたデータを含むデータソースとしてのみラベル付けします。 Audience Managerでは、この手順ではデータをハッシュ化しません。 このデータソースに保存する予定の電子メールアドレスが、アルゴリズムで既にハッシュ化されていることを確認し [!DNL SHA256] ます。 そうしないと、それを使用できなくなります [!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. データソースの設定を保存します。

>[!NOTE]
>
> オフラ [インデータをAudience Managerに取り込んで人ベースの宛先にする方法に関するよくある質問については、「データオンボーディング](people-based-destinations-prerequisites.md#data-onboarding) 」を参照してください。

## 手順2 — ファイルベースのID同期を使用してDPUUIDをハッシュ化された電子メールアドレスに一致させる {#match-ids-emails}

>[!IMPORTANT]
>
> この手順は、上記のシナリオ2 [にのみ](people-based-destinations-workflow-combined.md#configure-data-source-settings) 適用されます。 既存のDPUUIDが既にハッシ [ュ化された電子メールアドレスである場合は](../../reference/ids-in-aam.md) 、手順3 — セグメント用のプロ [ファイル結合ルールの作成に進みます](people-based-destinations-workflow-combined.md#create-merge-rule)。

既存の [DPUUIDを下の表（右の列）のハッシュ化された電子メールアドレスに一致させ、手順1の「データソースの設定」で作成した新しいデータソースにハッシュ化された電子メールアドレスを格納するとします](../../reference/ids-in-aam.md)[](people-based-destinations-workflow-combined.md#configure-data-source-settings)。

| DPUUID(CRM ID) | 電子メールアドレス | ハッシュ化された電子メールアドレス |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

最大10個のハッシュ化された電子メールアドレスを1つの [DPUUIDにリンクできます](../../reference/ids-in-aam.md)。 これを行うには、ハッシュ化された電子メールアドレスを、同期ファイル内でコンマで区切ります。

この例では、2つのデータソースが作成されます。

| データソースID | データソースのコンテンツ |
| -------------- | -------------------------- |
| 999999 | 既存のDPUUID(CRM ID) |
| 987654 | ハッシュ化された電子メールアドレス |

 

ID同 [期ファイルには](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 、次の内容が含まれます。

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

ID同期フ [ァイルは](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 、次の命名構造に従う必要があります。

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

上の例では、ファイル名は次のようになります。
`c2c_id_999999_987654_1560431657.sync`

[サンプルファイルをここにダウンロードします](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)。

## 手順3 — セグメント用のプロファイル結合ルールを作成する {#create-merge-rule}

次の手順は、ユーザーベースの宛先に送信するオーディエンスセグメントを作成するのに役立つ、新しい結合ルールを作成することです。

>[!IMPORTANT]
>
> またはオプションを使用してルールが既に定義されてい [!UICONTROL Current Authenticated Profiles] る場合は、手 [!UICONTROL Last Authenticated Profiles] 順4 — オーディエンスセグメント [の作成に進むことができます](people-based-destinations-workflow-combined.md#create-audience-segments)。

1. Audience Managerアカウントにログインし、/に移動し **[!UICONTROL Audience Data]** ます **[!UICONTROL Profile Merge Rules]**。
1. 「**[!UICONTROL Add New Rule]**」をクリックします。
1. プロファイル結合ルールとを入 **[!UICONTROL Name]** 力しま **[!UICONTROL Description]**&#x200B;す。
1. セクションで、 **[!UICONTROL Profile Merge Rule Setup]** またはのオプション **[!UICONTROL Current Authenticated Profiles]** を選択 **[!UICONTROL Last Authenticated Profiles]** します。
1. リスト **[!UICONTROL Cross-Device Profile Options]** で、セグメントを実行するデータソースを選択します。 既存のDPUUIDを含むデータソースを指定し [ます](../../reference/ids-in-aam.md)。

## 手順4 — オーディエンスセグメントを作成する {#create-audience-segments}

新しいオーディエンスセグメントを作成するには、セグメントビル [ダーを使用しま](../segments/segment-builder.md)す。 送信先の既存のオーディエンスセグメントがある場合は、手順5 [!DNL People-Based Destinations]— 人物ベースのプ [ラットフォーム認証の設定に進みます](people-based-destinations-workflow-combined.md#configure-authentication)。

## 手順5 — 人ベースのプラットフォーム認証の設定 {#configure-authentication}

1. Audience Managerアカウントにログインし、/に移動し **[!UICONTROL Administration]** ます **[!UICONTROL Integrated Accounts]**。 以前にソーシャルプラットフォームとの統合を設定した場合は、このページにその統合が表示されます。 それ以外の場合、ページは空です。
   ![人口統合](assets/pbd-config.png)
1. 「**[!UICONTROL Add Account]**」をクリックします。
1. ドロップダウ **[!UICONTROL People-Based Platform]** ンメニューを使用して、統合を設定するプラットフォームを選択します。
   ![人々に基づくプラットフォーム](assets/pbd-add.png)
1. クリックす **[!UICONTROL Confirm]** ると、選択したプラットフォームの認証ページにリダイレクトされます。
1. ソーシャルプラットフォームアカウントに対して認証が済むと、Audience Managerにリダイレクトされ、関連する広告主アカウントが表示されます。 使用する広告主アカウントを選択し、をクリックしま **[!UICONTROL Confirm]**&#x200B;す。
1. Audience Managerでは、ページの上部に、アカウントが正常に追加されたかどうかを知らせる通知が表示されます。 また、この通知を使用して、ソーシャルプラットフォーム認証の期限が切れる前に通知を受信する連絡先の電子メールアドレスを追加することもできます。

>[!IMPORTANT]
>
>Udience Managerは、一定時間が経過すると期限切れになる認証トークンを使用して、ソーシャルプラットフォームとの統合を処理します。 期限切れのトークンを更新する方法について詳しくは、「認証トークンの更新」を参照してください。

## 手順6 — 人ベースの宛先の作成 {#create-destination}

1. Audience Managerアカウントにログインし、/に移動して、 **[!UICONTROL Audience Data]** をクリ **[!UICONTROL Destinations]**&#x200B;ックします **[!UICONTROL Create Destination]**。
1. このセクシ **[!UICONTROL Basic Information]** ョンで、新しいデ **[!UICONTROL Name]** ータソー **[!UICONTROL Description]** スのANDを入力し、次の設定を使用します。
   * **[!UICONTROL Category]**:統合プラットフォーム
   * **[!UICONTROL Type]**:人ベース、
   * **[!UICONTROL Platform]**:オーディエンスセグメントの送信先の人ベースのプラットフォームを選択します。
   * **[!UICONTROL Account]**:選択したプラットフォームに関連付ける広告主アカウントを選択します。
      ![create-destination](assets/pbd-create-destination.png)
1. 「**[!UICONTROL Next]**」をクリックします。
1. この宛先 **[!UICONTROL Data Export Labels]** に設定する対象を選択します。
1. セクション **[!UICONTROL Configuration]** で、ハッシュ化されたデータソースを含むデータソースを選択します。
1. セクション **[!UICONTROL Segment Mappings]** で、この宛先に送信するセグメントを選択します。 これは、手順4の「オーディエンスセグメントを作成」 [で作成したセグメントです](people-based-destinations-workflow-combined.md#create-audience-segments)。
1. 宛先を保存します。
