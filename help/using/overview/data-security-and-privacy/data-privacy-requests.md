---
description: このドキュメントでは、Audience Manager のデータプライバシー規制への準拠に関する技術について説明します。
seo-description: このドキュメントでは、Audience Manager のデータプライバシー規制への準拠に関する技術について説明します。
seo-title: データプライバシーリクエスト
solution: Audience Manager
keywords: GDPR UI、GDPR API、CCPA、プライバシー
title: データプライバシーリクエスト
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 99%

---

# データプライバシーリクエスト {#data-privacy-requests}

## 概要 {#overview}

このドキュメントでは、個人データのプライバシー管理と、[プライバシーサービスの UI](https://privacyui.cloud.adobe.io/) および **[!DNL Privacy Service API]** を使用して [!DNL Audience Manager] に送信できるオプトアウトリクエストについて説明します。

これらのツールを使用すると、[!DNL GDPR] および [!DNL CCPA] に基づいて行われた消費者データのプライバシーリクエストを送信できます。

この記事を読む前に、[GDPR の用語集](../data-security-and-privacy/aam-gdpr-glossary.md)と [CCPA の用語集](aam-ccpa-glossary.md)を参照して、ここで使用する用語の理解を深めることをお勧めします。

[!DNL Audience Manager] から消費者データにアクセスして削除する個々のリクエストを送信するには、次の 2 つの方法があります。

* [プライバシーサービスの UI](https://privacyui.cloud.adobe.io/) を使用する。[こちら](https://docs.adobe.com/content/help/ja-JP/experience-platform/privacy/home.translate.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)のドキュメントを参照してください。
* **[!DNL Privacy Service API]**&#x200B;を使用する。[こちら](https://docs.adobe.com/content/help/ja-JP/experience-platform/privacy/home.translate.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)のドキュメントおよび[こちらの](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml) [!DNL API] リファレンスを参照してください。

個々のデータのプライバシーリクエストを送信する場合、 **[Audience Manager 識別子](data-privacy-ids.md)** の節で説明されているように、[!DNL Audience Manager] 識別子（ID）を、それぞれの名前空間 ID（データソース ID）と共に送信できます。

[プライバシーサービス](https://docs.adobe.com/content/help/ja-JP/experience-platform/privacy/home.translate.html)は、データアクセスおよびデータ削除の 2 種類のリクエストをサポートします。

## データアクセスリクエスト {#access-data}

個々のデータアクセスリクエストは、[Privacy Service UI](https://privacyui.cloud.adobe.io)（ドキュメントは[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)）を使用して、または Privacy Service API （ドキュメントは[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)、[!DNL API] リファレンスは[こちら](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)）を呼び出して送信できます。

[プライバシーサービスの UI ](https://privacyui.cloud.adobe.io/)では、[!UICONTROL Request Builder] を使用するか、[!DNL JSON] ファイルをアップロードすることで、新しいジョブリクエストを作成できます。

有効な [!DNL JSON] ファイルがどのようなものであるかを確認するには、[JSON のサンプルをダウンロード](../data-security-and-privacy/assets/access_request.json)できます。

アドビは、お客様のデータのプライバシー要求を法律で定められた期間内に処理する取り組みを理解しています。

## データ削除リクエスト {#delete-data}

データ削除リクエストは、[Privacy Service UI](https://privacyui.cloud.adobe.io)（ドキュメントは[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)）を使用して、または Privacy Service API （ドキュメントは[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)、[!DNL API] リファレンスは[こちら](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)）を呼び出して送信できます。

[プライバシーサービスの UI ](https://privacyui.cloud.adobe.io/)では、[!UICONTROL Request Builder] を使用するか、[!DNL JSON] ファイルをアップロードすることで、新しいジョブリクエストを作成できます。

有効な [!DNL JSON] ファイルがどのようなものであるかを確認するには、[JSON のサンプルをダウンロード](../data-security-and-privacy/assets/access_request.json)できます。

アドビは、30 日以内にお客様のデータプライバシーに関するお客様の要請に応える取り組みを理解しています。そのため、[!DNL Adobe] では、お客様からのデータ削除要求をできるだけ早急に処理するよう努めています。

消費者データ削除要求への応答として、[!DNL Audience Manager] によって、要求に含まれている [!DNL Audience Manager] 識別子に関連付けられた特性およびセグメントが削除されます。さらに、個人に対する [!DNL Audience Manager] 識別子は以降の [!DNL Audience Manager] によるデータ収集から完全にオプトアウトされ、それぞれの ID マッピングは削除されます。

複数のデバイスにまたがる [!DNL CRM] ID や [!DNL cookie] ID などの宣言された ID がデータプライバシー要求で送信された場合、[!DNL Audience Manager] は関連付けられたすべてのデバイス（1 つの宣言された ID につき最大 100 個のデバイス）に対して必要な削除をおこないます。

[!DNL Audience Manager]特定のデータの削除を要求しているデータ主体のセグメント解除の情報を送信することで、 からアクティベーションパートナーに対して削除要求が通知されます。ただし、一部のアクティベーションパートナーは、

1. [!DNL Audience Manager] からのセグメント解除（またはセグメント削除）リクエストをサポートできません。
2. また、[!DNL Audience Manager] から 30 日未満の頻度で更新を受け取ることはできません。このような場合、[!DNL Audience Manager] をご利用のお客様は、アクティベーションパートナーに対して [!DNL Audience Manager] から自動で削除要求を送信することはできません。

このような場合、お客様はアクティベーションパートナーに対して、[!DNL Audience Manager] から自動で削除要求を送信することはできません。

セグメント解除をサポートする [!DNL Audience Manager] アクティベーションパートナーを確認するには、[パートナーに関する Excel シート](assets/AAM-Partners-October2019.xlsx)をダウンロードしてください。

## オプトアウト要求 {#opt-out-requests}

[!DNL Audience Manager] は、オプトアウト管理に関する業界全体の標準をサポートしています。[!DNL Audience Manager] でサポートされているオプトアウトのタイプについて詳しくは、以降の説明を参照してください。

データアクセスおよび削除の要求は[プライバシーサービス](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)で処理されますが、現在、オプトアウト要求は [!DNL DCS API] を通じてサポートされています。オプトアウト [!DNL API] 呼び出しの例を以下に示します。

### グローバルオプトアウト要求

グローバルオプトアウトは、すべてのブランドにおける [!DNL Audience Manager] およびその他の [!DNL Adobe Experience Cloud] ソリューションにまたがるオプトアウトです。次の表は、グローバルオプトアウトに使用する手法の一覧です。

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
   <td colname="col2"> <p><a href="https://www.adobe.com/jp/privacy/opt-out.html#customeruse" format="http" scope="external">プライバシーの設定ページ</a>には、エンドユーザーが Adobe Experience Cloud 広告ソリューション（Audience Manager など）によるデータ収集の制御やオプトアウトをおこなうための 1 クリック機能があります。特に、プライバシーの選択肢ページの<a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external">ビジネス関連の顧客のセクション</a>を参照してください。 </p> </td> 
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

パートナーレベルのオプトアウトでは、特定の [!DNL Audience Manager] パートナーによるデータ収集からユーザーをオプトアウトできます。[!DNL CRM] ID やハッシュ化された電子メールアドレスなど、クロスデバイス ID に対するパートナーレベルのオプトアウト要求を送信できます。

宣言された ID 呼び出しを使用するパートナーレベルのオプトアウトの後：

* [CRM ID](../../reference/ids-in-aam.md) がデータ収集からオプトアウトされます;
* [CRM ID](../../reference/ids-in-aam.md) にリンクされている最後のデバイス ID（[Audience Manager の一意のユーザー ID](../../reference/ids-in-aam.md)）は、データ収集からオプトアウトされます。
* [!DNL Audience Manager] は、[!DNL CRM] ID および [!DNL CRM] ID にリンクされている最後のデバイス ID について、進行中のすべてのデータ収集、セグメント化、アクティブ化を停止します。
* [!DNL Audience Manager] は、すべてのセグメントから、オプトアウトされた [!DNL CRM] ID と最後のデバイス ID のセグメントを解除します。
* [!UICONTROL Destination] パートナーは、[!DNL CRM] ID と最後のデバイス ID に対するセグメント解除要求を受け取ります。セグメント化解除は、[リアルタイム](data-privacy-requests.md#aam-partners-with-unsegmentation)宛先とバッチ宛先の両方で機能します。
* 履歴データは削除されません。

[!DNL Audience Manager] がパートナーレベルのオプトアウトリクエストを受信すると、[!DNL JSON] により返される [!DNL DCS] には[エラーコード 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes) が含まれます。ここには、[!DNL Audience Manager] ユーザー ID ではなく、[!UICONTROL "Encountered opt out tag"] というメッセージが表示されます。

`d_cid` および `d_cid_ic` のキーと値のペアを使用して宣言された ID のオプトアウトリクエストを作成できます。`d_dpid` や `d_dpuuid` などの従来のパラメーターはまだ機能しますが、既に非推奨（廃止予定）となっています。詳しくは、[DPID と DPUUID に代わる CID](../../reference/cid.md) を参照してください。以下の例で、*斜体*&#x200B;の部分には実際の情報が入ります。

#### [!DNL CID] および [!DNL CID_IC] でのオプトアウト。

説明と構文については、[宣言された ID の URL 変数および構文](../../features/declared-ids.md#variables-and-syntax)を参照してください。

| オプトアウト方法 | コードサンプル |
|--- |--- |
| データプロバイダー ID およびユーザー ID。 | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 統合コードおよびユーザー ID。 | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 複数の `d_cid` および `d_cid_ic` のキー値ペア。 | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### デバイス ID 呼び出しを使用するパートナーレベルのオプトアウト

パートナーレベルのオプトアウトでは、特定の [!DNL Audience Manager] パートナーによるデータ収集からユーザーをオプトアウトできます。[DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) に対して次の呼び出しを行うことにより、ブランドの指定デバイス ID でのデータ収集からオプトアウトできます。

| オプトアウト方法 | コードサンプル |
|--- |--- |
| [!DNL Audience Manager] [!DNL Unique User ID]（`uuid`）。 | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| [!DNL Experience Cloud] ID（`mid`）。 | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

詳しくは、[Audience Manager で使用される ID の一覧](/help/using/reference/ids-in-aam.md)の `uuid`、`mid`、および `imsOrgId` を参照してください。

デバイス ID 呼び出しを使用するパートナーレベルのオプトアウトの後：

* デバイス ID がデータ収集からオプトアウトされます。
* [!DNL Audience Manager] は、そのデバイス ID に転送される、パートナーのすべてのデータ収集、セグメント化またはアクティブ化を停止します。
* [!DNL Audience Manager] は、すべてのセグメントからデバイス ID のセグメントを解除します。
* 宛先パートナーは、デバイス ID のセグメント解除要求を受け取ります。セグメント化解除は、[リアルタイム](data-privacy-requests.md#aam-partners-with-unsegmentation)宛先とバッチ宛先の両方で機能します。
* 履歴データは削除されません。

## セグメント化解除に対応している [!DNL Audience Manager] パートナー {#aam-partners-with-unsegmentation}

お客様が消費者データのプライバシーリクエストを自動化できるよう、[!DNL Audience Manager] からアクティベーションパートナーに対してセグメント解除（またはセグメント削除）の情報が送信され、データ主体からの削除要求が通知されます。

ただし、一部のアクティベーションパートナーは、以下のいずれかまたは両方の状態である場合があります。

1. [!DNL Audience Manager] からのセグメント解除の要求をサポートしていない。
2. 30 日に 1 回より高い頻度で [!DNL Audience Manager] からの更新を受け取ることができない。

このような場合、お客様はアクティベーションパートナーに対して、[!DNL Audience Manager] から自動で削除要求を送信することはできません。

セグメント解除をサポートする [!DNL Audience Manager] アクティベーションパートナーを確認するには、[デバイスベースの宛先のリスト](/help/using/features/destinations/device-based-destinations-list.md)を参照してください。

## データ修正要求 {#correction}

[!DNL Audience Manager] はデータソースではないので、データ修正に対して [!DNL Audience Manager] でできることは限られています。修正においては、消費者が不正確な [!UICONTROL trait]／[!UICONTROL segment] からの解除を求める場合、または正しい [!UICONTROL trait]／[!UICONTROL segment] への適合を求める場合のいずれかとなります。

[!DNL Audience Manager] をご利用のお客様は、ユーザープロファイルに合致する信号／特性／セグメントを取得し、[オフラインのデータ収集](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)を通してこの情報を [!DNL Audience Manager] に送信できます。ユーザーの動作が変わらない限り、元の [!UICONTROL trait] および [!UICONTROL segments] に適合したままとなることにご注意ください。
