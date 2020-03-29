---
description: このページでは、オンライン広告ターゲティングの透明性を向上させるため、Web ベースの Audience Manager オーディエンスセグメントを Facebook に送信する目的で Facebook Website Custom Audiences（WCA）ピクセルを作成するプロセスについて説明します。
seo-description: このページでは、オンライン広告ターゲティングの透明性を向上させるため、Web ベースの Audience Manager オーディエンスセグメントを Facebook に送信する目的で Facebook Website Custom Audiences（WCA）ピクセルを作成するプロセスについて説明します。
seo-title: Facebook WCA の統合
solution: Audience Manager
title: Facebook WCA の統合
translation-type: ht
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Facebook WCA の統合 {#facebook-wca-integration}

このページでは、オンライン広告ターゲティングの透明性を向上させるため、Web ベースの Audience Manager オーディエンスセグメントを Facebook に送信する目的で Facebook Website Custom Audiences（WCA）ピクセルを作成するプロセスについて説明します。

## 概要 {#overview}

[Facebook Web サイトカスタムオーディエンス（WCA）](https://www.facebook.com/business/help/449542958510885)を使用すると、特定のページを訪問したユーザーや、Web サイトで特定のアクションを実行したユーザーのリストを作成できます。Audience Manager では、URL の宛先を使用して WCA でのアクティベートを有効にすることができます。これにより、ターゲティングをおこなうため、Web ベースのオーディエンスを Facebook に送信して、カスタムのピクセルベース統合を設定することができます。

![Facebook WCA の統合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> この機能を使用するには、[URL の宛先の](/help/using/features/destinations/create-url-destination.md)ソーシャルプラットフォームオプションで、Web サイトオーディエンスを選択する必要があります。ソーシャルプラットフォームでは、プラットフォームへの送信時、リファラー情報のマスクを解除する必要があります。つまり、宛先プラットフォーム／パートナーは、リファラー URL の情報を見ることができます。

## 前提条件 {#prerequisites}

1. Facebook 広告アカウント
2. Audience Manager セグメントで、新しい Facebook 宛先に割り当てる準備を整えます。Audience Manager UI での[セグメントの作成方法](/help/using/features/segments/segment-builder.md)をご確認ください。
3. アドビの Adobe Experience Platform ID サービス（ECID）バージョン 4.1.0 以降。**[こちら](https://github.com/Adobe-Marketing-Cloud/id-service/releases)** から最新バージョンをダウンロードできます。
4. Audience Manager Data Integration Library（DIL）バージョン 9.0 以降（**[こちら](https://github.com/Adobe-Marketing-Cloud/dil/releases)** からダウンロード可能）。また、[サーバー側転送（SSF）](https://marketing.adobe.com/resources/help/ja_JP/reference/ssf.html)を使用して Audience Manager にデータを読み込む場合は、AppMeasurement バージョン 2.12 以降を使用する必要があります。[Analytics コードマネージャー](https://marketing.adobe.com/resources/help/ja_JP/reference/code_manager_admin.html)を使用して AppMeasurement をダウンロードしてください。

手順 3 と 4 で、[Adobe Experience Platform Launch](https://docs.adobelaunch.com/) または [Adobe Dynamic Tag Management](https://marketing.adobe.com/resources/help/ja_JP/dtm/) を使用して、ライブラリをインストールまたはアップグレードすることをお勧めします。

## 手順 1：Audience Manager で Facebook の宛先を作成する {#step-1-create-facebook-destination}

Audience Manager で新しい URL の宛先を作成し、「Facebook Web サイトカスタムオーディエンス」という名前を付けます。宛先を作成する際には、以下の設定を使用してください。また、[URL の宛先の設定](/help/using/features/destinations/create-url-destination.md)ページを参考にすることもできます。

**Basic Information**

* **Category**：Custom
* **Type**：URL
* 「**Auto-fill Destination Mapping**」チェックボックスを選択してから、「**Segment ID**」を選択します。

**Data Export Labels**

「**This destination may enable a combination with personally identifiable information (PII)**」オプションを選択します。

>[!NOTE]
>
> このエクスポートラベルを使用すると、デバイスグラフから派生したサードパーティのデータやデータを、セグメントに含めることができなくなります。

**Configuration**

* **URL type**：「**Website audience for social platforms**」を選択します。この URL タイプオプションを選択すると、Audience Manager は Facebook WCA ピクセルを実行する際にリファラー URL 情報を難読化しません。
* **Serialize**：「**Enable**」を選択します。
* 「**Base URL**」と「**Secure URL**」フィールドに、Facebook WCA ピクセルを入力します。
* **Delimiter**：,

ベース URL の例：`https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

ページから実行されたピクセルの例。次の例は、3 つの Audience Manager セグメント（ID：3401321、2993399、3263410）の対象となるユーザーを表しています。

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| パラメーター | 説明 |
---------|----------|
| `id` | Facebook ピクセル ID。オーディエンスピクセルを作成する際に、Facebook Ad Manager UI で見つけることができます。 |
| `ev` | イベント。任意の値。サイトでピクセルが実行し始めると、Facebook Ad Manager UI に表示されます。詳細については、[手順 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience) に含まれる項目を参照してください。 |
| `cd[segID]` | サイトでピクセルが起動を開始すると、Facebook Ad Manager UI 内で入力される追加パラメーター。`segID` は任意です。 |
| `%ALIAS%` | Audience Manager マクロ。これらのマクロは、サイト訪問者が対象となる Audience Manager セグメント ID （コンマ区切り）へと動的に置き換えられます。 |

URL の宛先設定は、以下の画像のようになります。

![宛先の設定](/help/using/integration/assets/facebook-wca.png)

宛先を保存します。次に、**セグメントマッピング**&#x200B;の手順に進みます。

## 手順 2：セグメントマッピング - セグメントを宛先にマッピングする {#step-2-segment-mappings}

[URL の宛先を設定](/help/using/features/destinations/create-url-destination.md)ワークフローで、新しく作成した宛先に適切なセグメントをマッピングします。マッピング値には、Audience Manager セグメント ID が自動入力されます。

該当する場合は終了日を入力します。終了日がない場合は空白のままにしてください。

## 手順 3：Facebook Ad Manager 内でオーディエンスを作成する {#step-3-create-audience}

Facebook のヘルプドキュメントの[ウェブサイトカスタムオーディエンスを作成する](https://www.facebook.com/business/help/666509013483225)を参照してください。以下の表の「Create Audience」オプションを選択します。


| 項目 | 説明 |
---------|----------|
| Website traffic | カスタムの組み合わせ |
| Include | <ul><li>**Event**／**Adobe-Audience-Manager-Segment** を選択します。手順 1 のピクセルの例では ev パラメーターの値でした。ピクセルがまだ実行されていない場合、「**Event**」オプションまたは **Adobe-Audience-Manager-Segment** が Facebook UI に表示されないことがあります。</li><li>パラメーターの追加：「`segID`」を選択します。</li><li><p>**contains** 演算子を選択します。</p><p>訪問者が複数のセグメントに振り分けられる可能性があり、ピクセルパラメーターに複数のセグメント ID が存在する可能性があることを考えると、この操作は重要です。等号（=）演算子を使用すると、訪問者がオーディエンスに認定されないことがあり、ボリュームは少なくなります。</p></li><li>値を入力：Audience Manager セグメント ID を入力します。</li></ul> |
| Add New Condition | オプションの設定。 |
| In the Last | オプションの設定。 |
| Audience Name | このオーディエンスに条件を追加する場合を除き、一貫性を保つため、同じ Audience Manager セグメント名を使用することをお勧めします。 |

## 手順 4：Facebook Ads Manager のキャンペーンにオーディエンスを割り当てる {#step-4-assign-audience-to-campaign}

カスタムオーディエンスを作成したら、広告キャンペーンに割り当てます。新しいキャンペーンを作成するか、既存のキャンペーンを編集すると、新しく作成したオーディエンスが Facebook UI に表示されます。Audience Manager がセグメントに含まれている場合、サイトを訪問した際にブラウザーでそのピクセルを閲覧したユーザーを広告キャンペーンのターゲットとして設定します。

## 概要 {#summary}

これで、Audience Manager セグメントを Facebook WCA の宛先に割り当てました。Audience Manager は、ピクセル内の各セグメント ID を使用して、特定のセグメントのユーザーに対して Facebook WCA ピクセルを選択的に実行し、Facebook オーディエンスを生成します。これにより、Facebook のオーディエンスが徐々に増加し、サイト上の該当する閲覧者に対して実行されるタグも増加します。

>[!NOTE]
>
> ユーザーが Audience Manager セグメントから除外された場合、現在のところ、Audience Manager では、ユーザーがカスタムオーディエンスからユーザーを削除するように Facebook に通知することはできません。

