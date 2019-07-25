---
description: プロファイル結合ルールを作成するには、この節で説明している手順を確認して完了してください。
seo-description: プロファイル結合ルールを作成するには、この節で説明している手順を確認して完了してください。
seo-title: プロファイル結合ルールの導入
solution: Audience Manager
title: プロファイル結合ルールの導入
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# プロファイル結合ルールの導入 {#getting-started-with-profile-merge-rules}

To create [!UICONTROL Profile Merge Rules], review and complete the steps in each of the procedures described in this section.

<!-- merge-rules-start.xml -->

## デバイス間データソースの作成 {#create-data-source}

To create a cross-device data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. クロスデバイス対応データソースの作成や編集には、管理者権限が必要です。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>各種コントロールの説明については、[データソースの設定とメニューオプション](../../features/datasources-list-and-settings.md#settings-menu-options)を参照してください。

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. データソースの名前を入力します。
1. *（オプション）*&#x200B;データソースの説明を入力します。データソースの役割や目的を定義するのに、簡潔な説明が役に立ちます。
1. 統合コードを指定します。統合コードは、このデータソース専用の一意の ID です。
1. **[!UICONTROL ID Type]** リストで、を選択 **[!UICONTROL Cross Device]**&#x200B;します。
1. 「**[!UICONTROL ID Definition]**」リストで、データソースタイプを定義するオプションを選択します。オプションは以下のとおりです。
   * **[!UICONTROL Person]**：個人を定義する ID。この ID は複数の [!DNL Audience Manager] ID にマッピングできます。
   * **[!UICONTROL Household]**：人々のグループを定義する ID。この ID は複数の [!DNL Audience Manager] ID にマッピングできます。

## データ書き出しコントロール {#export-controls}

[データ書き出しコントロール](../../features/data-export-controls.md)は、データソースおよび宛先に適用できるオプションの分類ルールです。宛先へのデータ送信がデータのプライバシーや使用契約に違反する場合、データ送信を防止します。Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

「[!UICONTROL Data Source Settings]」セクションには複数のオプションが用意されていますが、クロスデバイス対応データソースの作成には次の 2 つのオプションが重要です。

* **[!UICONTROL Use as Authenticated Profile]**:デフォルトで選択されているこの設定により、独自の認証済みデータを [!UICONTROL Profile Merge Rule] 作成できます。

* **[!UICONTROL Use as a Device Graph]**:このコントロールは、データプロバイダーとして一覧表示されているアカウントでのみ使用できます。このチェックボックスを選択すると、データソースがデバイスグラフとして作成され、[!DNL Audience Manager] の他のお客様と共有できるようになります。[!DNL Audience Manager] コンサルタントと相談してデータプロバイダーとして設定し、これを [!UICONTROL Data Source] 共有する顧客を指定します。コンサルタントは、社内のプロビジョニングプロセスを通じて、アカウントとデバイスグラフ共有をプロビジョニングします。

* **[!UICONTROL Data retention for inactive Customer IDs]**:このコントロールを使用すると、非アクティブな顧客IDのデータ保持期間を設定できます。Audience ManagerがAudience Managerプラットフォームで最後に確認された後、Audience Managerがデータベースに顧客IDを保持する方法を決定します。デフォルト値は24ヶ月（720日）です。設定できる最小値は1か月、最大値は5年です。すべての月は30日としてカウントされます。Audience Managerは、非アクティブな顧客IDに設定したデータ保持に従って、非アクティブな顧客IDを週1度削除するプロセスを実行します。

The text fields associated with these settings let you rename the [!UICONTROL Data Source] with an alias that appears in the [Profile Merge Rule options](../../features/profile-merge-rules/merge-rule-definitions.md). For example, if you add an alias to **[!UICONTROL Use as Authenticated Profile]**, that name appears in the [!UICONTROL Authenticated Profile Options] list. If you add an alias to **[!UICONTROL Use as a Device Graph]**, that name appears in the [!UICONTROL Device Options] list.

>[!MORE_LIKE_THIS]
>
>* [データソースの作成](../../features/manage-datasources.md#create-data-source)


## プロファイル結合ルール{#create-profile-merge-rule}の作成 

[!UICONTROL Profile Merge Rule]を作成するには、 **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** ここで説明する各セクションの手順を実行してください。クロスデバイス対応データソースをセットアップした後、最大 3 個の結合ルールを作成できます。ルールの作成、編集、削除には、管理者権限が必要です。All users can view and use existing [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**前提条件:** デバイスの構築には、クロスデバイスデータソースが必要 [!UICONTROL Profile Merge Rule]です。See [Create a Data Source](../../features/manage-datasources.md#create-data-source).

>[!TIP]
>
>各種コントロールの説明については、[定義済みのプロファイルの結合ルールオプション](../../features/profile-merge-rules/merge-rule-definitions.md)を参照してください。

## Basic Information {#basic-info}

To complete the [!UICONTROL Basic Information] section:

1. Name the [!UICONTROL Profile Merge Rule].
2. *（オプション）* を説明 [!UICONTROL Profile Merge Rule]します。ルールの役割や目的を定義するのに、簡潔な説明が役に立ちます。
3. *（オプション）* これをデフォルトにする **[!UICONTROL Set as default]** 場合に選択 [!UICONTROL Profile Merge Rule]します。新規セグメントはデフォルトルールに自動的に関連付けられます。

## データ書き出しコントロール {#data-export-controls}

[データエクスポートコントロール](../../features/data-export-controls.md) はオプションの分類ルールで、このルールに適用 [!UICONTROL Profile Merge Rule]できます。宛先へのデータ送信がデータのプライバシーや使用契約に違反する場合、データ送信を防止します。Skip this section if you do not use [!UICONTROL Data Export Controls].

## Profile Merge Rule Setup {#profile-merge-rule-setup}

To complete the [!UICONTROL Proflie Merge Rule Setup] section:

1. Select an **[!UICONTROL Authenticated Option]**. オプションは以下のとおりです。
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Select an **[!UICONTROL Authenticated Profile Option]** (up to 3, maximum). これらは作成済みの[クロスデバイス対応データソース](../../features/profile-merge-rules/merge-rules-start.md)です。
3. Select a **[!UICONTROL Device Option]**. オプションは以下のとおりです。
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. **[!UICONTROL Save]**&#x200B;をクリックします。

## 結合ルールコードの設定 {#configure-merge-rule-code}

Follow these instructions to set up the [!UICONTROL Experience Cloud ID Service], [!UICONTROL DIL], and mobile [!DNL SDK] code to work with your merge rules.

<!-- merge-rules-configure-code.xml -->

### 前提条件

これらの手順を完了する&#x200B;*前*&#x200B;に、[クロスデバイス対応データソース](#create-data-source)および[プロファイル結合ルール](#create-profile-merge-rule)を設定する必要があります。

## Experience Cloud ID サービスのお客様向け {#id-service-customers}

The [!UICONTROL Experience Cloud ID Service] and the latest version of [DIL](../../dil/dil-overview.md) are recommended when working with [!UICONTROL Profile Merge Rules]. However, you don't have to use the [!UICONTROL Experience Cloud ID Service] to work with this feature. [!UICONTROL DIL] のみを使用する場合は、下記の[レガシー DIL](../../features/profile-merge-rules/merge-rules-start.md#legacy-dil) の節を参照してください。

### 顧客 ID 設定関数の設定

When working with the [!UICONTROL Experience Cloud ID Service], the `setCustomerIDs` function passes declared IDs to [!DNL Audience Manager]. プロファイル結合ルールを使用する場合、`setCustomerIDs` を変更して、デバイス間データソースの作成時に指定した統合コードを使用するよう設定します。例えば、統合コード `my_datasource_ic` でデバイス間データソースを作成したとします。宣言済み ID を渡すには、以下の変更後のコードのサンプルに示すように、統合コードを訪問者 ID 関数に追加します。

#### 汎用コードのサンプル

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### 変更後のコードのサンプル

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

For more information, see [Create a Cross-Device Data Source](#create-data-source) and [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html).

### `DIL.create` 関数の設定

The latest versions of [!UICONTROL DIL] now automatically pick up the [!UICONTROL declared ID] from the `visitorService` function in `DIL.create` (see [Declared ID Variables](../../features/declared-ids.md#declared-id-variables)). `DIL.create` 関数を調べ、以下のコードのサンプルのように適切に設定されていることを確認します。

<pre class="js"><code>var vdil= DIL. create（{パートナー:「パートナー名」、visitorService:{namespace:「<i>INSERT- MCORG- ID- HERE</i>」}}）;</code>
</pre>

namespace キー値ペアの `*`MCORG`*` 変数は [!DNL Experience Cloud] の組織 ID です。この ID がわからない場合、[!UICONTROL Administration] ダッシュボードの「[!DNL Experience Cloud]」セクションで確認できます。このダッシュボードを表示するには、管理者権限が必要です。[管理：コアサービス](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html)も参照してください。

### SDK の設定

下記の[SDK の設定](../../features/profile-merge-rules/merge-rules-start.md#configure-sdks)セクションも参照してください。

## レガシー DIL {#legacy-dil}

まだ [!DNL Experience Cloud ID Service] を使用していない場合は、是非使用することをお勧めします。しかし、新しいコードへの移行には、慎重な検討とテストが必要です。このような場合は、`DIL.create` 関数を調べ、以下のコードのサンプルのように適切に設定されていることを確認します。

<pre class="js"><code>DIL. create（{パートナー:「パートナー名」、DeclarID:{dpuuid:<i>dpuuid</i>，
 dpid:<i>dpid</i>}}）;</code>
</pre>

詳しくは、[!UICONTROL DIL]宣言済み ID 変数[の ](../../features/declared-ids.md#declared-id-variables) の節を参照してください。

### SDK の設定 {#configure-sdks-legacy-dil}

[!DNL SDK] コードに含まれるメソッドをチェックして、モバイルデバイス [!UICONTROL declared IDs][!DNL Android] や [!DNL iOS] 携帯端末を渡すことができます。[!DNL Android] と [!DNL iOS] のコードライブラリで、変数名は同じです。

* `dpid`：デバイス間データソース ID。
* `dpuuid`:（ [!UICONTROL declared ID] つまり、ユーザーID）。

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> デバイスタイプ </th> 
   <th colname="col2" class="entry"> メソッド </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>構文：</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>例：</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>構文：</b> </p><p>
    <code class="javascript">+（void） AudienceSetDpid:（NSString*） dpid
dpuuid:（NSString*） dpuuid; </code>
 </p>
    <p> <b>例：</b> </p><p>
    <code class="javascript">[ADBMobile AudienceSetpid:@"290" dpuuid:@"99301393923940"]; </code>
 </p>
    </td>
  </tr>
 </tbody>
</table>

[Android 用の Audience Manager メソッド](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html)と[ iOS 用の Audience Manager メソッド](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html)も参照してください。
