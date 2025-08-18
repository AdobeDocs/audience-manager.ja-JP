---
description: 認証要件、およびクラスレベルの DIL に関するドキュメントで使用されているテキスト書式について説明します。
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: クラスレベルの DIL API の概要
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 68%

---

# クラスレベルの DIL API の概要{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>2023 年 7 月以降、Adobeは [!DNL Data Integration Library (DIL)] および [!DNL DIL] 拡張機能の開発を廃止しました。
>
>既存のお客様は、[!DNL DIL] 実装を引き続き使用できます。 ただし、Adobeはこの点を超えて [!DNL DIL] 開発を行うことはありません。 お客様は、長期的なデータ収集戦略について [0}Experience Platform Web SDK} を評価することをお勧めします。](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)
>
>2023 年 7 月以降、新しいデータ収集統合機能の実装を検討しているお客様は、代わりに [0}Experience Platform Web SDK} を使用する必要があります。](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)

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
