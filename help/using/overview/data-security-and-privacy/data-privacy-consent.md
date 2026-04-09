---
description: このドキュメントでは、Audience Manager での同意管理のしくみを説明します。
seo-description: This document explains how consent management works in Audience Manager.
seo-title: Consent Management
solution: Audience Manager
keywords: GDPR UI、GDPR API、CCPA、プライバシー、同意
title: 同意管理
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: 9e545e8d-dbe4-4df9-8801-af3c2c73e406
TQID: https://experienceleague.adobe.com/ky1cNyZ507tDn2FFS6umoWsT-zaZ05wQwvK8xvNc7HU
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 685
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

[Experience Cloud オプトインサービス](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ja)を使用すると、サイトを訪問したユーザーのデバイスまたはブラウザーに Cookie を設定できるかどうかを訪問者が決定するようにプロトコルを設定できます。

これは、[!DNL Experience Cloud ID (ECID) Service]の拡張機能です。この拡張機能を使用すると、ユーザーの同意を得る前に、訪問者の Web ページに Cookie を配置できる Experience Cloud ソリューションの種類と種類を制御できます。

また、[Experience Cloud オプトインサービス](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ja)を使用すると、より大規模なデザインの一環として、お使いの同意管理プラットフォーム（CMP）および既存のシステムと統合するプロトコルを設定できます。

## オプトインの管理／同意の取得

Audience Manager をご利用のお客様は、広告やパーソナライゼーションなど、様々な用途に使用されるユーザーの同意を、特性として Audience Manager に保存できます。これらの特性を使用して作成したセグメントには、各用途に対してそれぞれ同意したユーザーのみが含まれます。この方法によってデータ収集が妨げられることはなく、有効化するセグメントを送信する際に使用するデータに対してのみ影響があることに注意してください。ユーザーが同意を取り消す場合、以下に示すように、Audience Manager [受信バッチプロセス](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)または Audience Manager オプトアウトプロセスを使用して、これらの特性をユーザープロファイルから削除できます。

## オプトアウトの管理／同意の撤回

Adobe Experience Cloud のオプトアウトは、[プライバシーの選択肢](https://www.adobe.com/jp/privacy/opt-out.html#customeruse)ページで管理できます。お客様のエンドユーザーは 1 回のクリックで、Adobe Experience Cloud の広告ソリューション（Audience Manager を含む）によるデータ収集をオプトアウトできます。特に、プライバシーの選択肢ページの[ビジネス関連の顧客のセクション](https://www.adobe.com/jp/privacy/opt-out.html#customeruse)を参照してください。サードパーティ Cookie をサポートしていないブラウザーについては、[宣言された ID のターゲティング](../../features/declared-ids.md#declared-id-targeting)を参照してください。モバイルデバイスの場合、[宣言された ID のオプトアウトの例](../../features/declared-ids.md#opt-out-examples)に従って、Audience Manager 識別子を取得し、Audience Manager オプトアウト API を呼び出してください。これに従えば、モバイル SDK でオプトアウト API を使用することで、これらのユーザーのすべてのデータ収集を止めることができます。[Android デバイス](https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html?lang=ja)および [iOS デバイス](https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html?lang=ja)を参照してください。オプトアウトの詳細については、[ データプライバシー要求ドキュメント ](../../overview/data-security-and-privacy/data-privacy-requests.md)を参照してください。

## セカンドパーティパートナーの同意の管理

セカンドパーティパートナーはデータ管理者でもあることが多く、セカンドパーティのデータパートナーとデータを共有するために必要な同意をデータ主体から取得するための独自のプロセスがあります。セカンドパーティパートナーが所定の用途に必要な同意を取得したかどうかを確認するのは、Audience Manager 利用者としてのお客様の責務となります。同意の取得に関する詳細については、上述したとおりです。

## Audience Marketplace サードパーティパートナーの同意の管理

Audience Marketplace サードパーティパートナーはデータ管理者でもあり、同意を取得し、アクセス／削除／修正の各要求を管理するための独自のプロセスがあります。アドビは Audience Marketplace サードパーティパートナーに対し、[Adobe Audience Finder](https://www.adobe-audience-finder.com/) 内の企業のプロファイル情報を更新し、ユーザーデータの収集に関する情報を追加するよう積極的に呼びかけています。情報は、Audience Marketplace サードパーティパートナーから提供され、定期的に更新されます。ただし、Audience Marketplace サードパーティパートナーが所定の用途に必要な合意を取得したかどうかを確認するのは、Audience Manager をご利用のそれぞれのお客様の責務となります。所定の用途のために Audience Marketplace サードパーティパートナーによって取得または報告された合意の範囲または妥当性について、アドビが意見を述べることはありません。
