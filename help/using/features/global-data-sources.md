---
description: グローバルデータソースを使用して、デバイス広告 ID をインポートします。
seo-description: グローバルデータソースを使用して、デバイス広告 ID をインポートします。
seo-title: グローバルデータソース
solution: Audience Manager
title: グローバルデータソース
uuid: null
translation-type: tm+mt
source-git-commit: 631111be50d8e1b2e8ec81a295ecda5ec3fd6fee

---


# グローバルデータソース {#global-data-sources}

## 概要

グローバルデータソースは、すべての Audience Manager のお客様がアクセスでき、[!DNL Apple]、[!DNL Samsung]、[!DNL Microsoft]、[!DNL Roku]、および[!DNL Android] などのデバイスメーカーによって生成されたデバイス広告 ID を含みます。これらの ID は、メーカーが広告目的での利用を許可したものです。Audience Manager のユーザーは、グローバルデータソースを使用して、デバイス ID を同期したり、それらのマッピングから識別されたデータをインポートまたはエクスポートしたりできます。

次の表に、Audience Manager でサポートされるグローバルデータソースを示します。

| データソース ID | 説明 |
|---|---|
| 20914 | **Google 広告 ID** - **GAID**[!DNL Android] は オペレーティングシステムを実行するデバイスを表します。 |
| 20915 | **広告用 Apple ID** - **IDFA**[!DNL iOS] は オペレーティングシステムを実行するデバイスを表します。 |
| 121963 | **広告用 ID** - **RIDA**[!DNL Roku] は Roku のストリーミングデバイスを表します。 |
| 389146 | **Microsoft 広告 ID** - **MAID**[!DNL Windows 10] は オペレーティングシステムを実行するデバイスを表します。 |
| 404660 | **DUID**[!DNL Samsung] は Samsung のスマートテレビを表します。 |
| 488258 | **Amazon Fire TV広告IDは、実**&#x200B;行中のデバイスを表します [!DNL Amazon Fire OS] |

## グローバルデータソースからのデータのインポート

デバイス ID は、[リアルタイムデータ転送](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md)と[バッチデータ転送](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)の両方を使用して、グローバルデータソースからインポートできます。

>[!IMPORTANT]
>
>グローバルデバイス ID を使用して Audience Manager にデータを送信する場合は、該当するデバイス ID に対応するデータソースを必ず使用してください。例：[!DNL Apple IDFA] のデータをインポートするには、データソース ID 20915 を使用します。

## 制限事項

[!DNL iOS]および [!DNL Android] オペレーティングシステムを実行するデバイスでは、ネイティブアプリケーションのみがデバイス広告 ID（[!UICONTROL DAID]）を取得して使用できます。モバイルブラウザーで実行されている Web アプリケーションは、デバイス広告 ID にアクセスできません。

## グローバルデバイス ID の検証

Audience Manager は、お客様によって読み込まれたデバイス広告 ID（[!UICONTROL DAID]）をその形式に基づいて検証し、デバイス製造元が説明する標準形式に一致するようにします。デバイス広告 ID とグローバルデータソースのマッピングおよびそれぞれの ID の適切な形式について詳しくは、[Audience Manager の ID のインデックス](../reference/ids-in-aam.md)を参照してください。デバイスタイプに基づいて、デバイス ID を正しい形式でインポートしていることを確認してください。Audience Manager では、適切な形式を満たさないデバイス ID は拒否され、ID が拒否されたことを示すエラーメッセージが返されます。

* バッチデータ転送のエラーメッセージについては、[オンボーディングステータスレポートの用語と定義](../reporting/onboarding-status-report.md#report-terms-conditions)を参照してください。
* リアルタイムデータ転送のエラーメッセージについては、[DCS エラーコード、メッセージ、例](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)を参照してください。

## デバイス ID の有効期限ポリシー

Audience Manager では、[AAM UUID](../faq/faq-privacy.md) と同様に、120 日間使用されなかったデバイス広告 ID は自動的に破棄されます。

## 新規グローバルデータソースのリクエスト

新規グローバルデータソースを Audience Manager に追加するには、アドビのコンサルタントチームまたはアドビのカスタマーケアにお問い合わせのうえ、必要なデータソースについて次の詳細情報を提供してください。

* リクエストするプラットフォームの名前（例：[!UICONTROL Apple IDFA]）
* プラットフォームを管理する会社または組織の名前（例：[!UICONTROL Apple Inc.]）
* Links to the technical specifications for the device advertising ID namespace (e.g., [AdSupport Documentation](https://developer.apple.com/documentation/adsupport)).