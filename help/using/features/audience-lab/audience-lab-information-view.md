---
description: このセクションには、テストグループとそれを分割したテストセグメントに関する一般情報、選択したコンバージョン特性、マッピングされた宛先が表示されます。また、テストグループの複製や削除をおこなえるコントロールも用意されています。
seo-description: このセクションには、テストグループとそれを分割したテストセグメントに関する一般情報、選択したコンバージョン特性、マッピングされた宛先が表示されます。また、テストグループの複製や削除をおこなえるコントロールも用意されています。
seo-title: テストグループの情報
solution: Audience Manager
title: テストグループの情報
topic-edit: DIL API
uuid: a49dfdb3-21e1-4c3d-b957-4d445f890124
feature: Audience Lab
exl-id: fb691c12-304d-4331-a395-a9005efa8bb0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 100%

---

# テストグループの情報 {#test-group-information}

このセクションには、テストグループとそれを分割したテストセグメントに関する一般情報、選択したコンバージョン特性、マッピングされた宛先が表示されます。また、テストグループの複製や削除をおこなえるコントロールも用意されています。

また、テストグループに使用したベースラインセグメントおよびテストセグメントの分割方法についての情報も確認できます。

**[!UICONTROL Test Segments]** のユーザーは、テストグループに使用したベースラインセグメントからランダムに取り込まれます。概要では、各テストセグメントに割り当てたユーザーの割合が示されます。

テストグループのレポートは、**[!UICONTROL Conversion Traits]**&#x200B;に基づいておこなわれます。[!UICONTROL Trait Builder]で特性の作成または編集をおこなう際に、ある特性をコンバージョンとして指定するには、**[](../../features/traits/create-onboarded-rule-based-traits.md)イベントタイプ**&#x200B;で&#x200B;**コンバージョン**&#x200B;を選択します。

**[!UICONTROL Destinations]**&#x200B;カードは折りたたみ可能です。個々の宛先を開くまたは閉じるには矢印を押します。マッピング先の宛先ごとに、テストセグメントに関する次の情報を取得できます。

* 各宛先に割り当てられたベースセグメントの合計母集団数から取得されたデバイス数
* マッピングキー
* マッピング値
* [!DNL URL] 宛先用 [!DNL URL] およびセキュア [!DNL URL]。

>[!NOTE]
>
>完了したテストグループは編集できません。一時停止、削除または複製のみ可能です。

![](assets/test-groups-information.PNG)
