---
description: このドキュメントでは、Audience Manager での同意管理のしくみを説明します。
seo-description: このドキュメントでは、Audience Manager での同意管理のしくみを説明します。
seo-title: 同意管理
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: 同意管理
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 09ac547f22bc07e5b8609226ddd736cb79cbc700

---


# 同意管理

## 概要 {#overview}

特定のマーケティング活動に同意が必要な場合は、範囲と、今後もデータを使用し続けるために特定の同意を更新する必要があるかどうかをAudience Managerのお客様が決定する必要があります。

Audience Manager は、必要とされる同意をユーザーから取得するために必要なツールを提供します。これにより、複数のチャネルにわたってパーソナライズされたエクスペリエンスをユーザーに提供できます。

>[!IMPORTANT]
>
> このドキュメントの内容は法的な助言ではなく、その代用になるものでもありません。
>
> アドビはデータ処理者であるので、同意の取得に関する法的なアドバイスはできません。You may also want to consider working with a consent management solution provider, such as [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) or [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), to receive the best recommendations, and consult your company's legal department for advice concerning consent and practices when setting up your opt-in implementation.

## Experience Cloud オプトインサービス

[Experience Cloud オプトインサービス](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html)を使用すると、サイトを訪問したユーザーのデバイスまたはブラウザーに Cookie を設定できるかどうかを訪問者が決定するようにプロトコルを設定できます。

これは、[!DNL Experience Cloud ID (ECID) Service]の拡張機能です。この拡張機能を使用すると、ユーザーの同意を得る前に、訪問者の Web ページに Cookie を配置できる Experience Cloud ソリューションの種類と種類を制御できます。

また、[Experience Cloud オプトインサービス](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html)を使用すると、より大規模なデザインの一環として、お使いの同意管理プラットフォーム（CMP）および既存のシステムと統合するプロトコルを設定できます。

## オプトインの管理／同意の取得

Audience Managerのお客様は、広告やパーソナライゼーションなど、様々な使用例に対するユーザーの同意をAudience Managerの特徴として保存できます。 これらの特性を使用して作成したセグメントには、これらの各使用事例に対するそれぞれの同意を提供するユーザーのみが含まれます。 この方法によってデータ収集が妨げられることはなく、有効化するセグメントを送信する際に使用するデータに対してのみ影響があることに注意してください。ユーザーが同意を取り消す場合、以下に示すように、Audience Manager受信バッチプロセスまたはAudience Managerオプトアウトプロセスを使用して [](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 、これらの特性をユーザープロファイルから削除できます。

## オプトアウトの管理／同意の撤回

Opt-out can be managed for the Adobe Experience Cloud via the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page. 1クリック機能を使用すると、エンドユーザーはAdobe Experience cloud広告ソリューション（Audience Managerを含む）によるデータ収集を制御およびオプトアウトできます。 特に、プライバシーの選択肢ページの[ビジネス関連の顧客のセクション](https://www.adobe.com/privacy/opt-out.html#customeruse)を参照してください。サードパーティ Cookie をサポートしていないブラウザーについては、[宣言済み ID のターゲティング](../../features/declared-ids.md#declared-id-targeting)を参照してください。モバイルデバイスの場合、[宣言済み ID のオプトアウトの例](../../features/declared-ids.md#opt-out-examples)に従って、Audience Manager 識別子を取得し、Audience Manager オプトアウト API を呼び出してください。これに従えば、モバイル SDK でオプトアウト API を使用することで、これらのユーザーのすべてのデータ収集を止めることができます。[Android デバイス](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html)および [iOS デバイス](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)を参照してください。オプトアウトに関する他の詳細情報については、[データのプライバシーリクエストに関するドキュメント](../../overview/data-security-and-privacy/data-privacy-requests.md)。

## セカンドパーティデータプロバイダーの同意の管理

セカンドパーティのデータプロバイダーはデータ管理者でもあることが多く、セカンドパーティのデータパートナーとデータを共有するために必要な同意をデータ主体から取得するための独自のプロセスがあります。セカンドパーティのデータプロバイダーが所定の用途に必要な同意を取得したかどうかを確認するのは、Audience Manager 利用者としてのお客様の責務となります。同意の取得に関する詳細については、上述したとおりです。

## Audience Marketplaceサードパーティデータプロバイダーの同意の管理

Audience Marketplaceサードパーティのデータプロバイダーもデータコントローラーで、同意を得てアクセス/削除/修正リクエストを管理するためのプロセスを所有しています。 Adobe is proactively requesting that Audience Marketplace Third Party Data Providers update their company profile information within [Adobe Audience Finder](https://www.adobe-audience-finder.com/) with additional information on user data collection. 情報は、Audience Marketplaceサードパーティのデータプロバイダーから提供され、定期的に更新されます。 ただし、Audience Marketplaceサードパーティデータプロバイダーが、その顧客の使用事例に関して必要な同意を得たかどうかは、各Audience Managerのお客様次第です。 アドビは、特定の使用事例に関してAudience Marketplaceサードパーティデータプロバイダーが取得または報告した同意の範囲または有効性について一切表明しません。
