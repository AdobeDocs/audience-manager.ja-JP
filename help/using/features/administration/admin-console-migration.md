---
description: Audience Manager のユーザー管理は Adobe Admin Console に移行されます。この記事では、ユーザー移行の準備に必要な作業と移行完了後の変更点について説明します。
keywords: rbac;RBAC;役割に基づく;ロールベース;ロールベースのアクセス制御
seo-description: Audience Manager のユーザー管理は Adobe Admin Console に移行されます。この記事では、ユーザー移行の準備に必要な作業と移行完了後の変更点について説明します。
seo-title: Admin Console への Audience Manager ユーザーの移行
solution: Audience Manager
title: Admin Console への Audience Manager ユーザーの移行
feature: 管理
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 100%

---

# [!DNL Audience Manager] ユーザーの [!DNL Admin Console] への移行 {#user-migration}

## 概要 {#overview}

[!DNL Audience Manager] ユーザーアカウント管理は [Adobe Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) に移行され、アドビソリューション全体を通してエクスペリエンスが効率化されます。

 [!DNL Admin Console] を使用するメリットは次のとおりです。

| メリット | 説明 |
|---|---|
| シングルサインオンソリューション間 | [!DNL Audience Manager] ユーザーは、[!DNL Adobe ID] または [!DNL Enterprise ID] を使用して、[!DNL Experience Cloud] などのすべてのソリューションにログインできます。このログインにより、[!DNL Experience Cloud] 全体で統合ソリューションとコアサービスにアクセスできます。移行後、従来のログイン（`bank.demdex.com` ）でログインしようとするユーザーは、`experiencecloud.adobe.com` にリダイレクトされます。 |
| ユーザーとグループの管理 | 移行が完了すると、[!DNL Audience Manager] 管理者は [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/) でのみユーザーとグループを管理するようになります。 |
| 製品とサービスの管理 | [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/) から、管理者は以下をおこなえます。 <ul><li>ユーザーの作成、更新、削除</li><li>ソリューションやサービスへのアクセスの許可</li></ul> |

ユーザーの移行を容易にするために、[!DNL Audience Manager] 管理者全員に、この記事で説明する手順に従って、できるだけ早く [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) へのユーザーアカウントの移行を開始するよう求めています。

## ユーザーに必要な作業 {#what-to-do-users}

Audience Manager ユーザーに必要なのは、[!DNL Audience Manager] 管理者に連絡して、[!DNL Admin Console] で新しいユーザーアカウントを作成するように依頼することだけです。

## 管理者に必要な作業 {#what-to-do-admins}

Audience Manager 管理者は、次の手順に従ってユーザーを [!DNL Admin Console] に移行する必要があります。

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com) に移動し、Adobe ID または Enterprise ID を使用してログインします。[!DNL Admin Console] にアクセスできない場合は、カスタマーケアまたはアドビコンサルタントにお問い合わせください。
2. ユーザーアカウントの作成および管理方法の詳細な手順については、[!DNL Adobe Admin Console] [ヘルプガイド](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/users.ug.html)を参照してください。
3. 既存のすべての Audience Manager ユーザーに対して新しいユーザーアカウントを作成します。
4. 新しく作成したユーザーアカウントについてユーザーに通知します。[!DNL Admin Console] に移行された後、ユーザーは従来のログインの使用をやめる必要があります。

## ユーザー移行に関する考慮事項 {#considerations}

ユーザーも管理者も、Audience Manager ユーザーの移行に関して次の点に留意する必要があります。

* 新しいユーザーアカウントが Admin Console で作成されても、従来のユーザーアカウントが持つ既存の権限が引き続き適用されます。
* ユーザー権限の更新は、引き続き [!DNL Audience Manager] から管理されます。[!DNL Admin Console] では、ユーザーとグループの管理のみを対象としています。
* 管理者は、従来のユーザーアカウントを無効にする必要はありません。古いユーザーアカウントは、移行後のアカウントに自動的に結合されます。
