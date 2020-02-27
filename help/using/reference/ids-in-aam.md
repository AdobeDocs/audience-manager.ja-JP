---
description: Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。
seo-title: Audience Manager で使用される ID の一覧
solution: Audience Manager
title: Audience Manager で使用される ID の一覧
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: f8916812a31513d3d8401a0598f37dae02a3fd02

---


# Audience Manager で使用される ID の一覧{#index-of-ids-in-audience-manager}

## 概要 {#overview}

Audience Managerは、複数のIDを使用して、送信するデータを識別し、管理します。 Adobe Audience Manager IDの完全なリストと、それらを使用する必要のあるプリフィックスの例については、この記事を参照してください。

## IDプリフィックス {#prefixing}

これらのIDのほとんどはスタンドアロン名で参照できますが、DCS呼び出しを通じてデータを渡す際に、様々な接頭辞と共に使用することが目的です。 これらのIDの一部は、ユーザーに公開されずにAudience Managerで使用され、その他のIDはユーザーインターフェイス(UI)にも表示されます。

以下の例で使用されるプリフィックスについて詳しくは、DCS API呼び出しでサ [ポートされる属性を参照してください。](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Audience Manager IDのリスト {#id-list}

| ID | 名前と説明 | 使用例 | UIの場所 |
|---|---|---|---|
| [!DNL AAM UUID] | Audience Manager の一意のユーザー ID数値型で 38 桁のデバイス ID。Audience Manager はこの値を、操作するデバイスのそれぞれに関連付けます。Audience Manager UIで一意のユーザーのメンションが表示される場合は常に、この ID を考慮してください。Audience Manager はこの ID を、「`demdex.net`」サードパーティドメインの cookie として保存します。 | 呼び出し [!DNL DCS] では、の前 `uuid` にプレフィックスが付 `d_` きます。 <br>例：`d_uuid = 07955261652886032950143702505894272138` | Audience Manager UIには表示されません。 |
| [!DNL ImsOrgId] | 組織 ID。これは、Experience cloudアカウントにサインアップしたときに会社に提供されるIDです。 | `5DC5123F5245B1D20A490D46@AdobeOrg` | Audience Manager UIには表示されません。 会社の組織 IDを 検索する方法については、「[組織 ID の検索](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)」を参照してください。 |
| PID | パートナー ID。PID は、Audience Manager での会社の ID です。Audience Manager は [!DNL imsOrgId] を [!DNL PID] に関連付けます。 | `1352` | Audience Manager UIには表示されません。 |
| [!DNL ECID]、[!DNL MID] | Experience Cloud ID。Experience Cloud ID（[!DNL ECID]、以前の略称 [!DNL MID] または [!DNL MCID]）は、組織 ID と Audience Manager の一意のユーザー ID から数学的に生成されます。これらの ID が変わらない限り、特定のユーザーに関する正しい [!DNL ECID] を生成できるかどうかは、単純に計算上の問題になります。同じ組織 ID と Audience Manager [!DNL UUID] があれば、いつでも同じ [!DNL ECID] 値が得られます。ECID について詳しくは、[Cookies と Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) のドキュメントを参照してください。 | `mid = 08382830887934830189014177072406221371` | Audience Manager UIには表示されません。 |
| [!DNL SID] | 特性 ID。特性 ID は、Audience Manager 環境内の特性を一意に識別します。 | 呼び出し [!DNL DCS] では、の前 `SID` にプレフィックスが付 `d_` きます。 <br>例 `d_sid=289983`. | 特性IDが各特性に割り当てられ、UIの特性ページに表示さ [れます](../features/traits/trait-details-page.md) 。 |
| [!DNL SID] | Segment ID。セグメント ID は、Audience Manager 環境内のセグメントを一意に識別します。 | 呼び出し [!DNL DCS] では、の前 `SID` にプレフィックスが付 `d_` きます。 <br>例 `d_sid=4798574`. | セグメントIDが各セグメントに割り当てられ、UIのセグメントページに表示さ [れます](../features/segments/segment-summary-view.md) 。 |
| [!DNL csegID] | レガシーセグメント ID。この ID は、Audience Manager 環境内のセグメントを一意に識別します。 | `741232` | 従来のセグメントIDが各セグメントに割り当てられ、UIのセグメントページに表示さ [れます](../features/segments/segment-summary-view.md) 。 |
| [!DNL destID] | 宛先 ID。宛先 ID は、Audience Manager 環境内の宛先を一意に識別します。UI の各宛先に ID が割り当てられます。 | `2523` | リンク先IDが各リンク先に割り当てられ、UIのリンク先ページに表示さ [れます](../features/destinations/destinations-home.md) 。 |
| [!DNL DPID] | データソース ID（データプロバイダー ID とも呼ばれます）。データソース ID は ID または特性の名前空間です。UI の各データソース（データプロバイダー）に ID が割り当てられます。 | 呼び出し [!DNL DCS] では、の前 `dpid` にプレフィックスが付 `d_` きます。 <br>例：`d_dpid=39217`。 | データプロバイダーIDが各データソースに割り当てられ、UIのデータソースページに表 [示されます](../features/datasources-list-and-settings.md) 。 |
| [!DNL DPUUID] | データプロバイダー個別ユーザー ID（[!DNL CRM ID]）。サードパーティ ID。[!DNL CRM] システムのエンドユーザーを識別するための ID です。[!DNL DPUUIDs] を Audience Manager の [!DNL UUIDs] と同期したり、 の UUID と同期したり、別のデータソース（[!DNL DPIDs]）からの [!DNL DPUUIDs] を ID 同期プロセスで同期したりできます。 | DCS呼び出しでは、の前に `dpuuid` 接頭辞が付いて `d_` います。 <br> 例 `d_dpuuid=2132-3423vn-343fds-3432r`. | Audience Manager UIには表示されません。 |
| [!DNL CRM ID] | See `DPUUID`. | See `DPUUID`. | See `DPUUID`. |
| [!DNL CID]、[!DNL CID_IC] | 顧客 ID、顧客 ID 統合コード。[!DNL CID] と [!DNL CID_IC] のキーと価のペアは、[!DNL DPID] と [!DNL DPUUID] を置き換えます。[!DNL DPID] および [!DNL DPUUID] と同じ機能ですが、1 つのキーと値のペアにデータプロバイダー ID とユーザー ID（または統合コード）が含まれるので、より効率的です。 | DCS呼び出しでは、これらのIDの前に接頭辞が付き `d_` ます。 <br>例：`d_cid_ic=39217_myIntegrationCode`。 | とを参 `DPID` 照してくだ `DPUUID`さい。 |
| [!DNL DAID] | デバイス広告 ID。各ハードウェアデバイスに一意の ID で、広告目的で使用されます。通常は、デバイスの製造元またはデバイスのオペレーティングシステムにより設定されます。 | 詳しくは、[グローバルデバイス ID](#global-device-ids) を参照してください。 |  |

## グローバルデバイス ID {#global-device-ids}

グローバルデバイス ID は、デバイスの製造元またはオペレーティングシステムが提供する、各デバイスに固有のデバイス広告 ID です。次の表に、これらの ID の内容と形式を示します。グローバルデバイス ID の概要と Audience Manager での使用方法について詳しくは、[グローバルデータソース](/help/using/features/global-data-sources.md)を参照してください。

| ID | グローバルデータソース ID | 名前と説明 | 例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID はモバイルデバイス識別子で、デバイスの製造元により設定されます。この ID は iOS オペレーティングシステムを使用するデバイスを表します。 | 形式は厳密に 32 文字の大文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`AEBE52E7-03EE-455A-B3C4-E57283966239`。 |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID] はモバイルデバイス識別子で、Android デバイスの製造元により設定されます。これらの ID は [!DNL Android] オペレーティングシステムを使用するデバイスを表します。 | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`e4fe9bde-caa0-47b6-908d-ffba3fa184f2`。 |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] は、[!DNL Roku] ストリーミングデバイスを表します。 | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`fcb2a29c-315a-5e6b-bcfd-d889ba19aada`。 |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID] は、デバイスごと、ユーザーごとに [!DNL Windows 10] で生成されるデバイス識別子です。 | [!DNL MAID] は英数字の形式です。 |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID] は、Samsung Smart TV が提供するデバイス識別子です。 | Samsung [!DNL DUID] は英数字の形式です。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | [!DNL Fire OS] オペレーティングシステムを実行しているデバイスを表すデバイス識別子。 | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`df07c7dc-cea7-4a89-b328-810ff5acb15d` |

