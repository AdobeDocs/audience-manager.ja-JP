---
description: 認証要件、およびクラスレベルの DIL に関するドキュメントで使用されているテキスト書式について説明します。
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: クラスレベルの DIL API の概要
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
TQID: https://experienceleague.adobe.com/RlkKHc2IuInFWfWOnTKS94XhBmbDbQYjtQZI40DsU-8
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: b82b475d-1e7d-46c6-9172-1f9c73004b11id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 203
ht-degree: 68%

---

# クラスレベルの DIL API の概要{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>2023年7月以降、Adobeは[!DNL Data Integration Library (DIL)]と[!DNL DIL]拡張機能の開発を中止しました。
>
>既存のお客様は、引き続き[!DNL DIL]実装を使用できます。 ただし、Adobeはこの時点を超えて[!DNL DIL]を開発しません。 お客様は、長期的なデータ収集戦略について[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を評価することをお勧めします。
>
>2023年7月以降に新しいデータ収集インテグレーションを導入するお客様は、代わりに[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を使用してください。

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
