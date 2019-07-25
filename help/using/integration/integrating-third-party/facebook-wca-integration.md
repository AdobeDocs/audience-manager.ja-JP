---
description: このページでは、WebベースのAudience ManagerオーディエンスセグメントをFacebookに送信するための手順（WebベースのAudience ManagerオーディエンスセグメントをFacebookに送信する手順）を紹介します。これには、透明度の向上によるオンライン広告ターゲット設定が含まれます。
seo-description: このページでは、WebベースのAudience ManagerオーディエンスセグメントをFacebookに送信するための手順（WebベースのAudience ManagerオーディエンスセグメントをFacebookに送信する手順）を紹介します。これには、透明度の向上によるオンライン広告ターゲット設定が含まれます。
seo-title: Facebook WCAの統合
solution: Audience Manager
title: Facebook WCAの統合
translation-type: tm+mt
source-git-commit: 56999c1968a486bed0e2e672a4de1774d049e09d

---


# Facebook WCA Integration {#facebook-wca-integration}

このページでは、WebベースのAudience ManagerオーディエンスセグメントをFacebookに送信するための手順（WebベースのAudience ManagerオーディエンスセグメントをFacebookに送信する手順）を紹介します。これには、透明度の向上によるオンライン広告ターゲット設定が含まれます。

## 概要 {#overview}

[Facebook Webサイトカスタムオーディエンス（WCA）](https://www.facebook.com/business/help/449542958510885) を使用すると、特定のページを訪問したユーザーや、Webサイトで特定のアクションを実行した人のリストを作成できます。Audience Managerでは、URL宛先を使用してWCAでのアクティブ化を有効にすることができます。これにより、WebベースのオーディエンスをFacebookに送信して、ターゲティング用にWebベースのオーディエンスを送信できます。

![Facebook WCAの統合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> This capability requires that you select the Website audience for social platforms option in [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination). ソーシャルプラットフォームでは、プラットフォームに送信するときにリファラー情報をマスク解除する必要があります。つまり、宛先プラットフォーム/パートナーは、リファラーURLの情報を表示できることに注意してください。

## 前提条件 {#prerequisites}

1. Facebook広告アカウント
2. Audience Managerセグメントで、新しいFacebook宛先に割り当てる準備ができました。Here is [how to create a segment](/help/using/features/segments/segment-builder.md) in the Audience Manager UI.
3. Adobe Experience Cloud IDサービス（ECID）バージョン4.1.0以降。Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternatively, if you use [Server-Side Forwarding (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to import data into Audience Manager, you must use AppMeasurement version 2.12 or newer. [Analyticsコードマネージャーを使用してAppMeasurementをダウンロード](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)します。

[Adobe Launch](https://docs.adobelaunch.com/) または [Adobe Dynamic Tag Managementを使用して、手順3および4のライブラリをインストールまたはアップグレードすることをお勧め](https://marketing.adobe.com/resources/help/en_US/dtm/)します。

## Step 1 - Create a Facebook Destination in Audience Manager {#step-1-create-facebook-destination}

Audience Managerで新しいURL宛先を作成し、Facebook Webサイトカスタムオーディエンスという名前を付けます。宛先を作成する際には、以下の設定を使用してください。You can also refer to the [Configure a URL Destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) page.

**Basic Information**

* **カテゴリ**:カスタム
* **タイプ**:URL
* Select the **Auto-fill Destination Mapping** check box, then select **Segment ID**.

**Data Export Labels**

Select the option **This destination may enable a combination with personally identifiable information (PII)**.

>[!NOTE]
>
> このエクスポートラベルを使用すると、デバイスグラフから派生したサードパーティのデータやデータをセグメントに含めることができなくなります。

**設定**

* **URLタイプ**:ソーシャルプラットフォーム用 **のWebサイトオーディエンスを選択**&#x200B;します。このURLタイプオプションを選択すると、Audience ManagerはFacebook WCAピクセルを発生させたときにリファラーURL情報を隠しません。
* **シリアライズ**:「 **有効**」を選択します。
* **「ベースURL** 」フィールドと「 **セキュアURL"** フィールドに、Facebook WCAピクセルを入力します。
* **区切り**: ,

Base URL example: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

ページから呼び出されたピクセルの例。次の例は、ID3401321、2993399、3263410の3つのAudience Managerセグメントの資格を持つユーザーを示しています。

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| パラメーター | 説明 |
---------|----------|
| `id` | FacebookのピクセルID。オーディエンスピクセルを作成する際に、Facebook広告マネージャーUIで検索できます。 |
| `ev` | イベント. これは任意の値で、サイトでピクセルが起動し始めると、Facebook広告マネージャーUIに表示されます。See the Include item in [Step 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), for more information. |
| `cd[segID]` | サイトでピクセルが起動し始めると、Facebook広告マネージャーUI内に入力される追加パラメーター。`segID` は任意です。 |
| `%ALIAS%` | Audience Managerマクロ。これらのマクロは、サイト訪問者が対象とするAudience ManagerセグメントIDに、コンマで区切られて動的に置き換えられます。 |

URLの宛先設定は、以下の画像のようになります。

![傾向設定](/help/using/integration/assets/facebook-wca.png)

宛先を保存します。Then, you can proceed to the **Segment Mappings** step.

## Step 2 - Segment Mappings - Map Segment to Destination {#step-2-segment-mappings}

In the [Configure URL destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) workflow, map the applicable segment to your newly created destination. マッピング値にAudience ManagerセグメントIDが自動入力されます。

該当する場合は終了日を入力してください。終了日がない場合は空白のままにしてください。

## Step 3 - Create an Audience within Facebook Ads Manager {#step-3-create-audience}

See [Create a Website Custom Audience](https://www.facebook.com/business/help/666509013483225) in the Facebook help documentation. 以下の表の「オーディエンスを作成」オプションを選択します。


| 項目 | 説明 |
---------|----------|
| Webサイトトラフィック | カスタムの組み合わせ |
| 以下を含む | <ul><li>**イベント** / **Adobe- Audience- Manager- Segment**&#x200B;を選択します。手順1のpixelパラメーターのevパラメーターの値でした。Note that if the pixel is yet to fire, the **Event** option or **Adobe-Audience-Manager-Segment** may not appear in the Facebook UI.</li><li>Add a parameter: Select `segID`.</li><li><p>**contains** 演算子を選択します。</p><p>これは、訪問者が複数のセグメントに振り分けられることを前提としており、ピクセルパラメーターに複数のセグメントIDがあることを前提としています。等号（=）演算子を使用すると、オーディエンスに対する訪問者の資格がないことがあり、より少ないボリュームになります。</p></li><li>次の値を追加します。Audience ManagerセグメントIDを入力します。</li></ul> |
| 新しい条件を追加 | オプションの設定。 |
| 「最後」 | オプションの設定。 |
| オーディエンス名 | このオーディエンスに条件を追加する場合を除き、同じAudience Managerセグメント名を一貫性のために使用することをお勧めします。 |

## Step 4 - Assign the Audience to a Campaign in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

カスタムオーディエンスを作成したら、広告キャンペーンに割り当てます。新しいキャンペーンを作成するか、既存のキャンペーンを編集すると、新しく作成したオーディエンスがFacebook UIに表示されます。Audience Managerがセグメントに含まれている場合、貴社のサイトの訪問時に、そのピクセルを閲覧したユーザを広告キャンペーンにターゲット設定します。

## 概要 {#summary}

これで、Audience ManagerセグメントをFacebook WCAの宛先に割り当てたので、Audience Managerは、Facebookオーディエンスに入力するために、ピクセル内の各セグメントIDを使用してFacebook WCAピクセルを特定のセグメントのユーザーに選択的に実行します。これにより、Facebookのオーディエンスが徐々に増加し、サイト上の該当する閲覧者に対してタグがより多く呼び出されます。

>[!NOTE]
>
> ユーザーがAudience Managerセグメントからフォールアウトした場合、現在、Audience Managerは、ユーザーがカスタムオーディエンスからユーザーを削除するようにFacebookに通知できません。

