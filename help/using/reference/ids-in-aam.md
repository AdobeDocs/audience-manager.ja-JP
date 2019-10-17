---
description: Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。
seo-title: Audience Manager で使用される ID の一覧
solution: Audience Manager
title: Audience Manager で使用される ID の一覧
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: ee11fe79cd81a17659c371b279536fd156aa360b

---


# Audience Manager で使用される ID の一覧{#index-of-ids-in-audience-manager}

Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。

| ID|名前と説明|例||—|—|—|| [!DNL AAM UUID] | Audience Manager固有のユーザーID。 数値型で 38 桁のデバイス ID。Audience Manager はこの値を、操作するデバイスのそれぞれに関連付けます。Audience Manager UIで一意のユーザーのメンションが表示される場合は常に、この ID を考慮してください。Audience Manager saves this ID as a cookie in the `demdex.net` 3rd party domain. The Audience Manager UUID is sent in event calls as the `d_uuid` signal. | `demdex = 07955261652886032950143702505894272138` |
| [!DNL ImsOrgId]|組織 ID. 会社が Experience Cloud にサインアップする際に生成される ID です。会社の組織IDを検索する方法については、「組織IDを検索」を [参照してください](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)。 |`5DC5123F5245B1D20A490D46@AdobeOrg`||PID|パートナーID。 PID は、Audience Manager での会社の ID です。Audience Manager associates an [!DNL imsOrgId] to a [!DNL PID]. |`1352`|
|[!DNL ECID], [!DNL MID]|Experience Cloud ID. The Experience Cloud ID ([!DNL ECID], legacy abbreviations [!DNL MID] or [!DNL MCID]) is derived mathematically from your Organization ID and the Audience Manager Unique User ID. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. You can read more about the ECID in the [Cookies and Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) documentation. |`mid = 08382830887934830189014177072406221371` |
|[!DNL SID]|特性 ID. 特性 ID は、 Audience Manager 環境内の特性を一意に識別します。ユーザーインターフェイス（UI）の各特性に特性 ID が割り当てられます。|`289983`|
|SID|Segment ID. セグメント ID は、 Audience Manager 環境内のセグメントを一意に識別します。UI の各セグメントにセグメント ID が割り当てられます。|`4798574`|
|[!DNL csegID]|Legacy Segment ID. この ID は、 Audience Manager 環境内のセグメントを一意に識別します。UI の各セグメントにレガシーセグメント ID が割り当てられます。|`741232`|
|[!DNL destID]|Destination ID. 宛先 ID は、 Audience Manager 環境内の宛先を一意に識別します。UI の各宛先に ID が割り当てられます。|`2523`|
|[!DNL DPID]|Data Source ID (also referred to as Data Provider ID). データソース ID は ID または特性の名前空間です。UI の各データソース（データプロバイダー）に ID が割り当てられます。| `39217` |
|[!DNL DPUUID]|Data Provider Unique User ID (also referred to as [!DNL CRM ID]). サードパーティ ID。This is the ID by which you identify end users in your own [!DNL CRM] system. You can sync [!DNL DPUUIDs] with Audience Manager [!DNL UUIDs] and you can sync [!DNL DPUUIDs] from your different Data Sources ([!DNL DPIDs]) in the ID synchronization process. |`2132-3423vn-343fds-3432r`||[!DNL CRM ID]|DPUUIDを参照してください。|`2132-3423vn-343fds-3432r`|
|[!DNL CID], [!DNL CID_IC]|顧客 ID、顧客 ID 統合コード. とのキ [!DNL CID] ーと値 [!DNL CID_IC] のペアが、とに置き換 [!DNL DPID] わりま [!DNL DPUUID]す。 They provide the same functions as the [!DNL DPID] and [!DNL DPUUID], but are more efficient because they include the data provider ID and user ID (or integration code) in a single key-value pair. ||
|[!DNL DAID]|Device Advertising ID. 各ハードウェアデバイスに一意の ID で、広告目的で使用されます。通常は、デバイスの製造元またはデバイスのオペレーティングシステムにより設定されます。|グローバルデ [バイスIDを参照してください](#global-device-ids)。 |

## グローバルデバイスID {#global-device-ids}

グローバルデバイスIDは、デバイスの製造元またはオペレーティングシステムが提供する、各デバイスに固有のデバイス広告IDです。 次の表に、これらのIDの内容と形式を示します。

| ID | 名前と説明 | 例 |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [!DNL IDFA] | [!DNL Identifier for Advertisers] ID はモバイルデバイス識別子で、デバイスの製造元により設定されます。この ID は iOS オペレーティングシステムを使用するデバイスを表します。 | 形式は厳密に 32 文字の大文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | [!DNL Google Advertising ID]sは、Androidデバイスの製造元が提供するモバイルデバイス識別子です。 These IDs represent devices that run the [!DNL Android] operating system. | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | [!DNL Roku IDs for Advertising] は、ストリーミング [!DNL Roku] デバイスを表します。 | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | [!DNL Microsoft Advertising ID]sは、デバイスごと、ユ [!DNL Windows 10] ーザーごとに生成されるデバイス識別子です。 | [!DNL MAID]sは英数字の文字列として形式設定されます。 |
| [!DNL DUID] | [!DNL Samsung DUID]sは、Samsung Smart TVが提供するデバイス識別子です。 | Samsung [!DNL DUID]s are formatted as alphanumeric strings. |
| [!DNL Amazon Fire TV Advertising ID] | オペレーティングシステムを実行しているデバイスを表す [!DNL Fire OS] デバイス識別子。 | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。例：`df07c7dc-cea7-4a89-b328-810ff5acb15d` |
