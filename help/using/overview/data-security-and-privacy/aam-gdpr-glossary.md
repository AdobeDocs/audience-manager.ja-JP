---
description: この記事では、欧州一般データ保護規則（GDPR）で使用される概念と用語、および Adobe Audience Manager をデータ処理者として使用する場合に GDPR の様々な要件に対処する方法について説明します。
seo-description: この記事では、欧州一般データ保護規則（GDPR）で使用される概念と用語、および Adobe Audience Manager をデータ処理者として使用する場合に GDPR の様々な要件に対処する方法について説明します。
seo-title: GDPR の用語集
solution: Audience Manager
title: GDPR の用語集
uuid: e52cad27-6a44-45ee-8524-6080adb86cc8
feature: data governance & privacy
translation-type: ht
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: ht
source-wordcount: '724'
ht-degree: 100%

---


# GDPR の用語集 {#gdpr-glossary}

## 概要 {#overview}

この記事では、欧州一般データ保護規則（GDPR）で使用される概念と用語、および Adobe Audience Manager をデータ処理者として使用する場合に GDPR の様々な要件に対処する方法について説明します。

GDPR は 2018 年 5 月 25 日に施行された法律で、その第一の目的は、EU 内の個人（データ主体）が個人データをコントロールする権利を取り戻すこと、および EU 域内の規則を統合することで、国際的なビジネスのための規制環境を簡潔にすることです。GDPR への対応の一環として Adobe Audience Manager では、消費者であるデータ主体からのアクセス要求や削除要求をサポートするために、必要なサービスおよびプロセスの機能拡張をおこないました。

GDPR が Experience Cloud でどのように機能するかをよりよく理解するためには、[Experience Cloud の GDPR に関するFAQ](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md) を参照してください。

## GDPR の用語集 {#gdpr-glossay}

GDPR に関連して使用されるキーワードを確認しましょう。よく使用される用語の一部がここに挙げられています。

 

**データ管理者：** GDPR では「管理者」を「単独でまたは他と共同して、個人データの処理の目的および手段を決定する…法人…。」と定義しています。Audience Manager をご利用のお客様はデータ管理者となります。お客様は Audience Manager でのデータの管理方法を制御します。

 

**データ処理者：**「処理者」とは、「管理者のために個人データを処理する…法人…」です。Audience Manager のコンテキストでは、アドビは、サービスを運用する際、Audience Manager を介し、コントローラーに代わって処理する個人データの「データ処理者」として機能します。アドビは、データ管理者の指示に従って（お客様との契約書に記載されているとおり、または Audience Manager で行われたアクションを通じて）のみ、個人データを処理します。

 

**データ主体：**&#x200B;個人データが関連付けられる個人。Audience Manager では、データ主体とは Audience Manager をご利用のお客様に対する消費者またはエンドユーザーとなります。データ主体からアドビに対して直接要求が送られた場合、これらの要求はそれぞれ Audience Manager のお客様に転送されます。

 

**同意：**&#x200B;同意とは、「声明または明らかに積極的な行為により、その者が同人に関する個人データの処理への同意を表明することによって、データ主体の自由になされた特定の十分に情報を知らされたうえでの明確な意思表示」を意味します。同意を得ることはデータ管理者の責務となります。アドビが Audience Manager を通して同意を得ることはありません。

 

**アクセス：**&#x200B;データ主体はデータ管理者に対して、自身の個人データを処理しているかを確認できる権利があります。データ管理者がデータ主体の個人データを処理していた場合、データ管理者はデータ主体に対し、個人データへのアクセスを許可し、コピーを提供する義務があります。データ主体からのアクセス要求に関し、データ管理者はアドビのサポートを得ることができます。

 

**削除：** GDPR では「忘れられる権利」すなわち「消去権」が明文化されています。データ主体はデータ管理者に対して、自身の個人データの消去を要求できます。データ管理者はアドビなどの処理者と連携して、データ主体からの削除要求に対応します。

 

**修正：**&#x200B;データ主体はデータ管理者に対して、不正確な個人データの訂正を要求できます。データ管理者はアドビなどの処理者と連携して、データ主体からの修正要求に対応します。

 

**Audience Manager 識別子（ID）：** Adobe Audience Manager は様々な種類の ID を保存します。[Audience Manager 識別子](data-privacy-ids.md)ページには、これらの ID の概要、対応するデータソースおよび簡単な説明が記載されています。[Adobe Experience Platform プライバシーサービス](https://docs.adobe.com/content/help/ja-JP/experience-platform/privacy/home.translate.html)にリクエストを送信する場合は、これらの ID を参照して、データ主体の削除やアクセスのリクエストを行います。

 

**個人データ：** GDPR では、個人データの定義が拡大されています。GDPR では、お客様の使用目的によっては Audience Manager が扱うすべてのデータが個人データとして分類されます。

 

**禁止データ：** Audience Manager では、個人が直接特定できる情報をお客様が取り込むことを禁止しています。これには姓名、電子メール ID、CRM ID など、個人を直接特定するために使用できる情報が含まれます。Adobe Experience Cloud ソリューションでは、機密情報の取り扱いも禁止されています。これらの要件の詳細については、アドビと交わされた契約書を参照してください。このような種類のデータポイントを Audience Manager に取り込む必要がある場合は、事前にアドビのコンサルタントチームにお問い合わせのうえ、これらの ID のハッシュ化についてご相談ください。
