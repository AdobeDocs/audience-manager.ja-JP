---
description: 製品および機能に関するよくある質問と問題点の説明です。
keywords: Audience Manager の Cookie
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: 製品の機能に関するよくある質問
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
TQID: https://experienceleague.adobe.com/gsJ4qXlNDpfWmTq0jjmtjfUWI60yRr7uBTxZjsF-pQE
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cbid: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f2fdbb191013b0bcb9bdab0529e3b7f3c872fd54
workflow-type: tm+mt
source-wordcount: 428
ht-degree: 94%

---

# 製品の機能に関するよくある質問{#product-features-and-functions-faq}

製品および機能に関するよくある質問と問題点の説明です。

 

<!-- 

faq_features_functions.xml

 -->

**組織 ID はどのようなもので、どうすれば見つかりますか？**

*`Organization ID`*&#x200B;は、[!DNL Audience Manager]と[!DNL Adobe Experience Cloud]の組織を識別する一意のIDです。 大文字と小文字が区別される 24 文字の英数字から成る文字列の後に [!UICONTROL @AdobeOrg] が付いたものです。

つまり、*`Organization ID`* は `1FD6776A524453CC0A490D44@AdobeOrg` のようになります。

*`Organization ID`* は、Audience Manager の [DIL](../dil/dil-overview.md) API、[Adobe Experience Platform ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)およびその他の [!DNL Experience Cloud] ソリューションで使用されます。 *`Organization ID`* は、管理者権限を持つユーザーが [!DNL Adobe Admin Console] で確認できます。 詳しくは、[管理 - ユーザー管理の FAQ](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=ja) を参照してください。

 

**特性や宛先を一括で作成できますか？**

はい。 詳しくは、[一括管理ツール](../reference/bulk-management-tools/bulk-management-intro.md)を参照してください。

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]ツールは、[!DNL Audience Manager] ではサポートされて&#x200B;*いません*。 便宜上、提供されているものにすぎません。 一括変更の場合は、代わりに[Audience Manager API](../api/api.md)を使用することをお勧めします。

 

**宛先への一括 ID 書き出しを実行する際に、一部の顧客 ID が見つかりません。 なぜこのような問題が発生するのでしょうか。**

デバイス ID（[AAM UUID](../reference/ids-in-aam.md)）が複数の CRM ID（[DPUUID](../reference/ids-in-aam.md)）にリンクされている場合は、最新のマッピングのみが書き出されます。 このため、書き出されるデバイス ID の数が予想より少なくなる場合があります。

 

**[!DNL Audience Manager] を使用すれば、サードパーティのタグやピクセルを使用しなくてもよくなったり、ページの読み込み時間が改善されたりしますか？**

[!DNL Audience Manager] がサードパーティデータパートナーと統合されている場合は、ピクセルやタグの代わりに [!DNL Audience Manager] へのサーバー間 ID 呼び出しを使用することができます。 この場合、[!DNL Audience Manager] は、ユーザーを初めて確認したときに 1 回だけ ID 呼び出しをおこない、その情報をサードパーティパートナーと同期します。 これにより、ページごとに何度もピクセル呼び出しをおこなう必要はなくなります。 ピクセル呼び出しが少なくなれば、ページ読み込み時間も短縮されます。

 

**データフィードを購読しました。 そのデータはどこに保存されていますか？**

データフィードとフィードに含まれているすべての特性は、[!DNL Audience Manager] では、サブフォルダーおよび特性として表示されます。 **[!UICONTROL Audience Data > Traits]** の順に選択し、[!UICONTROL 3rd-Party Data]フォルダーを開くと、特性が表示されます。また、このデータを使用してセグメントとモデルを作成できます。

 

**[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager では [!UICONTROL Tag Insertion Manager]（TIM）を使用して [!UICONTROL data collection code (DIL)] を作成および管理していました。 この機能は時代後れとなったので、[!UICONTROL Dynamic Tag Manager (DTM)] で置き換えられた後、[!DNL Adobe Experience Platform Tags] で置き換えられました。 詳しくは、[Adobe Experience Platform タグ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja)を参照してください。

 

**Adobe Analytics セグメントと Audience Manager セグメントには何か違いがありますか？**

はい、あります。両者の違いについて詳しくは、[Analytics と Audience Manager について](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=ja)を参照してください。
