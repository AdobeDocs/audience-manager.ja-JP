---
description: このドキュメントでは、Audience Manager での同意管理のしくみを説明します。
seo-description: このドキュメントでは、Audience Manager での同意管理のしくみを説明します。
seo-title: 同意管理
solution: Audience Manager
keywords: GDPR UI、GDPR API、CCPA、プライバシー、同意
title: 同意管理
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: データ・ガバナンスとプライバシー
exl-id: 9e545e8d-dbe4-4df9-8801-af3c2c73e406
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 98%

---

# 同意管理

## 概要 {#overview}

特定のマーケティング活動に同意が必要な場合は、範囲と、今後もデータを使用し続けるために特定の同意を更新する必要があるかどうかを Audience Manager のお客様が決定する必要があります。

Audience Manager は、必要とされる同意をユーザーから取得するために必要なツールを提供します。これにより、複数のチャネルをまたいでパーソナライズされたエクスペリエンスをユーザーに提供できます。

>[!IMPORTANT]
>
> このドキュメントの内容は法的な助言ではなく、その代用になるものでもありません。
>
> アドビはデータ処理者であるので、同意の取得に関する法的なアドバイスはできません。また、[Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/)、[TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) などの同意管理ソリューションプロバイダーとの連携を検討し、自社の法務部門に相談してオプトイン実装を設定する際の同意と慣行に関するアドバイスを受けることもできます。

## Experience Cloud オプトインサービス

[Experience Cloud オプトインサービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/implementation/opt-in-service/optin-overview.html)を使用すると、サイトを訪問したユーザーのデバイスまたはブラウザーに Cookie を設定できるかどうかを訪問者が決定するようにプロトコルを設定できます。

これは、[!DNL Experience Cloud ID (ECID) Service]の拡張機能です。この拡張機能を使用すると、ユーザーの同意を得る前に、訪問者の Web ページに Cookie を配置できる Experience Cloud ソリューションの種類と種類を制御できます。

また、[Experience Cloud オプトインサービス](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)を使用すると、より大規模なデザインの一環として、お使いの同意管理プラットフォーム（CMP）および既存のシステムと統合するプロトコルを設定できます。

## オプトインの管理／同意の取得

Audience Manager をご利用のお客様は、広告やパーソナライゼーションなど、様々な用途に使用されるユーザーの同意を、特性として Audience Manager に保存できます。これらの特性を使用して作成したセグメントには、各用途に対してそれぞれ同意したユーザーのみが含まれます。この方法によってデータ収集が妨げられることはなく、有効化するセグメントを送信する際に使用するデータに対してのみ影響があることに注意してください。ユーザーが同意を取り消す場合、以下に示すように、Audience Manager [受信バッチプロセス](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)または Audience Manager オプトアウトプロセスを使用して、これらの特性をユーザープロファイルから削除できます。

## オプトアウトの管理／同意の撤回

Adobe Experience Cloud のオプトアウトは、[プライバシーの選択肢](https://www.adobe.com/jp/privacy/opt-out.html#customeruse)ページで管理できます。お客様のエンドユーザーは 1 回のクリックで、Adobe Experience Cloud の広告ソリューション（Audience Manager を含む）によるデータ収集をオプトアウトできます。特に、プライバシーの選択肢ページの[ビジネス関連の顧客のセクション](https://www.adobe.com/privacy/opt-out.html#customeruse)を参照してください。サードパーティ Cookie をサポートしていないブラウザーについては、[宣言された ID のターゲティング](../../features/declared-ids.md#declared-id-targeting)を参照してください。モバイルデバイスの場合、[宣言された ID のオプトアウトの例](../../features/declared-ids.md#opt-out-examples)に従って、Audience Manager 識別子を取得し、Audience Manager オプトアウト API を呼び出してください。これに従えば、モバイル SDK でオプトアウト API を使用することで、これらのユーザーのすべてのデータ収集を止めることができます。[Android デバイス](https://docs.adobe.com/content/help/ja-JP/mobile-services/android/gdpr-privacy-android/privacy.html)および [iOS デバイス](https://docs.adobe.com/content/help/ja-JP/mobile-services/ios/privacy-gdpr-ios/privacy.html)を参照してください。オプトアウトに関する他の詳細情報については、[データのプライバシーリクエストに関するドキュメント](../../overview/data-security-and-privacy/data-privacy-requests.md)。

## セカンドパーティパートナーの同意の管理

セカンドパーティパートナーはデータ管理者でもあることが多く、セカンドパーティのデータパートナーとデータを共有するために必要な同意をデータ主体から取得するための独自のプロセスがあります。セカンドパーティパートナーが所定の用途に必要な同意を取得したかどうかを確認するのは、Audience Manager 利用者としてのお客様の責務となります。同意の取得に関する詳細については、上述したとおりです。

## Audience Marketplace サードパーティパートナーの同意の管理

Audience Marketplace サードパーティパートナーはデータ管理者でもあり、同意を取得し、アクセス／削除／修正の各要求を管理するための独自のプロセスがあります。アドビは Audience Marketplace サードパーティパートナーに対し、[Adobe Audience Finder](https://www.adobe-audience-finder.com/) 内の企業のプロファイル情報を更新し、ユーザーデータの収集に関する情報を追加するよう積極的に呼びかけています。情報は、Audience Marketplace サードパーティパートナーから提供され、定期的に更新されます。ただし、Audience Marketplace サードパーティパートナーが所定の用途に必要な合意を取得したかどうかを確認するのは、Audience Manager をご利用のそれぞれのお客様の責務となります。所定の用途のために Audience Marketplace サードパーティパートナーによって取得または報告された合意の範囲または妥当性について、アドビが意見を述べることはありません。
