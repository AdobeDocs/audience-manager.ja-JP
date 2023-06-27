---
description: 認証要件、およびクラスレベルの DIL に関するドキュメントで使用されているテキスト書式について説明します。
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: クラスレベルの DIL API の概要
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 71%

---

# クラスレベルの DIL API の概要{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>2023 年 7 月より、Adobeは、 [!DNL Data Integration Library (DIL)] そして [!DNL DIL] 拡張子。
><br><br>
>既存のお客様は、引き続き [!DNL DIL] 実装。 しかし、Adobeは発展しない [!DNL DIL] この点を越えて お客様は、 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) 長期のデータ収集戦略に対応するために使用されます。
><br><br>
>2023 年 7 月以降に新しいデータ収集統合を実装する場合は、 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) 代わりに、

クラスレベルの DIL API を使用すると、Audience Manager オブジェクトをプログラムで作成し操作することができます。クラスレベルの API は他のインスタンスレベルの関数と連携して、値を設定したりデータを返したりします。

## クラスレベルの DIL API の概要 {#get-started}

認証要件、およびクラスレベルの [!UICONTROL DIL] に関するドキュメントで使用されているテキスト書式について説明します。

<!-- 

c_class_start.xml

 -->

クラスレベルの [!UICONTROL DIL] API を使用する場合：

* アクセスにはパートナー名およびコンテナ名前空間 ID（NSID）が必要になります。担当の Audience Manager アカウントマネージャーにご連絡のうえ、これらの情報を入手してください。
* サンプルとして提示された API ドキュメント内のすべての&#x200B;*斜体*&#x200B;テキストを、使用するメソッドで必要となる値、ID、または他の変数に置き換えてください。
* [!UICONTROL DIL] はエンコードされたデータを宛先の Cookie に書き込みます。例えば、空白は `%20`、セミコロンは `%3B` にエンコードされます。
