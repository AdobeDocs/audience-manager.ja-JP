---
description: このドキュメントでは、Audience Manager のデータプライバシー規制への準拠に関する技術について説明します。
seo-description: このドキュメントでは、Audience Manager のデータプライバシー規制への準拠に関する技術について説明します。
seo-title: データのプライバシーリクエスト
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: データのプライバシーリクエスト
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 63%

---


# データのプライバシーリクエスト {#data-privacy-requests}

## 概要 {#overview}

This document provides an overview of managing individual data privacy and opt-out requests that you can send to [!DNL Audience Manager] through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send consumer data privacy requests made under [!DNL GDPR] and [!DNL CCPA].

この記事を読む前に、[GDPR の用語集](../data-security-and-privacy/aam-gdpr-glossary.md)と [CCPA の用語集](aam-ccpa-glossary.md)を参照して、ここで使用する用語の理解を深めることをお勧めします。

You can submit individual requests to access and delete consumer data from [!DNL Audience Manager], in two ways:

* [プライバシーサービスの UI](https://privacyui.cloud.adobe.io/) を使用する。[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)のドキュメントを参照してください。
* **[!DNL Privacy Service API]**&#x200B;を使用する。See the documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) and the [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending individual data privacy requests, you can submit any [!DNL Audience Manager] identifiers (IDs), as described in the **[Audience Manager Identifiers](data-privacy-ids.md)**section, along with their respective namespace IDs (data source IDs).

[プライバシーサービス](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)は、データアクセスおよびデータ削除の 2 種類のリクエストをサポートします。

## データアクセスリクエスト {#access-data}

個々のデータアクセスリクエストは、[プライバシ－サービスの UI](https://privacyui.cloud.adobe.io/)（ドキュメントは[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)）または [!DNL Privacy Service API]（ドキュメントは[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)、[!DNL API]レフェレンスは [こちら](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)）を呼び出して送信できます。

[プライバシーサービスの UI ](https://privacyui.cloud.adobe.io/)では、[!UICONTROL Request Builder] を使用するか、[!DNL JSON] ファイルをアップロードすることで、新しいジョブリクエストを作成できます。

有効な [!DNL JSON] ファイルがどのようなものであるかを確認するには、[JSON のサンプルをダウンロード](../data-security-and-privacy/assets/access_request.json)できます。

アドビは、お客様のデータのプライバシー要求を法律で定められた期間内に処理する取り組みを理解しています。

## データ削除リクエスト {#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the [!DNL Privacy Service API] (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

[プライバシーサービスの UI ](https://privacyui.cloud.adobe.io/)では、[!UICONTROL Request Builder] を使用するか、[!DNL JSON] ファイルをアップロードすることで、新しいジョブリクエストを作成できます。

有効な [!DNL JSON] ファイルがどのようなものであるかを確認するには、[JSON のサンプルをダウンロード](../data-security-and-privacy/assets/access_request.json)できます。

アドビは、30 日以内にお客様のデータプライバシーに関するお客様の要請に応える取り組みを理解しています。For that reason, [!DNL Adobe] is committed to processing your data deletion request as soon as possible.

In response to your consumer data deletion requests, [!DNL Audience Manager] deletes traits and segments associated with the [!DNL Audience Manager] identifier included in the request. Additionally, the respective [!DNL Audience Manager] identifiers for the individual opted out of further data collection by [!DNL Audience Manager] and the respective ID mappings will be removed.

複数のデバイスにまたがる [!DNL CRM] ID や顧客の ID などの宣言済み ID がデータプライバシー要求で送信された場合、 は関連付けられたすべてのデバイス（1 つの宣言済み ID につき最大 100 個のデバイス）に対して必要な削除をおこないます。[!DNL cookie][!DNL Audience Manager]

[!DNL Audience Manager]特定のデータの削除を要求しているデータ主体のセグメント解除の情報を送信することで、 からアクティベーションパートナーに対して削除要求が通知されます。ただし、一部のアクティベーションパートナーは、

1. Cannot support unsegment (or remove segment) requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] with a frequency of less than 30 days. In those cases, [!DNL Audience Manager] customers are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

In those cases, you are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

 のアクティベーションパートナーの中でどれがセグメント解除をサポートしているかを確認するには、[パートナーに関する Excel シート](assets/AAM-Partners-October2019.xlsx)をダウンロードしてください。[!DNL Audience Manager]

## オプトアウト要求 {#opt-out-requests}

[!DNL Audience Manager] オプトアウト管理に関する業界全体の標準をサポートします。 Read on for complete information on the types of opt-out supported by [!DNL Audience Manager].

データアクセスおよび削除の要求は[プライバシーサービス](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)で処理されますが、現在、オプトアウト要求は [!DNL DCS API] を通じてサポートされています。Read on to learn what the opt-out [!DNL API] calls should look like.

### グローバルオプトアウト要求

The global opt-out represents an opt-out across [!DNL Audience Manager] and other [!DNL Adobe Experience Cloud] solutions for all brands. 次の表は、グローバルオプトアウトに使用する手法の一覧です。

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> オプトアウトの対象 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p><a href="https://www.adobe.com/jp/privacy/opt-out.html#customeruse" format="http" scope="external">プライバシーの設定ページ</a>には、エンドユーザーが Adobe Experience Cloud 広告ソリューション（Audience Manager など）によるデータ収集の制御やオプトアウトをおこなうための 1 クリック機能があります。特に、プライバシーの選択肢ページの<a href="https://www.adobe.com/jp/privacy/opt-out.html#customeruse" format="http" scope="external">ビジネス関連の顧客のセクション</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audience Manager に対する直接 API 呼び出し </p> </td> 
   <td colname="col2"> <p>すべての Audience Manager ブランドによるデータ収集からオプトアウトするには、以下のように DCS API を呼び出し、<a href="../../reference/ids-in-aam.md">Audience Manager ユーザー ID </a>を含めます。 </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>その結果、送信された Audience Manager ユーザー ID に対して <code>demdex=NOTARGET</code> および <code>dextp=NOTARGET</code> Cookie が設定されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>モバイルデバイス </p> </td> 
   <td colname="col2"> <p>以下のデバイスに対するオプトアウト設定とプライバシー設定を確認します。 </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/ja-JP/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android デバイス </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/ja-JP/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS デバイス </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

エンドユーザーは、アドビの業界標準パートナーの Web サイトを訪問してグローバルデータ収集からオプトアウトすることもできます。

* [Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#! /)
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#! /)。

上記のオプトアウトリクエストをおこなうと、次の処理がおこなわれます。

* [!DNL Audience Manager]ユーザーがブラウザーの Cookie をクリアしない限り、 は、すべてのデータ収集、セグメント化またはアクティブ化を停止します。
* 120 日後にユーザープロファイルから履歴データが削除されます。

### 宣言された ID 呼び出しを使用するパートナーレベルのオプトアウト

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. You can send partner-level opt-out requests for cross-device IDs, including [!DNL CRM] IDs and hashed email addresses.

宣言された ID 呼び出しを使用するパートナーレベルのオプトアウトの後：

* [CRM ID](../../reference/ids-in-aam.md) がデータ収集からオプトアウトされます;
* [CRM ID](../../reference/ids-in-aam.md) にリンクされている最後のデバイス ID（[Audience Manager の一意のユーザー ID](../../reference/ids-in-aam.md)）は、データ収集からオプトアウトされます。
* [!DNL Audience Manager] は、 ID および ID にリンクされている最後のデバイス ID について、進行中のすべてのデータ収集、セグメント化、アクティブ化を停止します。[!DNL CRM][!DNL CRM]
* [!DNL Audience Manager] すべてのセグメントから、オプトアウト [!DNL CRM] IDと最後のデバイスIDをセグメント解除します。
* [!UICONTROL Destination] パートナーは、 [!DNL CRM] IDと最後のデバイスIDに対するセグメント解除リクエストを受け取ります。 セグメント化解除は、[リアルタイム](data-privacy-requests.md#aam-partners-with-unsegmentation)宛先とバッチ宛先の両方で機能します。
* 履歴データは削除されません。

When [!DNL Audience Manager] receives a partner-level opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the [!DNL Audience Manager] user ID.

`d_cid` および `d_cid_ic` のキーと値のペアを使用して宣言済み ID のオプトアウトリクエストを作成できます。`d_dpid` や `d_dpuuid` などの従来のパラメーターはまだ機能しますが、既に廃止されています。詳しくは、[DPID と DPUUID に代わる CID](../../reference/cid.md) を参照してください。以下の例で、*斜体*&#x200B;の部分には実際の情報が入ります。

#### オプトアウト(お [!DNL CID] よび [!DNL CID_IC]

説明と構文については、[宣言された ID の URL 変数および構文](../../features/declared-ids.md#variables-and-syntax)を参照してください。

| オプトアウト方法 | コードサンプル |
|--- |--- |
| データプロバイダー ID およびユーザー ID。 | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 統合コードおよびユーザー ID。 | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 複数の `d_cid` および `d_cid_ic` のキー値ペア | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### デバイス ID 呼び出しを使用するパートナーレベルのオプトアウト

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) に対して次の呼び出しを行うことにより、ブランドの指定デバイス ID でのデータ収集からオプトアウトできます。

| オプトアウト方法 | コードサンプル |
|--- |--- |
| [!DNL Audience Manager] ( [!DNL Unique User ID]`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| An [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

詳しくは、[Audience Manager で使用される ID の一覧](/help/using/reference/ids-in-aam.md)の `uuid`、`mid`、および `imsOrgId` を参照してください。

デバイス ID 呼び出しを使用するパートナーレベルのオプトアウトの後：

* デバイス ID がデータ収集からオプトアウトされます。
* [!DNL Audience Manager] は、そのデバイス ID に転送される、パートナーのすべてのデータ収集、セグメント化またはアクティブ化を停止します。
* [!DNL Audience Manager] すべてのセグメントからデバイスIDのセグメント化を解除します。
* 宛先パートナーは、デバイス ID のセグメント解除要求を受け取ります。セグメント化解除は、[リアルタイム](data-privacy-requests.md#aam-partners-with-unsegmentation)宛先とバッチ宛先の両方で機能します。
* 履歴データは削除されません。

## [!DNL Audience Manager] セグメント化解除機能を持つパートナー {#aam-partners-with-unsegmentation}

In order to help you automate your consumer data privacy requests, [!DNL Audience Manager] will attempt to notify activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

ただし、一部のアクティベーションパートナーは、以下のいずれかまたは両方の状態である場合があります。

1. Cannot support unsegment requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

セグメント解除をサポートする アクティベーションパートナーを確認するには、[デバイスベースの宛先のリスト](/help/using/features/destinations/device-based-destinations-list.md)を参照してください。[!DNL Audience Manager]

## データ修正要求 {#correction}

Given that [!DNL Audience Manager] is not the source of the data, there is a limited role for data correction in [!DNL Audience Manager]. The correction could mean that the consumer has requested to either be disqualified from an incorrect [!UICONTROL trait]/[!UICONTROL segment] or qualified to the desired [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] ユーザーは、ユーザーのプロファイルに対して関連するシグナル/特性/セグメントを取り込み、 [オフラインデータ取り込みを通じて](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 、この情報を送信でき [!DNL Audience Manager]ます。 Please note that the user will continue to get qualified to the original [!UICONTROL trait] and [!UICONTROL segments] if they repeat their behavior.
