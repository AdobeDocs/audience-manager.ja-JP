---
description: このドキュメントでは、Audience Manager での同意管理のしくみを説明します。
seo-description: このドキュメントでは、Audience Manager での同意管理のしくみを説明します。
seo-title: 同意管理
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: 同意管理
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: ht
source-git-commit: fbe4e8c912093c495f27ca887a44ac31d394811a

---


# 同意管理

## 概要 {#overview}

特定のマーケティング活動において消費者の同意が必要となった場合、同意は主体的に（事前にチェックが付けられたチェックボックスや暗黙の同意は認められません）、独立しておこなわれる必要があります。また、データ主体の同意を条件にサービスを提供することは禁じられています。データを使用し続けるにあたって、特定の同意を更新する必要が生じる可能性もあります。

Audience Manager は、必要とされる同意をユーザーから取得するために必要なツールを提供します。これにより、複数のチャネルにわたってパーソナライズされたエクスペリエンスをユーザーに提供できます。

>[!IMPORTANT]
>
> このドキュメントの内容は法的な助言ではなく、その代用になるものでもありません。
>
> アドビはデータ処理者であるので、同意の取得に関する法的なアドバイスはできません。最良の助言を受けるには [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) や [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) などの同意管理ソリューションプロバイダーと協力し、オプトイン実装を設定する際の同意と慣行に関するアドバイスを会社の法務部門に依頼することをお勧めします。

## Experience Cloud オプトインサービス

[Experience Cloud オプトインサービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/implementation-guides/opt-in-service/optin-overview.html)を使用すると、サイトを訪問したユーザーのデバイスまたはブラウザーに Cookie を設定できるかどうかを訪問者が決定するようにプロトコルを設定できます。

これは、[!DNL Experience Cloud ID (ECID) Service]の拡張機能です。この拡張機能を使用すると、ユーザーの同意を得る前に、訪問者の Web ページに Cookie を配置できる Experience Cloud ソリューションの種類と種類を制御できます。

また、[Experience Cloud オプトインサービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/implementation-guides/opt-in-service/optin-overview.html)を使用すると、より大規模なデザインの一環として、お使いの同意管理プラットフォーム（CMP）および既存のシステムと統合するプロトコルを設定できます。

## オプトインの管理／同意の取得

Audience Manager をご利用のお客様は、広告やパーソナライゼーションなど、様々な用途に使用されるユーザーの同意を、特性として Audience Manager に保存できます。これらの特性を使用してセグメントを作成すれば、各用途に対してそれぞれ同意したユーザーのみが含まれるセグメントとすることができます。この方法によってデータ収集が妨げられることはなく、有効化するセグメントを送信する際に使用するデータに対してのみ影響があることに注意してください。ユーザーが同意を撤回した場合、Audience Manager の[インバウンドのバッチ処理](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)または以下に詳述される Audience Manager のオプトアウト処理を使用して、ユーザープロファイルからこれらの特性を削除できます。

## オプトアウトの管理／同意の撤回

Adobe Experience Cloud のオプトアウトは、[プライバシーの選択肢](https://www.adobe.com/jp/privacy/opt-out.html#customeruse)ページで管理できます。お客様のエンドユーザーは 1 回のクリックで、Adobe Experience Cloud の広告ソリューション（Audience Manager を含む）によるデータ収集をオプトアウトできます。特に、プライバシーの選択肢ページの[ビジネス関連の顧客のセクション](https://www.adobe.com/jp/privacy/opt-out.html#customeruse)を参照してください。サードパーティ Cookie をサポートしていないブラウザーについては、[宣言済み ID のターゲティング](../../features/declared-ids.md#declared-id-targeting)を参照してください。モバイルデバイスの場合、[宣言済み ID のオプトアウトの例](../../features/declared-ids.md#opt-out-examples)に従って、Audience Manager 識別子を取得し、Audience Manager オプトアウト API を呼び出してください。これに従えば、モバイル SDK でオプトアウト API を使用することで、これらのユーザーのすべてのデータ収集を止めることができます。[Android デバイス](https://marketing.adobe.com/resources/help/ja_JP/mobile/android/privacy.html)および [iOS デバイス](https://marketing.adobe.com/resources/help/ja_JP/mobile/ios/privacy.html)を参照してください。オプトアウトに関する他の詳細情報については、[データのプライバシーリクエストに関するドキュメント](../../overview/data-security-and-privacy/data-privacy-requests.md)。

## セカンドパーティデータプロバイダーの同意の管理

セカンドパーティのデータプロバイダーはデータ管理者でもあることが多く、セカンドパーティのデータパートナーとデータを共有するために必要な同意をデータ主体から取得するための独自のプロセスがあります。セカンドパーティのデータプロバイダーが所定の用途に必要な同意を取得したかどうかを確認するのは、Audience Manager 利用者としてのお客様の責務となります。同意の取得に関する詳細については、上述したとおりです。

## サードパーティデータプロバイダーの同意の管理

サードパーティデータプロバイダーはデータ管理者でもあり、同意を取得し、アクセス／削除／修正の各要求を管理するための独自のプロセスがあります。アドビはデータプロバイダーに対し、[Adobe Audience Finder](https://www.adobe-audience-finder.com/) 内の企業のプロファイル情報を更新し、ユーザーデータの収集に関する情報を追加するよう積極的に呼びかけています。情報はデータプロバイダーから提供され、定期的に更新されます。ただし、サードパーティのデータプロバイダーが所定の用途に必要な合意を取得したかどうかを確認するのは、Audience Manager をご利用のそれぞれのお客様の責務となります。所定の用途のためにサードパーティのデータプロバイダーによって取得または報告された合意の範囲または妥当性について、アドビが意見を述べることはありません。
