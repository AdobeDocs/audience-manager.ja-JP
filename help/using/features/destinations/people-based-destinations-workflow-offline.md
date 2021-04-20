---
description: 'このページでは、オフラインのみの顧客データからオーディエンスセグメントを構築し、それらを People-Based Destinations に送信する方法について、順を追って説明します。  '
seo-description: 'このページでは、オフラインのみの顧客データからオーディエンスセグメントを構築し、それらを People-Based Destinations に送信する方法について、順を追って説明します。  '
seo-title: ワークフロー B - オフラインのみのデータに基づくパーソナライゼーション
solution: Audience Manager
title: ワークフロー B - オフラインのみのデータに基づくパーソナライゼーション
feature: People-based Destinations
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 99%

---

# ワークフロー B - オフラインのみのデータに基づくパーソナライゼーション {#workflow-b}

>[!IMPORTANT]
>この記事には、この機能の設定と使用方法を説明する製品ドキュメントが含まれています。法的なアドバイスは何も含まれません。法律に関するガイダンスについては、御社の顧問弁護士にアドバイスを求めてください。

このページでは、オフラインのみの顧客データからオーディエンスセグメントを構築し、それらを People-Based Destinations に送信する方法について、順を追って説明します。

## 手順 1- オフラインの特性をオンボーディングする {#step-1-onboard-traits}

このシナリオでオーディエンスセグメントを作成する際は、最初の手順として、オフラインの顧客データを Audience Manager に取り込みます。

>[!IMPORTANT]
>
> 続行する前に、オンボーディングしようとしている顧客アクティビティが、対応する [オンボーディングされた特性](../traits/trait-and-segment-qualification-reference.md)を備えた Audience Manager で既に定義されていることを確認します。

既存の Audience Manager 顧客 ID（[DPUUID](../../reference/ids-in-aam.md)）がハッシュ化された電子メールであるかどうかにかかわらず、[DPUUID](../../reference/ids-in-aam.md) を含むデータソースに対して特性のオンボーディングをおこなう必要があります。

### 例

対応するオンボード特性 ID について、下の表から顧客 ID を認定したい場合。[DPUUID](../../reference/ids-in-aam.md) は、ID 999999 のデータソースに格納され、Audience Manager パートナー の ID は 123 だとします。

| 顧客 ID（DPUUID） | オンボードの特性 ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

上記の例で、対応するオンボード特性について顧客 ID を絞り込むには、[受信データファイル](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)を次の内容でアップロードする必要があります。

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

ファイル名は次のようになります。`ftp_dpm_999999_123_TIMESTAMP.sync.gz`
ファイル名構造について詳しくは、「[受信データファイルの Amazon S3 名とファイルサイズの要件](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)」を参照してください。

## 手順 2 - データソースの設定 {#configure-data-source-settings}

[DPUUID](../../reference/ids-in-aam.md) が小文字かどうか、ハッシュ化された電子メールアドレスであるかどうかに応じて、ハッシュされた電子メールアドレスを保存するデータソースを設定する必要があります。

 

**シナリオ 1：[DPUUID](../../reference/ids-in-aam.md) が、既に小文字のハッシュ化された電子メールアドレスになっている。**

この場合、以下のように、対応するデータソースにラベルを付ける必要があります。

1. **[!UICONTROL Audience Data]**／**[!UICONTROL Data Sources]** に移動します。
1. [DPUUID](../../reference/ids-in-aam.md) を含むデータソースを見つけてクリックします。
1. オプション **[!UICONTROL Cannot be tied to personally identifiable information]** が選択解除されていることを確認します。
1. データソースの設定を保存します。

 

**シナリオ 2：[DPUUID](../../reference/ids-in-aam.md) が、小文字のハッシュ化された電子メールアドレスになっていない。**

この場合、ハッシュ化された電子メールアドレスを保存する新しいクロスデバイスデータソースを作成する必要があります。手順は次のとおりです。

1. Audience Managerアカウントにログインし、**[!UICONTROL Audience Data]**／**[!UICONTROL Data Sources]** に移動して、**[!UICONTROL Add New]**&#x200B;をクリックします。
1. 新しいデータソースに、**[!UICONTROL Name]** と **[!UICONTROL Description]** を入力します。
1. **[!UICONTROL ID Type]** ドロップダウンメニューで、「**[!UICONTROL Cross Device]**」を選択します。
1. **[!UICONTROL Data Source Settings]** セクションで、**[!UICONTROL Inbound]** と **[!UICONTROL Outbound]** のオプションを両方選択し、**[!UICONTROL Share associated cross-device IDs in people-based destinations]** オプションを有効にします。
1. ドロップダウンメニューを使用して、このデータソースの **[!UICONTROL Emails(SHA256, lowercased)]** ラベルを選択します。
   >[!IMPORTANT]
   >
   >このオプションは、データソースに、特定のアルゴリズムでハッシュ化されたデータを含んでいるというラベルのみを付けます。Audience Manager は、この手順ではデータをハッシュ化しません。このデータソースに保存する予定の電子メールアドレスが、[!DNL SHA256] アルゴリズムで既にハッシュ化されていることを確認してください。それ以外の場合は、[!DNL People-Based Destinations] では使用できません。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > People-Based Destinations 用にオフラインデータを Audience Manager に取り込む方法については、「[データのオンボーディング](people-based-destinations-prerequisites.md#data-onboarding)」を参照してください。

[!UICONTROL People-Based Destinations] のデータソースの作成方法に関するビデオチュートリアルについては、以下のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 手順 3 -ファイルベースの ID 同期経由で、DPUUID と ハッシュ化した電子メールアドレスを照合する {#match-ids-emails}

>[!IMPORTANT]
>
> この手順は前述の[シナリオ 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) にのみ適用されます。既存の [DPUUID](../../reference/ids-in-aam.md) がハッシュ化された電子メールアドレスの場合は、[手順 4 - セグメントの結合ルールの作成](#create-profile-merge-rule)をスキップしてください。

手順 1 の例にある既存の [DPUUID](../../reference/ids-in-aam.md) と、下の表（右側の列）のハッシュ化された電子メールアドレスを照合し、ハッシュ化された電子メールアドレスを「[手順 2 - データソースの設定](#configure-data-source-settings)」で作成した新しいデータソースに保存するとします。

2 つのデータソースが表示されるようになりました。

| データソース ID | データソースの内容 |
| -------------- | -------------------------- |
| 999999 | 既存の DPUUID（CRM ID） |
| 987654 | ハッシュ化された電子メールアドレス |

| DPUUID（CRM ID） | 電子メールアドレス | ハッシュ化された電子メールアドレス |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 891590247967603433311707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

ここに示す例では、[ID 同期ファイル](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) には以下の内容が含まれています。

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

## 手順 4 - セグメントのプロファイル結合ルールを作成する {#create-profile-merge-rule}

次の手順では、オーディエンスセグメントを作成して [!DNL People-Based Destinations] に送信するのに役立つ、新しい結合ルールを作成します。

1. Audience Manager アカウントにログインして、**[!UICONTROL Audience Data]**／**[!UICONTROL Profile Merge Rules]** に移動します。
2. 「[!UICONTROL Add New Rule]」をクリックします。
3. プロファイル結合ルール **[!UICONTROL Name]** および **[!UICONTROL Description]** を入力します。
4. **[!UICONTROL Profile Merge Rule Setup]** セクションで、**[!UICONTROL All Cross-Device Profiles]** ルールを **[!UICONTROL Cross-Device Options]** リストから選択します。
5. **[!UICONTROL Cross-Device Profile Options]** リストで、特性をオンボードしたデータソースを選択します。
   ![merge-rule-setup](assets/pbd-pmr.png)

## 手順 5 - オーディエンスセグメントを作成する {#create-audience-segments}

オフラインのみのデータから新しいセグメントを作成するには [セグメントビルダー](../segments/segment-builder.md) を使用し、セグメントの作成時に前の手順で作成した新しいプロファイル結合ルールを使用するようにしてください。

## 手順 6 - ユーザーベースのプラットフォーム認証を設定する {#configure-authentication}

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

## 手順 7 - People-Based Destinations を作成する {#create-destination}

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
1. **[!UICONTROL Segment Mappings]** セクションで、この宛先に送信するセグメントを選択します。これは、「[手順 5 - オーディエンスセグメントを作成する](people-based-destinations-workflow-offline.md#create-audience-segments)」で作成したセグメントです。
1. 宛先を保存します。
