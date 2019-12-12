---
description: このドキュメントでは、Audience Manager のデータプライバシー規制への準拠に関する技術について説明します。
seo-description: このドキュメントでは、Audience Manager のデータプライバシー規制への準拠に関する技術について説明します。
seo-title: データのプライバシーリクエスト
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: データのプライバシーリクエスト
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 09ac547f22bc07e5b8609226ddd736cb79cbc700

---


# データのプライバシーリクエスト {#data-privacy-requests}

## 概要 {#overview}

このドキュメントでは、個人データのプライバシー管理と、[プライバシーサービスの UI](https://gdprui.cloud.adobe.io/) および **[!DNL Privacy Service API]** を使用して Audience Manager に送信できるオプトアウトリクエストについて説明します。

これらのツールを使用すると、GDPR および CCPA に基づいて行われた消費者データのプライバシーリクエストを送信できます。

この記事を読む前に、[GDPR の用語集](../data-security-and-privacy/aam-gdpr-glossary.md)と [CCPA の用語集](aam-ccpa-glossary.md)を参照して、ここで使用する用語の理解を深めることをお勧めします。

Audience Manager から消費者データにアクセスして削除する個々のリクエストを送信するには、次の 2 つの方法があります。

* [プライバシーサービスの UI](https://gdprui.cloud.adobe.io/) を使用する。[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)のドキュメントを参照してください。
* **[!DNL Privacy Service API]**&#x200B;を使用する。[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)のドキュメントおよび[こちら](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)の API　リファレンスを参照してください。

個々のデータのプライバシーリクエストを送信する場合、**[Audience Manager 識別子](data-privacy-ids.md)**&#x200B;の節で説明されているように、Audience Manager 識別子（ID）を、それぞれの名前空間 ID（データソース ID）と共に送信できます。

[プライバシーサービス](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)は、データアクセスおよびデータ削除の 2 種類のリクエストをサポートします。

## データアクセスリクエスト {#access-data}

個々のデータアクセスリクエストは、[プライバシ－サービスの UI](https://gdprui.cloud.adobe.io/)（ドキュメントは[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)）または [!DNL Privacy Service API]（ドキュメントは[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)、[!DNL API]レフェレンスは [こちら](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)）を呼び出して送信できます。

[プライバシーサービスの UI ](https://gdprui.cloud.adobe.io/)では、[!UICONTROL Request Builder] を使用するか、[!DNL JSON] ファイルをアップロードすることで、新しいジョブリクエストを作成できます。

有効な [!DNL JSON] ファイルがどのようなものであるかを確認するには、[JSON のサンプルをダウンロード](../data-security-and-privacy/assets/access_request.json)できます。

アドビは、顧客のデータのプライバシー要求を法律で定められた期間内に処理する取り組みを理解しています。

## データ削除リクエスト {#delete-data}

データ削除リクエストは、[プライバシーサービスの UI](https://gdprui.cloud.adobe.io/)（ドキュメントは[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)）または[!DNL Privacy Service API]（ドキュメントは[こちら](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)、API リファレンスは[こちら](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)）を呼び出して送信できます。

[プライバシーサービスの UI ](https://gdprui.cloud.adobe.io/)では、[!UICONTROL Request Builder] を使用するか、[!DNL JSON] ファイルをアップロードすることで、新しいジョブリクエストを作成できます。

有効な [!DNL JSON] ファイルがどのようなものであるかを確認するには、[JSON のサンプルをダウンロード](../data-security-and-privacy/assets/access_request.json)できます。

アドビは、データのプライバシーに関するお客様の要請を受信後30日以内に遵守する取り組みを理解しています。 そのため、アドビはデータ削除リクエストの処理をできるだけ早く行うことに取り組んでいます。

コンシューマーデータ削除のリクエストに応じて、Audience Managerは、リクエストに含まれるAudience Manager識別子に関連付けられた特徴とセグメントを削除します。 さらに、Audience Managerによる追加のデータ収集からオプトアウトされた個々のAudience Manager識別子に対応するIDマッピングは削除されます。

複数のデバイスにまたがる [!DNL CRM] ID や顧客の Cookie ID などの宣言済み ID がデータプライバシー要求で送信された場合、Audience Manager は関連付けられたすべてのデバイス（1 つの宣言済み ID につき最大 100 個のデバイス）に対して必要な削除をおこないます。

Audience Managerは、特定のデータの削除を要求するデータサブジェクトのセグメント化解除情報を送信することで、アクティベーションパートナーに削除の要求に関する通知を試行します。 ただし、一部のアクティベーションパートナーは、

1. Audience Managerまたは
2. 30日未満の頻度でAudience Managerから更新を受け取ることはできません。 その場合、Audience Managerのお客様は、Audience Managerを使用して自動化された方法で、アクティベーションパートナーに削除リクエストを送信できません。

このような場合、お客様はアクティベーションパートナーに対して、Audience Manager から自動で削除要求を送信することはできません。

Audience Manager のアクティベーションパートナーの中でどれがセグメント解除をサポートしているかを確認するには、[パートナーに関する Excel シート](assets/AAM-Partners-October2019.xlsx)をダウンロードしてください。

## オプトアウト要求 {#opt-out-requests}

Audience Managerは、オプトアウト管理に関する業界全体の標準をサポートしています。 Audience Manager でサポートされているオプトアウトのタイプについて詳しくは、以降の説明を参照してください。

データのアクセスおよび削除要求は[プライバシーサービス](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)で処理されますが、現在、オプトアウトの要求は DCS API を通じてサポートされています。オプトアウト API 呼び出しの例を以下に示します。

### グローバルオプトアウト要求

グローバルオプトアウトは、すべてのブランドにおける Audience Manager およびその他の Adobe Experience Cloud ソリューションにまたがるオプトアウトです。次の表は、グローバルオプトアウトに使用する手法の一覧です。

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
   <td colname="col2"> <p><a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external">プライバシーの設定ページ</a>には、エンドユーザーが Adobe Experience Cloud 広告ソリューション（Audience Manager など）によるデータ収集の制御やオプトアウトをおこなうための 1 クリック機能があります。特に、プライバシーの選択肢ページの<a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external">ビジネス関連の顧客のセクション</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audience Manager に対する直接 API 呼び出し </p> </td> 
   <td colname="col2"> <p>すべての Audience Manager ブランドによるデータ収集からオプトアウトするには、以下のように DCS API を呼び出し、<a href="../../reference/ids-in-aam.md">Audience Manager ユーザー ID </a>を含めます。 </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>その結果、送信された Audience Manager ユーザー ID に対して <code>demdex=NOTARGET</code> および <code>dextp=NOTARGET</code> Cookie が設定されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>モバイルデバイス </p> </td> 
   <td colname="col2"> <p>以下のデバイスに対するオプトアウト設定とプライバシー設定を確認します。 </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android デバイス </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS デバイス </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

エンドユーザーは、アドビの業界標準パートナーの Web サイトを訪問してグローバルデータ収集からオプトアウトすることもできます。

* [Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/)
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/)

上記のオプトアウトリクエストをおこなうと、次の処理がおこなわれます。

* ユーザーがブラウザーのCookieをクリアしない限り、Audience Managerは、今後すべてのデータ収集、セグメント化またはアクティブ化を停止します。
* 120 日後にユーザープロファイルから履歴データが削除されます。

### 宣言された ID 呼び出しを使用するパートナーレベルのオプトアウト

パートナーレベルのオプトアウトでは、特定の Audience Manager パートナーによるデータ収集からユーザーをオプトアウトできます。CRM ID やハッシュ化された電子メールアドレスなど、クロスデバイス ID に対するパートナーレベルのオプトアウト要求を送信できます。

宣言された ID 呼び出しを使用するパートナーレベルのオプトアウトの後：

* [CRM ID](../../reference/ids-in-aam.md) がデータ収集からオプトアウトされます;
* [CRM ID](../../reference/ids-in-aam.md) にリンクされている最後のデバイス ID（[Audience Manager の一意のユーザー ID](../../reference/ids-in-aam.md)）は、データ収集からオプトアウトされます。
* Audience Manager は、CRM ID および CRM ID にリンクされている最後のデバイス ID について、進行中のすべてのデータ収集、セグメント化、アクティブ化を停止します。
* Audience Manager は、すべてのセグメントから、オプトアウトされた CRM ID と最後のデバイス ID のセグメントを解除します。
* 宛先パートナーは、CRM ID と最後のデバイス ID に対するセグメント解除要求を受け取ります。セグメント化解除は、[リアルタイム](data-privacy-requests.md#aam-partners-with-unsegmentation)宛先とバッチ宛先の両方で機能します。
* 履歴データは削除されません。

Audience Manager がパートナーレベルのオプトアウトリクエストを受信すると、DCS により返される JSON には[エラーコード 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes) が含まれます。ここには、Audience Manager ユーザー ID ではなく、[!UICONTROL "Encountered opt out tag"] というメッセージが表示されます。

`d_cid` および `d_cid_ic` のキーと値のペアを使用して宣言済み ID のオプトアウトリクエストを作成できます。`d_dpid` や `d_dpuuid` などの従来のパラメーターはまだ機能しますが、既に廃止されています。詳しくは、[DPID と DPUUID に代わる CID](../../reference/cid.md) を参照してください。以下の例で、*斜体*&#x200B;の部分には実際の情報が入ります。

#### CID および CID_IC を使用したオプトアウト

説明と構文については、[宣言済み ID の URL 変数および構文](../../features/declared-ids.md#variables-and-syntax)を参照してください。

| オプトアウト方法 | コードサンプル |
|--- |--- |
| データプロバイダー ID およびユーザー ID | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 統合コードおよびユーザー ID | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 複数の d_cid および d_cid_ic キー値ペア | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### デバイス ID 呼び出しを使用するパートナーレベルのオプトアウト

パートナーレベルのオプトアウトでは、特定の Audience Manager パートナーによるデータ収集からユーザーをオプトアウトできます。[DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) に対して次の呼び出しを行うことにより、ブランドの指定デバイス ID でのデータ収集からオプトアウトできます。

| オプトアウト方法 | コードサンプル |
|--- |--- |
| Audience Manager の一意のユーザー ID（`uuid`） | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Experience Cloud ID（`mid`） | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

詳しくは、[Audience Manager で使用される ID の一覧](/help/using/reference/ids-in-aam.md)の `uuid`、`mid`、および `imsOrgId` を参照してください。

デバイス ID 呼び出しを使用するパートナーレベルのオプトアウトの後：

* デバイス ID がデータ収集からオプトアウトされます。
* Audience Manager は、そのデバイス ID に転送される、パートナーのすべてのデータ収集、セグメント化またはアクティブ化を停止します。
* Audience Manager は、すべてのセグメントからデバイス ID のセグメントを解除します。
* 宛先パートナーは、デバイス ID のセグメント解除要求を受け取ります。セグメント化解除は、[リアルタイム](data-privacy-requests.md#aam-partners-with-unsegmentation)宛先とバッチ宛先の両方で機能します。
* 履歴データは削除されません。

## セグメント化解除に対応している Audience Manager パートナー {#aam-partners-with-unsegmentation}

コンシューマーデータのプライバシーリクエストを自動化するため、Audience Managerは、セグメント解除（またはセグメントの削除）情報を送信して、データサブジェクトからの削除リクエストについてアクティベーションパートナーに通知しようとします。

ただし、一部のアクティベーションパートナーは、以下のいずれかまたは両方の状態である場合があります。

1. Audience Managerまたは
2. 30日間で、Audience Managerからより頻繁に更新を受け取ることはできません。

このような場合、お客様はアクティベーションパートナーに対して、Audience Manager から自動で削除要求を送信することはできません。

Audience Manager のアクティベーションパートナーの中でどれがセグメント解除をサポートしているかを確認するには、[パートナーに関する Excel シート](assets/AAM-Partners-October2019.xlsx)をダウンロードしてください。

## データ修正要求 {#correction}

Audience Manager はデータソースではないので、データ修正に対して Audience Manager でできることは限られています。この修正は、コンシューマーが不正な特性/セグメントから資格を失うか、目的の特性/セグメントに資格を与えるかを要求したことを意味する場合があります。

Audience Manager をご利用のお客様は、ユーザープロファイルに合致する信号／特性／セグメントを取得し、[オフラインのデータ収集](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)を通してこの情報を Audience Manager に送信できます。ユーザーの動作が変わらない限り、元の特性およびセグメントに適合したままとなることにご注意ください。
