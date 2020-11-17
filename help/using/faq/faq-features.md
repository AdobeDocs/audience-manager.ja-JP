---
description: 製品および機能に関するよくある質問と問題点の説明です。
keywords: audience manager cookies
seo-description: 製品および機能に関するよくある質問と問題点の説明です。
seo-title: 製品の機能に関するよくある質問
solution: Audience Manager
title: 製品の機能に関するよくある質問
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 100%

---


# 製品の機能に関するよくある質問 {#product-features-and-functions-faq}

製品および機能に関するよくある質問と問題点の説明です。

 

<!-- 

faq_features_functions.xml

 -->

**組織 ID はどのようなもので、どうすれば見つかりますか？**

Folio Builder *`Organization ID`* は、[!DNL Audience Manager] や [!DNL Adobe Experience Cloud] が組織を識別するための一意の ID です。大文字と小文字が区別される 24 文字の英数字から成る文字列の後に [!UICONTROL @AdobeOrg] が付いたものです。

つまり、*`Organization ID`* は `1FD6776A524453CC0A490D44@AdobeOrg` のようになります。

*`Organization ID`* は、Audience Manager の [DIL](../dil/dil-overview.md) API、[Adobe Experience Platform ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)およびその他の [!DNL Experience Cloud] ソリューションで使用されます。*`Organization ID`* は、管理者権限を持つユーザーが [!DNL Adobe Admin Console] で確認できます。詳しくは、[管理 - ユーザー管理の FAQ](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/admin-getting-started.html) を参照してください。

 

**特性や宛先を一括で作成できますか？**

はい。詳しくは、[一括管理ツール](../reference/bulk-management-tools/bulk-management-intro.md)を参照してください。

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]ツールは、[!DNL Audience Manager] ではサポートされて&#x200B;*いません*。便宜上、提供されているものにすぎません。一括変更については、代わりに[Audience Manager API](../api/api.md) を使用することをお勧めします。

 

**宛先への一括 ID 書き出しを実行する際に、一部の顧客 ID が見つかりません。なぜこのような問題が発生するのでしょうか。**

デバイス ID（[AAM UUID](../reference/ids-in-aam.md)）が複数の CRM ID（[DPUUID](../reference/ids-in-aam.md)）にリンクされている場合は、最新のマッピングのみが書き出されます。このため、書き出されるデバイス ID の数が予想より少なくなる場合があります。

 

**[!DNL Audience Manager] を使用すれば、サードパーティのタグやピクセルを使用しなくてもよくなったり、ページの読み込み時間が改善されたりしますか？**

[!DNL Audience Manager] がサードパーティデータパートナーと統合されている場合は、ピクセルやタグの代わりに [!DNL Audience Manager] へのサーバー間 ID 呼び出しを使用することができます。この場合、[!DNL Audience Manager] は、ユーザーを初めて確認したときに 1 回だけ ID 呼び出しをおこない、その情報をサードパーティパートナーと同期します。これにより、ページごとに何度もピクセル呼び出しをおこなう必要はなくなります。ピクセル呼び出しが少なくなれば、ページ読み込み時間も短縮されます。

 

**データフィードを購読しました。そのデータはどこに保存されていますか？**

データフィードとフィードに含まれているすべての特性は、[!DNL Audience Manager] では、サブフォルダーおよび特性として表示されます。**[!UICONTROL Audience Data > Traits]** の順に選択し、[!UICONTROL 3rd-Party Data]フォルダーを開くと、特性が表示されます。また、このデータを使用してセグメントとモデルを作成できます。

 

**[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager では [!UICONTROL Tag Insertion Manager]（TIM）を使用して [!UICONTROL data collection code (DIL)] を作成および管理していました。この機能は時代後れとなったので、[!UICONTROL Dynamic Tag Manager (DTM)] で置き換えられた後、[!DNL Adobe Experience Platform Launch] で置き換えられました。詳しくは、[Adobe Experience Platform Launch](https://docs.adobelaunch.com/) および [Dynamic Tag Management](https://docs.adobe.com/content/help/ja-JP/dtm/using/dtm-home.html) を参照してください。

 

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

 

**Adobe Analytics セグメントと Audience Manager セグメントには何か違いがありますか？**

はい、あります。両者の違いについて詳しくは、[Analytics と Audience Manager について](https://docs.adobe.com/content/help/ja-JP/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)を参照してください。
