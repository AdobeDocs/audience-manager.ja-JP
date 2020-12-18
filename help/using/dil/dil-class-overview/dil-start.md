---
description: 認証要件、およびクラスレベルの DIL に関するドキュメントで使用されているテキスト書式について説明します。
seo-description: 認証要件、およびクラスレベルの DIL に関するドキュメントで使用されているテキスト書式について説明します。
seo-title: クラスレベルの DIL API の概要
solution: Audience Manager
title: クラスレベルの DIL API の概要
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
translation-type: ht
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: ht
source-wordcount: '156'
ht-degree: 100%

---


# クラスレベルの DIL API の概要 {#getting-started-with-class-level-dil-apis}

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

