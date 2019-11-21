---
description: このドキュメントでは、Audience Managerでの同意管理のしくみを説明します。
seo-description: このドキュメントでは、Audience Managerでの同意管理のしくみを説明します。
seo-title: 同意管理
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: 同意管理
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: fbe4e8c912093c495f27ca887a44ac31d394811a

---


# 同意管理

## 概要 {#overview}

特定のマーケティング活動に同意が必要な場合は、消費者の同意がアクティブ（事前にチェックされたボックスがない、同意としての無音など）で、バンドルが解除され、サービスの提供がData Subjectの同意に基づいて条件付けられない場合があります。 データを使用し続けるにあたって、特定の同意を更新する必要が生じる可能性もあります。

Audience Managerは、必要な同意をユーザーから取得するために必要なツールを提供します。これにより、複数のチャネルにわたってパーソナライズされたエクスペリエンスをユーザーに提供できます。

>[!IMPORTANT]
>
> 本書の内容は法律上の助言ではなく、法律上の助言の代わりに使用するものではありません。
>
> アドビはデータ処理者であるので、同意の取得に関する法的なアドバイスはできません。ベストレコメンデーションを受け取るには、 [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) 、 [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/)などの同意管理ソリューションプロバイダと協力し、オプトイン実装を設定する際の同意と慣行に関するアドバイスを会社の法務部門に依頼することをお勧めします。

## Experience cloudオプトインサービス

[Experience cloudオプトインサービスを使用すると](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) 、訪問者がサイトにアクセスする際にユーザーのデバイスまたはブラウザーにcookieを設定できるかどうかを判断するためのプロトコルを設定できます。

これは、の拡張機能です。この拡張機能を使 [!DNL Experience Cloud ID (ECID) Service]用すると、ユーザーの同意を得る前に、訪問者のWebページにcookieを配置できるExperience cloudソリューションの種類と種類を制御できます。

また、 [Experience cloudオプトインサービスを使用すると](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) 、より大規模なデザインの一環として、お使いの同意管理プラットフォーム(CMP)および既存のシステムと統合するプロトコルを設定できます。

## オプトインの管理／同意の取得

Audience Manager をご利用のお客様は、広告やパーソナライゼーションなど、様々な用途に使用されるユーザーの同意を、特性として Audience Manager に保存できます。これらの特性を使用してセグメントを作成すれば、各用途に対してそれぞれ同意したユーザーのみが含まれるセグメントとすることができます。この方法によってデータ収集が妨げられることはなく、有効化するセグメントを送信する際に使用するデータに対してのみ影響があることに注意してください。ユーザーが同意を撤回した場合、Audience Manager の[インバウンドのバッチ処理](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)または以下に詳述される Audience Manager のオプトアウト処理を使用して、ユーザープロファイルからこれらの特性を削除できます。

## オプトアウトの管理／同意の撤回

Adobe Experience Cloud のオプトアウトは、[プライバシーの選択肢](https://www.adobe.com/privacy/opt-out.html#customeruse)ページで管理できます。お客様のエンドユーザーは 1 回のクリックで、Adobe Experience Cloud の広告ソリューション（Audience Manager を含む）によるデータ収集をオプトアウトできます。特に、プライバシーの選択肢ページの[ビジネス関連の顧客のセクション](https://www.adobe.com/privacy/opt-out.html#customeruse)を参照してください。サードパーティ Cookie をサポートしていないブラウザーについては、[宣言済み ID のターゲティング](../../features/declared-ids.md#declared-id-targeting)を参照してください。モバイルデバイスの場合、[宣言済み ID のオプトアウトの例](../../features/declared-ids.md#opt-out-examples)に従って、Audience Manager 識別子を取得し、Audience Manager オプトアウト API を呼び出してください。これに従えば、モバイル SDK でオプトアウト API を使用することで、これらのユーザーのすべてのデータ収集を止めることができます。[Android デバイス](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html)および [iOS デバイス](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)を参照してください。オプトアウトに関する他の詳細情報については、 データプライ [バシーリクエストのドキュメント](../../overview/data-security-and-privacy/data-privacy-requests.md)。

## サードパーティデータプロバイダの同意の管理

セカンドパーティのデータプロバイダーはデータ管理者でもあることが多く、セカンドパーティのデータパートナーとデータを共有するために必要な同意をデータ主体から取得するための独自のプロセスがあります。サードパーティのデータプロバイダーがユースケースに必要な同意を得たかどうかは、Audience Managerのお客様が決定する必要があります。 同意の取得に関する詳細については、上述したとおりです。

## サードパーティデータプロバイダの同意の管理

サードパーティのデータプロバイダーもデータコントローラーで、同意を得てアクセス/削除/修正リクエストを管理するプロセスを所有しています。 アドビはデータプロバイダーに対し、[Adobe Audience Finder](https://www.adobe-audience-finder.com/) 内の企業のプロファイル情報を更新し、ユーザーデータの収集に関する情報を追加するよう積極的に呼びかけています。情報はデータプロバイダーから提供され、定期的に更新されます。 ただし、サードパーティのデータプロバイダーが所定の用途に必要な合意を取得したかどうかを確認するのは、Audience Manager をご利用のそれぞれのお客様の責務となります。所定の用途のためにサードパーティのデータプロバイダーによって取得または報告された合意の範囲または妥当性について、アドビが意見を述べることはありません。
