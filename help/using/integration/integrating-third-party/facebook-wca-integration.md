---
description: このページでは、オンライン広告ターゲティングの透明性を向上させるため、Web ベースの Audience Manager オーディエンスセグメントを Facebook に送信する目的で Facebook Website Custom Audiences（WCA）ピクセルを作成するプロセスについて説明します。
seo-description: このページでは、オンライン広告ターゲティングの透明性を向上させるため、Web ベースの Audience Manager オーディエンスセグメントを Facebook に送信する目的で Facebook Website Custom Audiences（WCA）ピクセルを作成するプロセスについて説明します。
seo-title: Facebook WCA の統合
solution: Audience Manager
title: Facebook WCA の統合
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 56%

---


# Facebook WCA の統合 {#facebook-wca-integration}

This page illustrates the process of creating [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixels for the purposes of sending web-based [!DNL Audience Manager] audience segments to [!DNL Facebook], for online ad targeting with improved transparency.

## 概要 {#overview}

[Facebook Web サイトカスタムオーディエンス（WCA）](https://www.facebook.com/business/help/449542958510885)を使用すると、特定のページを訪問したユーザーや、Web サイトで特定のアクションを実行したユーザーのリストを作成できます。[!DNL Audience Manager] では、 の宛先を使用して でのアクティベートを有効にすることができます。これにより、ターゲティングをおこなうため、Web ベースのオーディエンスを に送信して、カスタムのピクセルベース統合を設定することができます。[!DNL WCA][!DNL URL][!DNL Facebook]

![Facebook WCA の統合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> この機能を使用するには、[URL の宛先の](/help/using/features/destinations/create-url-destination.md)ソーシャルプラットフォームオプションで、Web サイトオーディエンスを選択する必要があります。ソーシャルプラットフォームでは、プラットフォームへの送信時、リファラー情報のマスクを解除する必要があります。Please be aware that this means that the destination platform/partner will be able to see information in your referrer [!DNL URL].

## 前提条件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] セグメントを作成し、新しい [!DNL Facebook] 宛先に割り当てる準備ができている。  UI での[セグメントの作成方法](/help/using/features/segments/segment-builder.md)をご確認ください。[!DNL Audience Manager]
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID])バージョン4.1.0以降。 **[こちら](https://github.com/Adobe-Marketing-Cloud/id-service/releases)** から最新バージョンをダウンロードできます。
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL])バージョン9.0以降、こちらからダウンロード **[でき](https://github.com/Adobe-Marketing-Cloud/dil/releases)**ます。 また、[サーバー側転送（SSF）](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/server-side-forwarding/ssf.html)を使用して にデータを読み込む場合は、AppMeasurement バージョン 2.12 以降を使用する必要があります。[!DNL Audience Manager][!DNL AppMeasurement]Analyticsコードマネージャー[を使用してダウンロードします](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/code-manager-admin.html)。

手順 3 と 4 で、[Adobe Experience Platform Launch](https://docs.adobelaunch.com/) または [Adobe Dynamic Tag Management](https://docs.adobe.com/content/help/ja-JP/dtm/using/dtm-home.html) を使用して、ライブラリをインストールまたはアップグレードすることをお勧めします。

## 手順 1：Audience Manager で Facebook の宛先を作成する {#step-1-create-facebook-destination}

で新しいを作成 [!UICONTROL URL Destination] し、名前 [!DNL Audience Manager] を付け [!DNL Facebook Website Custom Audiences]ます。 宛先を作成する際には、以下の設定を使用してください。また、[URL の宛先の設定](/help/using/features/destinations/create-url-destination.md)ページを参考にすることもできます。

### Basic Information

* **[!UICONTROL Category]**: カスタム
* **[!UICONTROL Type]**: URL
* Select the **[!UICONTROL Auto-fill Destination Mapping]** check box, then select **[!UICONTROL Segment ID]**.

### Data Export Labels

オプションを選択し **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**&#x200B;ます。

>[!NOTE]
>
> このエクスポートラベルを使用すると、デバイスグラフから派生したサードパーティのデータやデータを、セグメントに含めることができなくなります。

### Configuration

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. By selecting this [!UICONTROL URL Type] option, [!DNL Audience Manager] does not obscure the referrer [!DNL URL] information when firing a [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* In the **[!UICONTROL Base URL]** and **[!UICONTROL Secure URL]** field, enter the [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: ,

基本 [!DNL URL] の例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

ページから実行されたピクセルの例。This example shows a user who qualifies for three [!DNL Audience Manager] segments, with the IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| パラメーター | 説明 |
---------|----------|
| `id` | Your [!DNL Facebook] pixel ID, which you can find in the [!DNL Facebook Ad Manager] user interface when creating audience pixels. |
| `ev` | イベント。This is an arbitrary value, which will appear in the [!DNL Facebook Ad Manager] user interface once the pixel begins to fire on site. See the [!UICONTROL Include] item in [Step 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), for more information. |
| `cd[segID]` | An additional parameter, which will begin to populate within the [!DNL Facebook Ad Manager] user interface once the pixel begins to fire on site. `segID` は任意です。 |
| `%ALIAS%` | An [!DNL Audience Manager] macro, which will be dynamically replaced with the [!DNL Audience Manager] segment IDs that the site visitor qualifies for, delimited by comma , |

Your [!UICONTROL URL destination] configuration should look like in the image below:

![宛先の設定](/help/using/integration/assets/facebook-wca.png)

宛先を保存します。次に、**セグメントマッピング**&#x200B;の手順に進みます。

## 手順 2：セグメントマッピング - セグメントを宛先にマッピングする {#step-2-segment-mappings}

[URL の宛先を設定](/help/using/features/destinations/create-url-destination.md)ワークフローで、新しく作成した宛先に適切なセグメントをマッピングします。Notice the mapping value is auto-populated with the [!DNL Audience Manager] segment ID.

該当する場合は終了日を入力します。終了日がない場合は空白のままにしてください。

## 手順 3：Facebook Ad Manager 内でオーディエンスを作成する {#step-3-create-audience}

 のヘルプドキュメントの[ウェブサイトカスタムオーディエンスを作成する](https://www.facebook.com/business/help/666509013483225)を参照してください。[!DNL Facebook]Select the [!UICONTROL Create Audience] options in the table below:

| 項目 | 説明 |
---------|----------|
| Website traffic | カスタムの組み合わせ |
| Include | <ul><li>**Event**／**Adobe-Audience-Manager-Segment** を選択します。手順 1 のピクセルの例では ev パラメーターの値でした。ピクセルがまだ実行されていない場合、「**Event**」オプションまたは **Adobe-Audience-Manager-Segment** が Facebook UI に表示されないことがあります。</li><li>パラメーターの追加：「`segID`」を選択します。</li><li><p>**contains** 演算子を選択します。</p><p>訪問者が複数のセグメントに振り分けられる可能性があり、ピクセルパラメーターに複数のセグメント ID が存在する可能性があることを考えると、この操作は重要です。等号（=）演算子を使用すると、訪問者がオーディエンスに認定されないことがあり、ボリュームは少なくなります。</p></li><li>Add a value: Enter the [!DNL Audience Manager] segment ID.</li></ul> |
| Add New Condition | オプションの設定。 |
| In the Last | オプションの設定。 |
| Audience Name | We recommend you use the same [!DNL Audience Manager] segment name for consistency, unless you are adding additional conditions to this Audience. |

## 手順 4：Facebook Ads Manager のキャンペーンにオーディエンスを割り当てる {#step-4-assign-audience-to-campaign}

After creating the [!DNL Custom Audience], assign it to an ad campaign. Create a new campaign or edit an existing one and you will find your newly created audience is listed in the [!DNL Facebook] user interface. Your ad campaign will target users who have seen the pixel fire on their browser when visiting your site, if [!DNL Audience Manager] includes them in the segment.

## 概要 {#summary}

Now that you have assigned your [!DNL Audience Manager] segment to the [!DNL Facebook WCA] destination, [!DNL Audience Manager] will selectively fire the [!DNL Facebook WCA] pixel to users of a given segment with the respective segment ID in the pixel to populate the [!DNL Facebook Audience]. This results in a gradual increase in the [!DNL Facebook Audience] the more the tag is fired to the applicable audience on your site.

>[!NOTE]
>
> If a user falls out of the [!DNL Audience Manager] segment, there is currently no way for [!DNL Audience Manager] to inform [!DNL Facebook] to remove the user from the [!DNL Custom Audience].