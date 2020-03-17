---
description: 製品および機能に関するよくある質問と問題点の説明です。
keywords: audience manager cookies
seo-description: 製品および機能に関するよくある質問と問題点の説明です。
seo-title: 製品の機能に関するよくある質問
solution: Audience Manager
title: 製品の機能に関するよくある質問
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# 製品の機能に関するよくある質問{#product-features-and-functions-faq}

製品および機能に関するよくある質問と問題点の説明です。

<br> 

<!-- 

faq_features_functions.xml

 -->

**組織 ID はどのようなもので、どうすれば見つかりますか？**

Folio Builder *`Organization ID`* は、[!DNL Audience Manager] や [!DNL Adobe Experience Cloud] が組織を識別するための一意の ID です。大文字と小文字を区別する 24 文字の英数字から成る文字列の後に [!UICONTROL @AdobeOrg] が付いたものです。

つまり、*`Organization ID`* は `1FD6776A524453CC0A490D44@AdobeOrg` のようになります。

これは *`Organization ID`* 、Audience Managerの [DIL](../dil/dil-overview.md) API、 [Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/)、その他のソリューションで使用され [!DNL Experience Cloud] ます。 *`Organization ID`* は、管理者権限を持つユーザーが [!DNL Adobe Admin Console] で確認できます。詳しくは、[管理 - ユーザー管理の FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)を参照してください。

<br> 

**特性や宛先を一括で作成できますか？**

はい。詳しくは、[一括管理ツール](../reference/bulk-management-tools/bulk-management-intro.md)を参照してください。

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]ツールは、[!DNL Audience Manager] ではサポートされて&#x200B;*いません*。便宜上、提供されているものにすぎません。一括変更については、代わりに[Audience Manager API](../api/api.md) を使用することをお勧めします。

<br> 

**[!DNL Audience Manager]を使用すれば、サードパーティのタグやピクセルを使用しなくてもよくなったり、ページの読み込み時間が改善されたりしますか？**

[!DNL Audience Manager] がサードパーティデータパートナーと統合されている場合は、ピクセルやタグの代わりに [!DNL Audience Manager] へのサーバー間 ID 呼び出しを使用することができます。この場合、[!DNL Audience Manager] は、ユーザーを初めて確認したときに 1 回だけ ID 呼び出しをおこない、その情報をサードパーティパートナーと同期します。これにより、ページごとに何度もピクセル呼び出しをおこなう必要はなくなります。ピクセル呼び出しが少なくなれば、ページ読み込み時間も短縮されます。

<br> 

**データフィードを購読しました。そのデータはどこに保存されていますか？**

データフィードとフィードに含まれているすべての特性は、[!DNL Audience Manager] では、サブフォルダーおよび特性として表示されます。**[!UICONTROL Audience Data > Traits]** を選択し、[!UICONTROL 3rd-Party Data]フォルダーを開くと、特性が表示されます。また、このデータを使用してセグメントとモデルを作成できます。

<br> 

**[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager は [!UICONTROL Tag Insertion Manager]（TIM）を使用して [!UICONTROL data collection code (DIL)] を作成および管理します。この機能は廃止され、[!UICONTROL Dynamic Tag Manager (DTM)] に置き換えられた後、[!DNL Adobe Experience Platform Launch] に置き換えられました。For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**アルゴリズムモデルと特性レコメンデーションの違いは何ですか？どのようなタイミングで使用すればよいですか？**

**アルゴリズムモデル**

アルゴリズムモデルは、最も影響力のある特性を見つけ、それらの特性に基づいてユーザーを評価し、各ユーザーに個別のスコアを割り当てます。次に、ユーザーをターゲットにするアルゴリズムの特性を作成します。特性ビルダーの精度コントロールとリーチコントロールを使用すれば、ターゲットに設定したい影響力のある特性を持つすべてのユーザーを指定できます。

アルゴリズムモデルを使用すれば、様々な精度レベルでユーザーを選択したり、Audience Lab でテストしたりでき、ユーザーのグループのコンバージョン率が向上します。[Audience Lab でのモデルの比較](../features/audience-lab/audience-lab-use-cases.md#compare-models)の詳細なユースケースを参照してください。

アルゴリズムモデルでは、モデルは 8 日ごとに実行され、アルゴリズム特性の対象となるユーザーが更新されます。

**特性レコメンデーション**

特性レコメンデーションを使用すれば、セグメントの場合と同様、他の特性に関するインサイトを簡単に得ることができます。

特性レコメンデーションは、次の場合に使用してください。

* セグメントの作成中に、すばやくインサイトを得る必要がある場合。
* 短時間のキャンペーンでセグメントを使用している場合、またはコンバージョンしたオーディエンスをすばやく抑制したい場合。
* リーチを最大化したい場合。

<br> 

**Adobe Analytics セグメントと Audience Manager セグメントには何か違いがありますか？**

はい、あります。両者の違いについて詳しくは、[Analytics と Audience Manager について](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html)を参照してください。
