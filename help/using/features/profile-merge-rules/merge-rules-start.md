---
description: プロファイル結合ルールを作成するには、この節で説明している手順を確認して完了してください。
seo-description: プロファイル結合ルールを作成するには、この節で説明している手順を確認して完了してください。
seo-title: プロファイル結合ルールの導入
solution: Audience Manager
title: プロファイル結合ルールの導入
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: dc22ed98b51b5633532bab45a79a14ee14dba5f5
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 100%

---


# プロファイル結合ルールの導入 {#getting-started-with-profile-merge-rules}

[!UICONTROL Profile Merge Rules]プロを作成するには、この節で説明している手順を確認して完了してください。

<!-- merge-rules-start.xml -->

## クロスデバイス対応データソースの作成 {#create-data-source}

クロスデバイス対応データソースを作成するには、**[!UICONTROL Audience Data > Data Sources > Add New]** の順に選択して、ここに記載されているそれぞれの節の手順を完了します。クロスデバイス対応データソースの作成や編集には、管理者権限が必要です。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>各種コントロールの説明については、[データソースの設定とメニューオプション](../datasources-list-and-settings.md#settings-menu-options)を参照してください。

## Data Source Details {#details}

「[!UICONTROL Data Source Details]」セクションを完了するには：

1. データソースの名前を入力します。
2. *（オプション）*&#x200B;データソースの説明を入力します。データソースの役割や目的を定義するのに、簡潔な説明が役に立ちます。
3. 統合コードを指定します。統合コードは、このデータソース専用の一意の ID です。
4. **[!UICONTROL ID Type]** リストで、「**[!UICONTROL Cross Device]**」を選択します。
5. **[!UICONTROL ID Definition]** リストで、データソースタイプを定義するオプションを選択します。オプションは次のとおりです。
   * **[!UICONTROL Person]**：個人を定義する ID。この ID は複数の [!DNL Audience Manager] ID にマッピングできます。
   * **[!UICONTROL Household]**：ユーザーのグループを定義する ID。この ID は複数の [!DNL Audience Manager] ID にマッピングできます。

## データ書き出しコントロール {#export-controls}

[データ書き出しコントロール](../data-export-controls.md)は、データソースおよび宛先に適用できるオプションの分類ルールです。宛先へのデータ送信がデータプライバシーや使用契約に違反する場合、データ送信を防止します。データ書き出しコントロールを使用しない場合は、「[!UICONTROL Data Export Controls]」セクションを省略してください。

## Data Source Settings {#settings}

「[!UICONTROL Data Source Settings]」セクションには複数のオプションが用意されていますが、クロスデバイス対応データソースの作成には次の 2 つのオプションが重要です。

* **[!UICONTROL Use as Authenticated Profile]**：デフォルトで選択されています。この設定により、独自の認証済みデータで [!UICONTROL Profile Merge Rule] を作成できます。

* **[!UICONTROL Use as a Device Graph]**：このコントロールは、データプロバイダーとして登録されているアカウントでのみ使用できます。このチェックボックスを選択すると、データソースがデバイスグラフとして作成され、[!DNL Audience Manager] の他のお客様と共有できるようになります。担当の [!DNL Audience Manager] コンサルタントと協力して、データプロバイダーとしてセットアップしたり、この[!UICONTROL Data Source]の共有相手となる顧客を指定したりします。コンサルタントは、社内のプロビジョニングプロセスを通じて、アカウントとデバイスグラフ共有をプロビジョニングします。

* **[!UICONTROL Data retention for inactive Customer IDs]**：非アクティブな顧客 ID のデータ保持期間を設定できます。これにより、Audience Manager プラットフォームに Audience Manager が最後に表示された後、Audience Manager がデータベースに顧客 ID を保持する期間を決定します。デフォルト値は 24 か月（720 日）です。設定できる最小値は 1 か月、最大値は 5 年です。すべての月は 30 日としてカウントされます。Audience Manager は、非アクティブな顧客 ID に設定したデータ保持に従って、非アクティブな顧客 ID を週 1 度削除するプロセスを実行します。

これらの設定と関連付けられているテキストフィールドでは、[!UICONTROL Data Source]の名前を[プロファイル統合ルールオプション](merge-rule-definitions.md)に表示されるエイリアスに置き換えることができます。例えば、**[!UICONTROL Use as Authenticated Profile]** にエイリアスを追加した場合は、その名前が [!UICONTROL Authenticated Profile Options] リストに表示されます。**[!UICONTROL Use as a Device Graph]** にエイリアスを追加した場合は、その名前が [!UICONTROL Device Options] リストに表示されます。

## プロファイル結合ルールの作成 {#create-profile-merge-rule}

[!UICONTROL Profile Merge Rule] を作成するには、**[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** の順に選択して、ここに記載されているそれぞれの節の手順を完了します。

クロスデバイス対応データソースをセットアップした後、最大 3 個の結合ルールを作成できます。[People-Based Destinations](../destinations/people-based-destinations-overview.md) に新規登録すると、4 番目のプロファイル結合ルール（[!UICONTROL All Cross-Device Profiles]）にアクセスできるようになります。

ルールの作成、編集、削除には、管理者権限が必要です。すべてのユーザーが既存の[!UICONTROL Profile Merge Rules]を表示および使用できます。

<!-- create-profile-merge-rule.xml -->

**前提条件：**[!UICONTROL Profile Merge Rule]の作成には、クロスデバイス対応データソースが必要です。[データソースの作成](../manage-datasources.md#create-data-source)を参照してください。

>[!TIP]
>
>各種コントロールの説明については、[定義済みのプロファイルの結合ルールオプション](merge-rule-definitions.md)を参照してください。

## 基本情報 {#basic-info}

「[!UICONTROL Basic Information]」セクションを完了するには：

1. [!UICONTROL Profile Merge Rule] に名前を付けます。
2. *（オプション）*[!UICONTROL Profile Merge Rule] の説明を入力します。ルールの役割や目的を定義するのに、簡潔な説明が役に立ちます。
3. *（オプション）*&#x200B;これをデフォルトの [!UICONTROL Profile Merge Rule] にしたい場合は、「**[!UICONTROL Set as default]**」を選択します。新規セグメントはデフォルトルールに自動的に関連付けられます。

## データ書き出しコントロール {#data-export-controls}

[データ書き出しコントロール](../data-export-controls.md)は、[!UICONTROL Profile Merge Rule]に適用できるオプションの分類ルールです。宛先へのデータ送信がデータプライバシーや使用契約に違反する場合、データ送信を防止します。データ書き出しコントロールを使用しない場合は、「[!UICONTROL Data Export Controls]」セクションを省略してください。

## Profile Merge Rule Setup {#profile-merge-rule-setup}

「[!UICONTROL Proflie Merge Rule Setup]」セクションを完了するには：

1. 「**[!UICONTROL Authenticated Option]**」を選択します。オプションは次のとおりです。
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. **[!UICONTROL Authenticated Profile Option]** を（最大 3 つ）選択します。これらは以前作成した[クロスデバイス対応データソース](merge-rules-start.md)です。
3. 「**[!UICONTROL Device Option]**」を選択します。オプションは次のとおりです。
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. 「**[!UICONTROL Save]**」をクリックします。

### クロスデバイス ID をユーザーキーとして使用する Adobe Campaign の宛先に関する考慮事項 {#considerations}

2019 年後半に、クロスデバイス ID を使用して生成されたバッチファイルの精度を向上させるために、一連のプロファイル結合ルールの機能強化がリリースされました。これらの機能強化は、2020 年 3 月 17 日（火）より、Audience Manager インスタンスで厳密に適用されます。そのため、クロスプロファイル ID を使用して宛先にマッピングされたセグメントは、一部のデバイス結合ルールの設定でエクスポートの生成を停止します。

クロスデバイス ID（Adobe Campaign など）を使用して、Audience Manager インスタンスと宛先を正しく統合するには、次の要件を満たす必要があります。

1. Adobe Campaign の宣言された ID の宛先にマッピングされたセグメントで使用されるプロファイルの結合ルールを確認します。認証済みのすべてのプロファイルをエクスポートに含めることができるように、プロファイルのマージルールでは [!UICONTROL Last Authenticated Profile] オプションを使用する必要があります。プロファイル結合ルールで別のオプションを使用している場合は、[!UICONTROL Last Authenticated Profile] に切り替えます。
2. プロファイル結合ルール設定で、Adobe Campaign の宣言済み ID データソースを選択します。

>[!NOTE]
>
> 上記の手順に基づいて、[!UICONTROL Profile Merge Rules] が最大数に達しており、設定に関するサポートが必要な場合は、カスタマーケアにお問い合わせください。

## 結合ルールコードの設定 {#configure-merge-rule-code}

下の説明に従って、結合ルールと連携して動作するための [!UICONTROL Adobe Experience Platform Identity Service]、[!UICONTROL DIL]、およびモバイル [!DNL SDK] コードを設定します。

<!-- merge-rules-configure-code.xml -->

### 前提条件

これらの手順を完了する&#x200B;*前*&#x200B;に、[クロスデバイス対応データソース](#create-data-source)および[プロファイル結合ルール](#create-profile-merge-rule)を設定する必要があります。

## Adobe Experience Platform ID サービスの顧客の場合 {#id-service-customers}

[!UICONTROL Profile Merge Rules]を操作する際は、[!UICONTROL Adobe Experience Platform Identity Service] および最新バージョンの [DIL](../../dil/dil-overview.md) の使用をお勧めします。ただし、この機能を使用する場合に [!UICONTROL Adobe Experience Platform Identity Service] を使用することは必須ではありません。[!UICONTROL DIL] のみを使用する場合は、下記の[レガシー DIL](#legacy-dil) の節を参照してください。

### 顧客 ID 設定関数の設定

[!UICONTROL Adobe Experience Platform Identity Service] を操作する差異、`setCustomerIDs` 関数は宣言された ID を [!DNL Audience Manager] に渡します。プロファイル結合ルールを使用する場合、`setCustomerIDs` を変更して、クロスデバイス対応データソースの作成時に指定した統合コードを使用するよう設定します。例えば、統合コード `my_datasource_ic` でクロスデバイス対応データソースを作成したとします。宣言された ID を渡すには、以下の変更後のコードのサンプルに示すように、統合コードを訪問者 ID 関数に追加します。

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

詳しくは、[クロスデバイス対応データソースの作成](#create-data-source)と[顧客 ID と認証状態](https://docs.adobe.com/content/help/ja-JP/id-service/using/reference/authenticated-state.html)を参照してください。

### `DIL.create` 関数の設定

[!UICONTROL DIL] の最新バージョンでは、`DIL.create` の `visitorService` から [!UICONTROL declared ID] が自動取得されるようになりました（[宣言された ID 変数](../declared-ids.md#declared-id-variables)を参照）。`DIL.create` 関数を調べ、以下のコードのサンプルのように適切に設定されていることを確認します。

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

namespace キー値ペアの `*`MCORG`*` 変数は [!DNL Experience Cloud] の組織 ID です。この ID がわからない場合、[!UICONTROL Administration] ダッシュボードの「[!DNL Experience Cloud]」セクションで確認できます。このダッシュボードを表示するには、管理者権限が必要です。[管理：コアサービス](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/admin-getting-started.html)も参照してください。

### SDK の設定

下記の [SDK の設定](#configure-sdks-legacy-dil)セクションも参照してください。

## レガシー DIL {#legacy-dil}

まだ [!DNL Adobe Experience Platform Identity Service] を使用していない場合は、是非使用することをお勧めします。しかし、新しいコードへの移行には、慎重な検討とテストが必要です。このような場合は、`DIL.create` 関数を調べ、以下のコードのサンプルのように適切に設定されていることを確認します。

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

詳しくは、[宣言された ID 変数](../declared-ids.md#declared-id-variables)の [!UICONTROL DIL] の節を参照してください。

### SDK の設定 {#configure-sdks-legacy-dil}

[!UICONTROL declared IDs] を [!DNL Android] および [!DNL iOS] モバイルデバイスから渡す方法を [!DNL SDK] コードで確認します。[!DNL Android] と [!DNL iOS] のコードライブラリで、変数名は同じです。

* `dpid`：クロスデバイス対応データソース ID。
* `dpuuid`：[!UICONTROL declared ID]（例：ユーザー ID）。

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
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>例：</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

[Android 用の Audience Manager メソッド](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html)と[ iOS 用の Audience Manager メソッド](https://docs.adobe.com/content/help/ja-JP/mobile-services/ios/aam-methods.html)も参照してください。

>[!MORELIKETHIS]
>
>* [データソースの作成](../manage-datasources.md#create-data-source)

