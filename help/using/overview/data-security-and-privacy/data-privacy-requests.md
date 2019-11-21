---
description: このドキュメントでは、Audience Managerのデータプライバシー規制への準拠に関する技術について説明します。
seo-description: このドキュメントでは、Audience Managerのデータプライバシー規制への準拠に関する技術について説明します。
seo-title: データプライバシーリクエスト
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: データプライバシーリクエスト
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# データプライバシーリクエスト {#data-privacy-requests}

## 概要 {#overview}

このドキュメントでは、個人データのプライバシーと、プライバシーサービスのUIおよびを使用してAudience Managerに送信できるオプトアウト要求の管理 [に関する概要](https://gdprui.cloud.adobe.io/) を説明しま **[!DNL Privacy Service API]**&#x200B;す。

これらのツールを使用すると、GDPRおよびCCPAに基づいて行われたコンシューマーデータのプライバシーリクエストを送信できます。

この記事を読む前に、 [GDPR用語集と](../data-security-and-privacy/aam-gdpr-glossary.md) CCPA用語集を調べて [](aam-ccpa-glossary.md)、ここで使用する用語の理解を深めることをお勧めします。

Audience Managerからコンシューマーデータにアクセスして削除する個々のリクエストを送信するには、次の2つの方法があります。

* プライバシーサ [ービスのUIを使用](https://gdprui.cloud.adobe.io/)。 ドキュメントはこちらを参 [照してくださ](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)い。
* 通り抜けて **[!DNL Privacy Service API]**。 詳しくは、ここにあるドキ [ュメント](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) 、およびAPIリファレンスを参照して [ください](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)。

個々のデータのプライバシー要求を送信する場合、「 **[Audience Manager ID](data-privacy-ids.md)** 」の節で説明されているように、Audience Manager ID(ID)を、それぞれの名前空間ID（データソースID）と共に送信できます。

プライバシー [サービスは](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 、次の2種類のリクエストをサポートします。データアクセスおよびデータ削除のリクエストを作成できます。

## データアクセス要求 {#access-data}

個々のデータアクセス要求は、 [Privacy Service UI](https://gdprui.cloud.adobe.io/) (ここにある [documentation](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md))または [!DNL Privacy Service API] ( [documentation](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) and reference [!DNL API][](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)here)を通じて送信できます。

プライバ [シーサービスのUIを使用すると](https://gdprui.cloud.adobe.io/) 、を使用するか、ファイルをアップロードすることで、新しいジョ [!UICONTROL Request Builder] ブリクエストを作成で [!DNL JSON] きます。

To see what a valid [!DNL JSON] file looks like, you can [download a sample JSON](../data-security-and-privacy/assets/access_request.json).

法律で定められた期間内にお客様のデータプライバシーお客様の要請に応える取り組みを理解します。

## データ削除リクエスト{#delete-data}

データ削除リクエストは、 [Privacy Service UI](https://gdprui.cloud.adobe.io/) (ここにあるドキュメント [)または(ここにあるドキュメントおよびAPI参照](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md))を通じて送信で [!DNL Privacy Service API][](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)[](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)きます。

プライバ [シーサービスのUIを使用すると](https://gdprui.cloud.adobe.io/) 、を使用するか、ファイルをアップロードすることで、新しいジョ [!UICONTROL Request Builder] ブリクエストを作成で [!DNL JSON] きます。

To see what a valid [!DNL JSON] file looks like, you can [download a sample JSON](../data-security-and-privacy/assets/access_request.json).

データのプライバシーに関するお客様の要請を受領後30日以内に遵守する取り組みを理解いたします。 アドビでは、お客様からのデータ削除要求をできるだけ早急に処理するよう努めています。

データ削除のリクエストに応じて、リクエストに含まれるAudience Manager識別子に関連付けられた特性とセグメントを削除します。 さらに、データサブジェクトの各Audience Manager識別子は、Audience Managerによる追加のデータ収集から永久的にオプトアウトされ、各IDマッピングは削除されます。

When you send declared IDs, such as cross device [!DNL CRM] IDs or cookie IDs, in data privacy requests, Audience Manager will perform the necessary deletion on all the linked devices (up to 100 devices per declared ID).

特定のデータの削除を要求しているデータ主体のセグメント解除の情報を送信することで、Audience Manager からアクティベーションパートナーに対して削除要求が通知されます。ただし、一部のアクティベーションパートナーは、

1. アドビまたは
2. 30日未満の頻度で更新を受け取れません。 このような場合、Audience Manager をご利用のお客様は、アクティベーションパートナーに対して Audience Manager から自動で削除要求を送信することはできません。

このような場合、お客様はアクティベーションパートナーに対して、Audience Manager から自動で削除要求を送信することはできません。

Audience Manager のアクティベーションパートナーの中でどれがセグメント解除をサポートしているかを確認するには、[パートナーに関する Excel シート](assets/AAM-Partners-October2019.xlsx)をダウンロードしてください。

## オプトアウト要求 {#opt-out-requests}

アドビは、オプトアウト管理に関する業界全体のすべての標準に準拠しています。Audience Manager でサポートされているオプトアウトのタイプについて詳しくは、以降の説明を参照してください。

データアクセスおよび削除の要求はプライバシーサ [ービスで処理されますが](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)、現在、オプトアウトの要求はDCS APIを通じてサポートされています。 オプトアウトAPI呼び出しの例を以下に示します。

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
   <td colname="col2"> <p>Your users can opt-out from data collection by all Audience Manager brands by making a call to the DCS API below and include the <a href="../../reference/ids-in-aam.md"> Audience Manager User ID </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>As a result, we will set <code>demdex=NOTARGET</code> and <code>dextp=NOTARGET</code> cookies for the submitted Audience Manager User ID. </p> </td> 
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

* [Digital Advertising Alliance（DAA）](https://optout.aboutads.info/?c=2#!/)
* [Network Advertising Initiative（NAI）](https://optout.networkadvertising.org/?c=1#!/)

上記のオプトアウトリクエストをおこなうと、次の処理がおこなわれます。

* Audience Manager は進行中のすべてのデータ収集、セグメント化、アクティブ化を停止します。
* 120 日後にユーザープロファイルから履歴データが削除されます。

### 宣言済みID呼び出しを使用したパートナーレベルのオプトアウト

パートナーレベルのオプトアウトでは、特定のAudience Managerパートナーによるデータ収集からユーザーをオプトアウトできます。 CRM IDやハッシュ化された電子メールアドレスなど、クロスデバイスIDに対するパートナーレベルのオプトアウト要求を送信できます。

宣言された ID 呼び出しを使用するパートナーレベルのオプトアウトの後：

* The [CRM ID](../../reference/ids-in-aam.md) is opted out of data collection;
* [CRM ID](../../reference/ids-in-aam.md) にリンクされている最後のデバイス ID（[Audience Manager の一意のユーザー ID](../../reference/ids-in-aam.md)）は、データ収集からオプトアウトされます。
* Audience Managerは、CRM IDと、CRM IDにリンクされた最後のデバイスIDに関するデータ収集、セグメント化またはアクティブ化をすべて停止します。
* Audience Managerは、すべてのセグメントから、オプトアウトされたCRM IDと最後のデバイスIDのセグメントを解除します。
* 宛先パートナーは、CRM IDと最後のデバイスIDに対するセグメント解除要求を受け取ります。 セグメント化解除は、リアルタ [イム宛先とバッチ](data-privacy-requests.md#aam-partners-with-unsegmentation) 宛先の両方で機能します。
* 履歴データは削除されません。

Audience Manager がパートナーレベルのオプトアウトリクエストを受信すると、DCS により返される JSON には[エラーコード 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes) が含まれます。ここには、Audience Manager ユーザー ID ではなく、[!UICONTROL "Encountered opt out tag"] というメッセージが表示されます。

`d_cid` および `d_cid_ic` のキーと値のペアを使用して宣言済み ID のオプトアウトリクエストを作成できます。`d_dpid` や `d_dpuuid` などの従来のパラメーターはまだ機能しますが、既に廃止されています。詳しくは、[DPID と DPUUID に代わる CID](../../reference/cid.md) を参照してください。以下の例で、*斜体*&#x200B;の部分には実際の情報が入ります。

#### CIDとCID_ICを使用したオプトアウト

説明と構文については、[宣言済み ID の URL 変数および構文](../../features/declared-ids.md#variables-and-syntax)を参照してください。

| オプトアウト方法 | コードサンプル |
|--- |--- |
| データプロバイダー ID およびユーザー ID | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 統合コードおよびユーザー ID | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 複数の d_cid および d_cid_ic キー値ペア | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### デバイス ID 呼び出しを使用するパートナーレベルのオプトアウト

パートナーレベルのオプトアウトでは、特定のAudience Managerパートナーによるデータ収集からユーザーをオプトアウトできます。 [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) に対して次の呼び出しを行うことにより、ブランドの指定デバイス ID でのデータ収集からオプトアウトできます。

| オプトアウト方法 | コードサンプル |
|--- |--- |
| Audience Manager の一意のユーザー ID（`uuid`） | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Experience Cloud ID（`mid`） | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

詳しくは、[Audience Manager で使用される ID の一覧](/help/using/reference/ids-in-aam.md)の `uuid`、`mid`、および `imsOrgId` を参照してください。

デバイス ID 呼び出しを使用するパートナーレベルのオプトアウトの後：

* デバイス ID がデータ収集からオプトアウトされます。
* Audience Manager は、そのデバイス ID に転送される、パートナーのすべてのデータ収集、セグメント化またはアクティブ化を停止します。
* Audience Managerは、すべてのセグメントからデバイスIDのセグメントを解除します。
* 宛先パートナーは、デバイスIDのセグメント解除要求を受け取ります。 セグメント化解除は、リアルタ [イム宛先とバッチ](data-privacy-requests.md#aam-partners-with-unsegmentation) 宛先の両方で機能します。
* 履歴データは削除されません。

## セグメント解除に対応している Audience Manager パートナー {#aam-partners-with-unsegmentation}

お客様がデータのプライバシーリクエストを自動化できるように、Audience Managerは、データサブジェクトからの削除リクエストについて、セグメント解除（またはセグメントの削除）情報を送信することでアクティベーションパートナーに通知します。

ただし、一部のアクティベーションパートナーは、以下のいずれかまたは両方の状態である場合があります。

1. アドビからのセグメント解除の要求をサポートしていない。
1. 30 日に 1 回より高い頻度でアドビからの更新を受け取ることができない。

このような場合、お客様はアクティベーションパートナーに対して、Audience Manager から自動で削除要求を送信することはできません。

Audience Manager のアクティベーションパートナーの中でどれがセグメント解除をサポートしているかを確認するには、[パートナーに関する Excel シート](assets/AAM-Partners-October2019.xlsx)をダウンロードしてください。

## データ修正要求 {#correction}

Audience Manager はデータソースではないので、データ修正に対して Audience Manager でできることは限られています。修正においては、データ主体が不正確な特性／セグメントからの解除を求める場合、または正しい特性／セグメントへの適合を求める場合のいずれかとなります。

Audience Manager Customers can choose to capture the relevant signals/traits/segments against user profiles and send this information through [offline data ingestion](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) to Audience Manager. ユーザーの動作が変わらない限り、元の特性およびセグメントに適合したままとなることにご注意ください。
