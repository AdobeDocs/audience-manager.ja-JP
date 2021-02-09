---
description: Audience Managerのユーザー管理をAdobe Admin Consoleに移行中です。 この記事では、ユーザー移行の準備に必要な作業と、移行が完了した後の変更点について説明します。
keywords: rbac;RBAC;役割に基づく;ロールベース;ロールベースのアクセス制御
seo-description: Audience Managerのユーザー管理をAdobe Admin Consoleに移行中です。 この記事では、ユーザー移行の準備に必要な作業と、移行が完了した後の変更点について説明します。
seo-title: Audience ManagerユーザーのAdmin Consoleへの移行
solution: Audience Manager
title: Audience ManagerユーザーのAdmin Consoleへの移行
feature: Administration
translation-type: tm+mt
source-git-commit: 04504d4561414f9558a1f1f4db33cbcf535d54af
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 4%

---


# [!DNL Audience Manager] ユーザー移行  [!DNL Admin Console] {#user-migration}

## 概要 {#overview}

[!DNL Audience Manager] ユーザーアカウント管理は [Adobe Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html)に移行し、Adobeソリューション全体でのより合理化されたエクスペリエンスを提供します。

[!DNL Admin Console]を使用する利点は次のとおりです。

| メリット | 説明 |
|---|---|
| シングルサインオン ソリューション間 | [!DNL Audience Manager] ユーザーは、またはを使用して、他のす [!DNL Experience Cloud] べてのソリューションにサインイン [!DNL Adobe ID] でき [!DNL Enterprise ID]ます。このログインにより、[!DNL Experience Cloud]上の統合ソリューションとコアサービスにアクセスできます。 移行後、従来のログイン(`bank.demdex.com`)を使用してログインしようとするユーザーは、`experiencecloud.adobe.com`にリダイレクトされます。 |
| ユーザーとグループの管理 | 移行が完了すると、[!DNL Audience Manager]管理者は[[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/)内のユーザーとグループのみを管理します。 |
| 製品とサービスの管理 | [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/)から、管理者は次のことができます。 <ul><li>ユーザーの作成、更新および削除</li><li>ソリューションおよびサービスへのアクセスの許可</li><li>ユーザー権限の付与</li></ul> |

ユーザーの移行を容易にするために、[!DNL Audience Manager]管理者全員に、この記事で説明する手順に従って、できるだけ早く[Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)にユーザーアカウントを移行する開始を行うよう求めます。

## ユーザーが必要とする操作{#what-to-do-users}

Audience Managerユーザーとして必要なのは、[!DNL Audience Manager]管理者に問い合わせて、[!DNL Admin Console]で新しいユーザーアカウントを作成するように依頼することだけです。

## 管理者が必要とする操作{#what-to-do-admins}

Audience Manager管理者は、次の手順に従って[!DNL Admin Console]にユーザーを移行する必要があります。

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com)に移動し、Adobe IDまたはEnterprise IDを使用してログインします。 [!DNL Admin Console]へのアクセス権がない場合は、カスタマーケアまたはAdobeコンサルタントにお問い合わせください。
2. ユーザーアカウントの作成および管理方法の詳細な手順については、[!DNL Adobe Admin Console] [ヘルプガイド](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html)を参照してください。
3. 既存のすべてのAudience Managerユーザーに対して新しいユーザーアカウントを作成します。
4. 新しく作成したユーザーアカウントについてユーザーに通知します。 ユーザーは[!DNL Admin Console]に移行された後、従来のログインの使用を停止する必要があります。

## ユーザー移行に関する考慮事項{#considerations}

ユーザーと管理者は、Audience Managerユーザーの移行に関して、次の点に注意する必要があります。

* Admin Consoleで新しいユーザーアカウントを作成すると、既存のユーザーアカウントの既存の権限が自動的に引き継がれます。 管理者は、[!DNL Admin Console]に新しい権限を割り当てる必要はありません。
* 管理者は、レガシーユーザーアカウントを無効にする必要はありません。 古いユーザーアカウントは、移行されたアカウントに自動的に結合されます。
* ユーザー権限の更新は、引き続き[!DNL Audience Manager]から管理されます。 [!DNL Admin Console]は、ユーザーとグループの管理のみを対象としています。