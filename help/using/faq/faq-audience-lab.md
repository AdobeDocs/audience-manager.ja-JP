---
description: Audience Lab 機能に関するよくある質問です。
seo-description: Audience Lab 機能に関するよくある質問です。
seo-title: Audience Lab に関するよくある質問
solution: Audience Manager
title: Audience Lab に関するよくある質問
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 100%

---


# Audience Lab に関するよくある質問 {#audience-lab-faq}

Audience Lab 機能に関するよくある質問です。

<!-- 

audience-lab-faq.xml

 -->

<br> 

**テストグループに作成されたテストセグメントにはそれぞれ異なるセグメント ID が割り当てられますか？様々な宛先に ID をマッピングするにはどうすればよいですか？**

はい。テストセグメントにはそれぞれ異なるセグメント ID が割り当てられます。[!UICONTROL Auto-fill Destination Mapping]を使用する宛先、またはセグメントの宛先が [!DNL Google] である場合、[!UICONTROL Audience Lab]は通常の宛先の場合と同様にマッピング値を処理します。

<br> 

**同じコンバージョン特性を複数のテストグループに関連付けることはできますか？**

はい。できます。一方のテストでコンバージョン X に関連付けられた男性セグメントを使用し、他方のテストでコンバージョン X に関連付けられた女性セグメントを使用しているとします。これらは 2 つの異なるオーディエンスをテストしているので、両方のテストでコンバージョンが発生していても問題ありません。

<br> 

**あるテストグループは、テストセグメントの分割に認証済みプロファイルを使用しているとします。認証済みプロファイルは 4 つの    [Audience Manager UUID](../reference/ids-in-aam.md) に関連付けられています。訪問者が 4 つの UUID の中の 1 つのコンバージョン特性を示した場合、[!UICONTROL Audience Lab]はこれを 1 つのコンバージョンまたは 4 つのコンバージョンどちらのコンバージョンとしてカウントしますか？**

この場合、[!UICONTROL Audience Lab]は 1 回のコンバージョンとしてのみカウントします。

<br> 

**上記のケースで、訪問者は始めに認証済みプロファイルに関連付けられた 4 つの UUID の中の 1 つのコンバージョン特性を示し、次に他の 2 つの UUID のコンバージョン特性を示したとします。この場合、コンバージョンは 1 回または 3 回のどちらとしてカウントされますか？**

この場合、[!UICONTROL Audience Lab]は 3 回のコンバージョンとしてカウントします。認証済み特性を示した各デバイスについて 1 回となります。

<br> 

**ユーザーは [!UICONTROL Segment: Read-Only] アクセス権を持つ事ができますが、[!UICONTROL Audience Lab] テストセグメント作成権限も持つことはできますか？**

[!UICONTROL Audience Lab]での [!UICONTROL RBAC] 権限の使用方法に関する情報については、[セグメントのテストグループの作成](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)を参照してください。

**[!UICONTROL Audience Lab] を [!UICONTROL Profile Link Device Graph] および外部のデバイスグラフ（[Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/ja-JP/device-co-op/using/home.html)、Tapad デバイスグラフ、Liveramp デバイスグラフ）と共に使用することはできますか？**

[!UICONTROL Profile Link Device Graph]を使用する場合、[!UICONTROL Audience Lab]では今のところ、条件を満たすデバイスと関連付けられたデバイスによってのみセグメント母集団を分割できます。[!UICONTROL Audience Lab]で他のデバイスグラフもサポート対象とするよう作業を進めています。サポートの追加が完了し次第お知らせいたします。
