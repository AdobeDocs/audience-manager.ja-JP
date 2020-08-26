---
description: Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。
seo-title: Audience Manager で使用される ID の一覧
solution: Audience Manager
title: Audience Manager で使用される ID の一覧
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: reference
translation-type: tm+mt
source-git-commit: b8b848ad04d1ec07c12e57d94e4f3c6e672dc102
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 54%

---


# Index of IDs in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## 概要 {#overview}

[!DNL Audience Manager] は、複数の ID を使用して、送信するデータを識別および管理します。Refer to this article for the complete list of [!DNL Audience Manager] IDs, together with examples of the prefixes you should use them with.

## ID プレフィックス {#prefixing}

While you can refer to most of these IDs by their standalone names, most of them are meant to be used with various prefixes, when passing in data through [!DNL DCS] calls. Some of these IDs are used by [!DNL Audience Manager] without being exposed to users, while others are also visible in the user interface (UI).

以下の例で使用されるプレフィックスについて詳しくは、[DCS API 呼び出しでサポートされる属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)を参照してください。

## [!DNL Audience Manager] ID のリスト {#id-list}

| ID | 名前と説明 | 使用例 | ユーザーインターフェイスの場所 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]（別名） [!UICONTROL Device ID]。 数値型で 38 桁のデバイス ID。[!DNL Audience Manager] はこの値を、操作するデバイスのそれぞれに関連付けます。Think of this ID whenever you see a mention of unique users in the [!DNL Audience Manager] UI. Audience Manager saves this ID as a [!DNL cookie] in the `demdex.net` 3rd party domain. | [!DNL DCS] 呼び出しでは、`uuid` の前に `d_` プレフィックスが付きます。<br>例：`d_uuid = 07955261652886032950143702505894272138` | You can filter [!DNL traits] by [!UICONTROL Device ID] when creating [Look-Alike Models](../features/algorithmic-models/create-model.md), and [building segments](../features/segments/segment-builder.md). また、[特性に関する一般レポート](../reporting/general-reports.md)および[特性に関するトレンドレポート](../reporting/trend-reports.md)を実行中に、[!UICONTROL Device ID] で結果をフィルタリングできます。 |
| [!DNL ImsOrgId] | [!DNL Organization ID]をインストールします。This is the ID that a company is provided with upon signing up for an [!DNL Experience Cloud] account. | `5DC5123F5245B1D20A490D46@AdobeOrg` | ユーザーインター [!DNL Audience Manager] フェイスには表示されません。 To learn how you can find your company&#39;s [!DNL Organization ID], read [Find your Organization ID](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]をインストールします。The [!DNL PID] is a company&#39;s ID in [!DNL Audience Manager]. Audience Manager は [!DNL imsOrgId] を [!DNL PID] に関連付けます。 | `1352` | ユーザーインター [!DNL Audience Manager] フェイスには表示されません。 |
| [!DNL ECID]、[!DNL MID] | [!DNL Experience Cloud] ID. ID( [!DNL Experience Cloud] 従来の略語、または[!DNL ECID])は、ユーザーとユーザー [!DNL MID] から数学的に導き出され [!DNL MCID]ま [!DNL Organization ID][!DNL Audience Manager][!UICONTROL Unique User ID]す。 これらの ID が変わらない限り、特定のユーザーに関する正しい [!DNL ECID] を生成できるかどうかは、単純に計算上の問題になります。With the same [!DNL Organization ID] and [!DNL Audience Manager] [!DNL UUID] you get the same [!DNL ECID] value every time. You can read more about the [!DNL ECID] in the [Cookies and Experience Cloud ID](https://docs.adobe.com/content/help/ja-JP/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) documentation. | `mid = 08382830887934830189014177072406221371` | ユーザーインター [!DNL Audience Manager] フェイスには表示されません。 |
| [!DNL SID] | [!UICONTROL Trait ID]をインストールします。は、 [!UICONTROL Trait ID] 環境内で一意 [!DNL traits][!DNL Audience Manager] に識別します。 | [!DNL DCS] 呼び出しでは、`SID` の前に `d_` プレフィックスが付きます。<br>例 `d_sid=289983`。 | A [!UICONTROL Trait ID] が各に割り当てら [!DNL trait]れ、ユーザーインターフェイスの [特徴](../features/traits/trait-details-page.md) ページに表示されます。 |
| [!DNL SID] | [!UICONTROL Segment ID]をインストールします。は、 [!UICONTROL Segment ID] 環境内で一意 [!DNL segments][!DNL Audience Manager] に識別します。 | [!DNL DCS] 呼び出しでは、`SID` の前に `d_` プレフィックスが付きます。<br>例 `d_sid=4798574`。 | 各セグメント [!UICONTROL Segment ID] にはが割り当てら [!DNL segment]れ、ユーザーインターフェイスの [セグメント](../features/segments/segment-summary-view.md) ページに表示されます。 |
| [!DNL csegID] | [!DNL Legacy Segment ID]をインストールします。This ID uniquely identifies segments in the [!DNL Audience Manager] environment. | `741232` | A [!UICONTROL Legacy Segment ID] is assigned to each segment, and visible in the user interface, in the [Segments](../features/segments/segment-summary-view.md) page. |
| [!DNL destID] | [!UICONTROL Destination ID]をインストールします。は、 [!UICONTROL Destination ID] 環境内で一意 [!DNL destinations][!DNL Audience Manager] に識別します。 ユーザーインターフェイスの各ユーザー [!DNL destination] にIDが割り当てられます。 | `2523` | 各 [!UICONTROL Destination ID] に割り当てら [!DNL destination]れ、ユーザーインターフェイスの [宛先](../features/destinations/destinations-home.md) ページに表示されます。 |
| [!DNL DPID] | [!UICONTROL Data Source ID] (別名 [!UICONTROL Data Provider ID])。 は、IDまた [!UICONTROL Data Source ID] はの名前空間で [!DNL traits]す。 ユーザーインターフェイスの各 [!DNL data source] （データプロバイダー）にIDが割り当てられます。 | [!DNL DCS] 呼び出しでは、`dpid` の前に `d_` プレフィックスが付きます。<br>例：`d_dpid=39217`。 | 各 [!UICONTROL Data Provider ID] に割り当てら [!DNL data source]れ、ユーザーインターフェイスの [データソース](../features/datasources-list-and-settings.md) ページに表示されます。 |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]またはとも呼ば [!DNL CRM ID] れ [!UICONTROL Cross-Device ID]ます。 サードパーティ ID。[!DNL CRM] システムのエンドユーザーを識別するための ID です。You can sync [!DNL DPUUIDs] with [!DNL Audience Manager] [!DNL UUIDs] and you can sync [!DNL DPUUIDs] from your different [!UICONTROL Data Sources] ([!DNL DPIDs]) in the ID synchronization process. | In [!DNL DCS] callls, `dpuuid` is preceded by the `d_` prefix. <br>例：`d_dpuuid=2132-3423vn-343fds-3432r`。 | You can filter [!DNL traits] by [!UICONTROL Cross-Device ID] when creating [Look-Alike Models](../features/algorithmic-models/create-model.md), and [building segments](../features/segments/segment-builder.md). また、[特性に関する一般レポート](../reporting/general-reports.md)および[特性に関するトレンドレポート](../reporting/trend-reports.md)を実行中に、[!UICONTROL Cross-Device ID] で結果をフィルタリングできます。 |
| [!DNL CRM ID] | `DPUUID` を参照してください。 | `DPUUID` を参照してください。 | `DPUUID` を参照してください。 |
| [!DNL CID]、[!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. [!DNL CID] と [!DNL CID_IC] のキーと価のペアは、[!DNL DPID] と [!DNL DPUUID] を置き換えます。[!DNL DPID] および [!DNL DPUUID] と同じ機能ですが、1 つのキーと値のペアにデータプロバイダー ID とユーザー ID（または統合コード）が含まれるので、より効率的です。 | In [!DNL DCS] calls, these IDs are preceded by the `d_` prefix. <br>例：`d_cid_ic=39217_myIntegrationCode`。 | `DPID` と `DPUUID` を参照してください。 |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]をインストールします。各ハードウェアデバイスに一意の ID で、広告目的で使用されます。通常は、デバイスの製造元またはデバイスのオペレーティングシステムにより設定されます。 | 詳しくは、[グローバルデバイス ID](#global-device-ids) を参照してください。 |  |

## [!DNL Global Device IDs] {#global-device-ids}

グローバルデバイス ID は、デバイスの製造元またはオペレーティングシステムが提供する、各デバイスに固有のデバイス広告 ID です。次の表に、これらの ID の内容と形式を示します。For more information about global device IDs and how to use them in [!DNL Audience Manager], read [Global Data Sources](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | 名前と説明 | 例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID はモバイルデバイス識別子で、デバイスの製造元により設定されます。これらの ID は [!DNL iOS] オペレーティングシステムを使用するデバイスを表します。 | 形式は厳密に 32 文字の大文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`AEBE52E7-03EE-455A-B3C4-E57283966239`。 |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID] はモバイルデバイス識別子で、Android デバイスの製造元により設定されます。これらの ID は [!DNL Android] オペレーティングシステムを使用するデバイスを表します。 | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`e4fe9bde-caa0-47b6-908d-ffba3fa184f2`。 |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] は、[!DNL Roku] ストリーミングデバイスを表します。 | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`fcb2a29c-315a-5e6b-bcfd-d889ba19aada`。 |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID] は、デバイスごと、ユーザーごとに [!DNL Windows 10] で生成されるデバイス識別子です。 | [!DNL MAID] は英数字の形式です。 |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] は、 [!DNL Samsung] Smart TVが提供するデバイス識別子です。 | [!DNL Samsung] [!DNL TIFA] IDは英数字の文字列として形式設定されます。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | [!DNL Fire OS] オペレーティングシステムを実行しているデバイスを表すデバイス識別子。 | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`df07c7dc-cea7-4a89-b328-810ff5acb15d` |