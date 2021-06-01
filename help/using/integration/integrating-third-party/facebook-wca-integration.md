---
description: このページでは、オンライン広告ターゲティングの透明性を向上させるため、Web ベースの Audience Manager オーディエンスセグメントを Facebook に送信する目的で Facebook Website Custom Audiences（WCA）ピクセルを作成するプロセスについて説明します。
seo-description: このページでは、オンライン広告ターゲティングの透明性を向上させるため、Web ベースの Audience Manager オーディエンスセグメントを Facebook に送信する目的で Facebook Website Custom Audiences（WCA）ピクセルを作成するプロセスについて説明します。
seo-title: Facebook WCA の統合
solution: Audience Manager
title: Facebook WCA の統合
feature: サードパーティ統合
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 100%

---

# [!DNL Facebook WCA] 統合 {#facebook-wca-integration}

このページでは、オンライン広告ターゲティングの透明性を向上させるため、Web ベースの [!DNL Audience Manager] オーディエンスセグメントを [!DNL Facebook]に 送信する目的で）[!DNL Facebook Website Custom Audiences]（[!DNL WCA]）ピクセルを作成するプロセスについて説明します。

## 概要 {#overview}

[Facebook Web サイトカスタムオーディエンス（WCA）](https://www.facebook.com/business/help/449542958510885)を使用すると、特定のページを訪問したユーザーや、Web サイトで特定のアクションを実行したユーザーのリストを作成できます。[!DNL Audience Manager] では、[!DNL URL] の宛先を使用して[!DNL WCA] でのアクティベートを有効にすることができます。これにより、ターゲティングをおこなうため、Web ベースのオーディエンスを [!DNL Facebook] に送信して、カスタムのピクセルベース統合を設定することができます。

![Facebook WCA の統合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> この機能を使用するには、[URL の宛先](/help/using/features/destinations/create-url-destination.md)のソーシャルプラットフォームオプションで、[!UICONTROL Website]オーディエンスを選択する必要があります。ソーシャルプラットフォームでは、プラットフォームへの送信時、リファラー情報のマスクを解除する必要があります。つまり、宛先プラットフォーム／パートナーは、リファラー [!DNL URL] の情報を見ることができます。

## 前提条件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] セグメントで、新しい 宛先に割り当てる準備を整えます。[!DNL Facebook]UI での[セグメントの作成方法](/help/using/features/segments/segment-builder.md)をご確認ください。[!DNL Audience Manager]
3. [!DNL Adobe Experience Platform Identity Service]（[!DNL ECID]）バージョン 4.1.0 以降。**[こちら](https://github.com/Adobe-Marketing-Cloud/id-service/releases)** から最新バージョンをダウンロードできます。
4. [!DNL Audience Manager Data Integration Library]（[!DNL DIL]）バージョン 9.0 以降。**[こちら](https://github.com/Adobe-Marketing-Cloud/dil/releases)**&#x200B;からダウンロードできます。また、[サーバー側転送（SSF）](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/server-side-forwarding/ssf.html)を使用して にデータを読み込む場合は、AppMeasurement バージョン 2.12 以降を使用する必要があります。[!DNL Audience Manager][Analytics Code Manager](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/code-manager-admin.html) を使用して [!DNL AppMeasurement] をダウンロードしてください。

手順 3 と 4 で、[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html?lang=ja) を使用して、ライブラリをインストールまたはアップグレードすることをお勧めします。

## 手順 1 - [!DNL Audience Manager] で [!UICONTROL Facebook Destination] を作成します。 {#step-1-create-facebook-destination}

[!DNL Audience Manager] で新しい [!UICONTROL URL Destination]を作成し、[!DNL Facebook Website Custom Audiences]と名付けます。宛先を作成する際には、以下の設定を使用してください。また、[URL の宛先の設定](/help/using/features/destinations/create-url-destination.md)ページを参考にすることもできます。

### 基本情報

* **[!UICONTROL Category]**: カスタム
* **[!UICONTROL Type]**：[!DNL URL]
* 「**[!UICONTROL Auto-fill Destination Mapping]**」チェックボックスを選択してから、「**[!UICONTROL Segment ID]**」を選択します。

### [!UICONTROL Data Export Labels]

オプション&#x200B;**[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**&#x200B;を選択します。

>[!NOTE]
>
> このエクスポートラベルを使用すると、デバイスグラフから派生したサードパーティのデータやデータを、セグメントに含めることができなくなります。

### 設定

* **[!UICONTROL URL type]**：**[!UICONTROL Website audience for social platforms]** を選択します。この [!UICONTROL URL Type] オプションを選択すると、[!DNL Audience Manager] は [!DNL Facebook WCA] ピクセルを実行する際にリファラー [!DNL URL] 情報を難読化しません。
* **[!UICONTROL Serialize]**：**[!UICONTROL Enable]** を選択します。
* 「**[!UICONTROL Base URL]**」と「**[!UICONTROL Secure URL]**」フィールドに、[!DNL Facebook WCA] ピクセルを入力します。
* **[!UICONTROL Delimiter]**：`,`

基本 [!DNL URL] の例：`https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

ページから実行されたピクセルの例。次の例は、3 つの [!DNL Audience Manager]（ID：3401321、2993399、3263410）の対象となるユーザーを表しています。

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| パラメーター | 説明 |
---------|----------|
| `id` | [!DNL Facebook] ピクセル ID。オーディエンスピクセルを作成する際に、[!DNL Facebook Ad Manager] ユーザーで見つけることができます。 |
| `ev` | イベント。任意の値。サイトでピクセルが実行し始めると、[!DNL Facebook Ad Manager] ユーザーインターフェイスに表示されます。詳しくは、[手順 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience) の [!UICONTROL Include] 項目を参照してください。 |
| `cd[segID]` | サイトでピクセルが起動を開始すると、[!DNL Facebook Ad Manager] 内で入力される追加パラメーター。`segID` は任意です。 |
| `%ALIAS%` | [!DNL Audience Manager] マクロ。これらのマクロは、サイト訪問者が対象となる [!DNL Audience Manager] [!UICONTROL segment] ID （コンマ区切り）へと動的に置き換えられます。 |

[!UICONTROL URL destination]の設定は、以下の画像のようになります。

![宛先の設定](/help/using/integration/assets/facebook-wca.png)

[!UICONTROL destination]を保存します。次に、**セグメントマッピング**&#x200B;の手順に進みます。

## 手順 2 - セグメントマッピング - セグメントを宛先にマッピングする {#step-2-segment-mappings}

[URL の宛先を設定](/help/using/features/destinations/create-url-destination.md)ワークフローで、新しく作成した[!UICONTROL destination]に適切なセグメントをマッピングします。マッピング値は、[!DNL Audience Manager] [!UICONTROL segment ID]を使用して自動生成されます。

該当する場合は終了日を入力します。終了日がない場合は空白のままにしてください。

## 手順 3 - [!DNL Facebook Ads Manager] 内で [!UICONTROL Audience] {#step-3-create-audience}

 [!DNL Facebook] のヘルプドキュメントの[ウェブサイトカスタムオーディエンスを作成する](https://www.facebook.com/business/help/666509013483225)を参照してください。以下の表の「[!UICONTROL Create Audience]」オプションを選択します。

| 項目 | 説明 |
---------|----------|
| Website traffic | カスタムの組み合わせ |
| Include | <ul><li>**[!UICONTROL Event]**／**[!UICONTROL Adobe-Audience-Manager-Segment]** を選択します。手順 1 のピクセルの例では `ev` パラメーターの値でした。ピクセルがまだ実行されていない場合、「**[!UICONTROL Event]**」オプションまたは **[!UICONTROL Adobe-Audience-Manager-Segment]** が [!DNL Facebook]に ユーザーインターフェイス表示されないことがあります。</li><li>パラメーターの追加：「`segID`」を選択します。</li><li><p>**contains** 演算子を選択します。</p><p>訪問者が複数のセグメントに振り分けられる可能性があり、ピクセルパラメーターに複数の[!UICONTROL segment IDs] が存在する可能性があることを考えると、この操作は重要です。等号（`=`）演算子を使用すると、訪問者がオーディエンスに認定されないことがあり、ボリュームは少なくなります。</p></li><li>値を入力：[!DNL Audience Manager] セグメント ID を入力します。</li></ul> |
| Add New Condition | オプションの設定。 |
| In the Last | オプションの設定。 |
| Audience Name | このオーディエンスに条件を追加する場合を除き、一貫性を保つため、同じ [!DNL Audience Manager] セグメント名を使用することをお勧めします。 |

## 手順 4 - [!UICONTROL Audience] を、 [!DNL Facebook Ads Manager] の [!UICONTROL Campaign] に割り当てる {#step-4-assign-audience-to-campaign}

[!DNL Custom Audience]を作成したら、広告キャンペーンに割り当てます。新しいキャンペーンを作成するか、既存のキャンペーンを編集すると、新しく作成したオーディエンスが [!DNL Facebook] ユーザーインターフェイスに表示されます。[!DNL Audience Manager] がセグメントに含まれている場合、サイトを訪問した際にブラウザーでそのピクセルを閲覧したユーザーを広告キャンペーンのターゲットとして設定します。

## 概要 {#summary}

これで、[!DNL Audience Manager] セグメントを [!DNL Facebook WCA] の宛先に割り当てました。[!DNL Audience Manager] は、ピクセル内の各セグメント ID を使用して、特定のセグメントのユーザーに対して [!DNL Facebook WCA] ピクセルを選択的に実行し、[!DNL Facebook Audience] を生成します。これにより、[!DNL Facebook Audience]が徐々に増加し、サイト上の該当する閲覧者に対して実行されるタグも増加します。

>[!NOTE]
>
> ユーザーが [!DNL Audience Manager] セグメントから除外された場合、現在のところ、[!DNL Audience Manager] では、ユーザーが [!DNL Custom Audience] からユーザーを削除するように [!DNL Facebook] に通知することはできません。

