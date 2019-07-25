---
description: 製品および機能に関するよくある質問と問題点の説明です。
keywords: Audience Manager の Cookie
seo-description: 製品および機能に関するよくある質問と問題点の説明です。
seo-title: 製品の特長と機能の FAQ
solution: Audience Manager
title: 製品の特長と機能の FAQ
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 製品の特長と機能の FAQ{#product-features-and-functions-faq}

製品および機能に関するよくある質問と問題点の説明です。

<br> 

<!-- 

faq_features_functions.xml

 -->

**組織 ID はどのようなもので、どうすれば見つかりますか？**

"*`Organization ID`* は、[!DNL Audience Manager] や [!DNL Adobe Experience Cloud] が組織を識別するための一意の ID です。It consists of a case-sensitive, 24-character alphanumeric string followed by [!UICONTROL @AdobeOrg].

つまり、*`Organization ID`* は `1FD6776A524453CC0A490D44@AdobeOrg` のようになります。

The *`Organization ID`* is used by Audience Manager's [DIL](../dil/dil-overview.md) API, the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/), and other [!DNL Experience Cloud] solutions. *`Organization ID`* は、管理者権限を持つユーザーが [!DNL Adobe Admin Console] で確認できます。詳しくは、[管理 - ユーザー管理の FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)を参照してください。

<br> 

**特性や宛先を一括で作成できますか？**

はい。詳しくは、[一括管理ツール](../reference/bulk-management-tools/bulk-management-intro.md)を参照してください。

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools] ツール *は* サポート [!DNL Audience Manager]されていません。便宜上、提供されているものにすぎません。一括変更については、代わりに   [Audience Manager API](../api/api.md) を使用することをお勧めします。

<br> 

**[!DNL Audience Manager]を使用すれば、サードパーティのタグやピクセルを使用しなくてもよくなったり、ページの読み込み時間が改善されたりしますか？**

[!DNL Audience Manager] がサードパーティデータパートナーと統合されている場合は、ピクセルやタグの代わりに [!DNL Audience Manager] へのサーバー間 ID 呼び出しを使用することができます。この場合、[!DNL Audience Manager] は、ユーザーを初めて確認したときに 1 回だけ ID 呼び出しをおこない、その情報をサードパーティパートナーと同期します。これにより、ページごとに何度もピクセル呼び出しをおこなう必要はなくなります。ピクセル呼び出しが少なくなれば、ページ読み込み時間も短縮されます。

<br> 

**データフィードを購読しました。そのデータはどこに保存されていますか？**

データフィードとフィードに含まれているすべての特性は、[!DNL Audience Manager] では、サブフォルダーおよび特性として表示されます。Go to **[!UICONTROL Audience Data > Traits]** and expand the [!UICONTROL 3rd-Party Data] folder to view your traits or create segments and models with this data.

<br> 

**[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. 詳しくは、[Adobe Launch](https://docs.adobelaunch.com/) および [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) を参照してください。

<br> 

**アルゴリズムモデルと特性Recommendationsの違いは何ですか?When should I use each of them?**

**アルゴリズムモデル**

アルゴリズムモデルは、影響力のある特性だけでなく、それらの特性に基づいてユーザーをスコアし、各ユーザーに個々のスコアを割り当てます。次に、アルゴリズムの特性を作成してユーザーをターゲットにします。特性ビルダーの精度コントロールとリーチコントロールを使用すると、ターゲット設定したい影響力のある特性を持つユーザーをすべて指定できます。

アルゴリズムモデルを使用すると、様々な精度レベルでユーザーを選択し、オーディエンスラボでテストして、ユーザーのグループのコンバージョン率が向上します。See the detailed use case in [Compare Models in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

アルゴリズムモデルでは、モデルは8日ごとに実行され、アルゴリズムの特徴の対象となるユーザーが更新されます。

**特性レコメンデーション**

特性レコメンデーションは、セグメントで使用しているものと類似した他の特性に関するインサイトを簡単に得るための手段です。

Trait Recommendationsは、以下の場合に使用してください。

* セグメントの作成中に、すばやくインサイトを設定する必要があります。
* 短時間キャンペーンでセグメントを使用しているか、コンバージョンしたオーディエンスをすばやく抑制したい場合、
* リーチを最大化しようとしています。

<br> 

**Adobe Analytics セグメントと Audience Manager セグメントには何か違いがありますか？**

はい、あります。両者の違いについて詳しくは、[Analytics と Audience Manager について](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html)を参照してください。
