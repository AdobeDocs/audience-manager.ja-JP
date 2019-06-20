---
description: Audience Lab 機能に関するよくある質問です。
seo-description: Audience Lab 機能に関するよくある質問です。
seo-title: オーディエンスラボに関するよくある質問
solution: Audience Manager
title: オーディエンスラボに関するよくある質問
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab の FAQ{#audience-lab-faq}

Audience Lab 機能に関するよくある質問です。

<!-- 

audience-lab-faq.xml

 -->

<br> 

**テストグループに作成されたテストセグメントにはそれぞれ異なるセグメント ID が割り当てられますか？様々な送信先に ID をマッピングするにはどうすればよいですか？**

はい。テストセグメントにはそれぞれ異なるセグメント ID が割り当てられます。For destinations with [!UICONTROL Auto-fill Destination Mapping] or segments sent to [!DNL Google], [!UICONTROL Audience Lab] will handle the mapping values just like the destinations normally would.

<br> 

**同じコンバージョン特性を複数のテストグループに関連付けることはできますか？**

はい。できます。一方のテストでコンバージョン X に関連付けられた男性セグメントを使用し、他方のテストでコンバージョン X に関連付けられた女性セグメントを使用しているとします。これらは 2 つの異なるオーディエンスをテストしているので、両方のテストでコンバージョンが発生していても問題ありません。

<br> 

**あるテストグループは、テストセグメントの分割に認証済みプロファイルを使用しているとします。認証済みプロファイルは 4 つの[Audience Manager UUID](../reference/ids-in-aam.md)に関連付けられています。When the visitor exhibits a conversion trait from one of the four UUIDs, does[!UICONTROL Audience Lab]count this as one or four conversions?**

In this case, [!UICONTROL Audience Lab] only counts one conversion.

<br> 

**上記のケースで、訪問者は始めに認証済みプロファイルに関連付けられた 4 つの UUID の中の 1 つのコンバージョン特性を示し、次に他の 2 つの UUID のコンバージョン特性を示したとします。この場合、コンバージョンは 1 回または 3 回のどちらとしてカウントされますか？**

In this case, [!UICONTROL Audience Lab] counts three conversions, one for each device that has exhibited the authentication trait.

<br> 

**ユーザーはアクセス権を持つ[!UICONTROL Segment: Read-Only]ことができますが、セグメント作成アクセス[!UICONTROL Audience Lab]もテストできますか?**

See [Create Segment Test Group](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) for information on how to use [!UICONTROL Audience Lab] with [!UICONTROL RBAC] privileges.

**[!UICONTROL Audience Lab][!UICONTROL Profile Link Device Graph]外部デバイスグラフ（[Adobe Experience Cloud Device Co- op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html)、Tapad Device Graph、Liveramp Device Graph）と組み合わせて使用できますか。**

For now, [!UICONTROL Audience Lab] can only split out segment populations by the devices connected to a qualifying device, when using the [!UICONTROL Profile Link Device Graph]. We are working on adding support in [!UICONTROL Audience Lab] for the other device graphs and will let you know when we do so.
