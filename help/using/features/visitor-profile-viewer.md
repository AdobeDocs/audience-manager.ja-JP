---
description: 訪問者プロファイルビューアでは、特性やセグメントなど、現在のブラウザーに対するユーザープロファイルの現在の状態を表示できます。各特性について、SID、名前、訪問者の特性がどのように適合したかについての詳細（ファーストパーティまたはサードパーティ）、適合した日付、適合する頻度を表示できます。セグメントについては、各セグメントの SID、名前、セグメントメンバーシップの日付を確認できます。また、別の Audience Manager プロファイル ID（UUID）の訪問者プロファイルも確認できます。訪問者プロファイルビューアはトラブルシューティングに役立ちます。
keywords: 場所;場所パラメーター
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: 訪問者プロファイルビューア
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
TQID: https://experienceleague.adobe.com/e-qPcNaUpT-inBkx30AqUa-KkjjVJRyce86O-HQNitE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 250
ht-degree: 100%

---

# 訪問者プロファイルビューア {#visitor-profile-viewer}

[!UICONTROL Visitor Profile Viewer]を使用すると、現在のブラウザーのユーザープロファイルについて、特性やセグメントを含む現在の状態を表示できます。特性については、各特性の [!UICONTROL SID]、名前、訪問者の特性がどのように認識されたか（ファーストパーティまたはサードパーティ）についての詳細、認識の日付、認識頻度を確認できます。セグメントについては、各セグメントの [!UICONTROL SID]、名前、セグメントメンバーシップの日付を確認できます。また、別の Audience Manager プロファイル ID（[!UICONTROL UUID]）の訪問者プロファイルも確認できます。[!UICONTROL Visitor Profile Viewer]はトラブルシューティングに便利です。

>[!NOTE]
>
>* アクセスには[!UICONTROL Administrator]権限が必要です。
>* 適合したセグメントとオンボードの特性の情報がユーザーインターフェイスに表示されるまで、24 時間の遅れがあります。

<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. **[!UICONTROL Tools]**／**[!UICONTROL Visitor Profile Viewer]** をクリックします。

1. *（オプション）*&#x200B;特性名をクリックすると、[!UICONTROL Trait Builder]にその特性が表示されます。

   詳しくは、[特性](../features/traits/trait-details-page.md)を参照してください。

1. *（オプション）*&#x200B;セグメント名をクリックすると、[!UICONTROL Segment Builder]にそのセグメントが表示されます。

   詳しくは、[セグメント](../features/segments/segments-purpose.md)を参照してください。

1. *（オプション）*「**[!UICONTROL UUID]**」ボックスで、別の Audience Manager プロファイル ID を指定してから、「**[!UICONTROL Refresh]**」をクリックして、そのユーザーの特性とセグメントを表示します。
