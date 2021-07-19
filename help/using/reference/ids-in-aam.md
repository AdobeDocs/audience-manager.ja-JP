---
description: Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Adobe Audience Manager の ID の詳細なリストについては、このドキュメントを参照してください。
seo-title: Audience Manager で使用される ID の一覧
solution: Audience Manager
title: Audience Manager で使用される ID の一覧
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: リファレンス
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 100%

---

# [!DNL Audience Manager]で使用される ID の一覧  {#index-of-ids-in-audience-manager}

## 概要 {#overview}

[!DNL Audience Manager] は、複数の ID を使用して、送信するデータを識別および管理します。[!DNL Audience Manager] ID の完全なリストと、それらで使用する必要のあるプレフィックスの例については、この記事を参照してください。

## ID プレフィックス {#prefixing}

これらの ID のほとんどはスタンドアロン名で参照できますが、[!DNL DCS] 呼び出しを通じてデータを渡す際には様々なプレフィックスと共に使用されます。これらの ID には、ユーザーに公開されずに [!DNL Audience Manager] で使用されるものと、ユーザーインターフェイス（UI）に表示されるものがあります。

以下の例で使用されるプレフィックスについて詳しくは、[DCS API 呼び出しでサポートされる属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)を参照してください。

## [!DNL Audience Manager] ID のリスト {#id-list}

| ID | 名前と説明 | 使用例 | ユーザーインターフェイスの場所 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID] は、[!UICONTROL Device ID] とも呼ばれます。数値型で 38 桁のデバイス ID。[!DNL Audience Manager] はこの値を、操作するデバイスのそれぞれに関連付けます。[!DNL Audience Manager]UI で一意のユーザーのメンションが表示される場合は常に、この ID を考慮してください。Audience Manager はこの ID を、「`demdex.net`」サードパーティドメインの [!DNL cookie] として保存します。 | [!DNL DCS] 呼び出しでは、`uuid` の前に `d_` プレフィックスが付きます。<br>例：`d_uuid = 07955261652886032950143702505894272138` | [類似（look-alike）モデル](../features/algorithmic-models/create-model.md)をの作成時や[セグメントの作成](../features/segments/segment-builder.md)時には、[!UICONTROL Device ID] で[!DNL traits]をフィルタリングできます。また、[特性に関する一般レポート](../reporting/general-reports.md)および[特性に関するトレンドレポート](../reporting/trend-reports.md)を実行中に、[!UICONTROL Device ID] で結果をフィルタリングできます。 |
| [!DNL ImsOrgId] | [!DNL Organization ID]をインストールします。会社が [!DNL Experience Cloud] アカウントに新規登録する際に生成される ID です。 | `5DC5123F5245B1D20A490D46@AdobeOrg` | [!DNL Audience Manager] ユーザーインターフェイスには表示されません。会社の [!DNL Organization ID] の検索方法については、[組織 ID の検索](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)を参照してください。 |
| [!DNL PID] | [!DNL Partner ID]をインストールします。[!DNL PID] は、[!DNL Audience Manager] における会社 ID です。Audience Manager は [!DNL imsOrgId] を [!DNL PID] に関連付けます。 | `1352` | [!DNL Audience Manager] ユーザーインターフェイスには表示されません。 |
| [!DNL ECID]、[!DNL MID] | [!DNL Experience Cloud] ID。[!DNL Experience Cloud] ID（、レ従来の略語である[!DNL ECID]、レ従来の略語である [!DNL MID]、または[!DNL MCID]）は、[!DNL Organization ID]、[!DNL Audience Manager]、および [!UICONTROL Unique User ID] から数学的に導き出されます。これらの ID が変わらない限り、特定のユーザーに関する正しい [!DNL ECID] を生成できるかどうかは、単純に計算上の問題になります。[!DNL Organization ID] と [!DNL Audience Manager] [!DNL UUID] が同じであれば、いつでも同じ [!DNL ECID] 値が得られます。[!DNL ECID] について詳しくは、[Cookies と Experience Cloud ID](https://docs.adobe.com/content/help/ja-JP/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) のドキュメントを参照してください。 | `mid = 08382830887934830189014177072406221371` | [!DNL Audience Manager] ユーザーインターフェイスには表示されません。 |
| [!DNL SID] | [!UICONTROL Trait ID]をインストールします。[!UICONTROL Trait ID] は、[!DNL Audience Manager] 環境内で一意に [!DNL traits] を識別します。 | [!DNL DCS] 呼び出しでは、`SID` の前に `d_` プレフィックスが付きます。<br>例：`d_sid=289983`。 | [!UICONTROL Trait ID] は各[!DNL trait]に割り当てられ、[特性](../features/traits/trait-details-page.md)ページのユーザーインターフェイスに表示されます。 |
| [!DNL SID] | [!UICONTROL Segment ID]をインストールします。[!UICONTROL Segment ID] は、[!DNL Audience Manager] 環境内で一意に [!DNL segments] を識別します。 | [!DNL DCS] 呼び出しでは、`SID` の前に `d_` プレフィックスが付きます。<br>例：`d_sid=4798574`。 | [!UICONTROL Segment ID] は各[!DNL segment]に割り当てられ、[セグメント](../features/segments/segment-summary-view.md)ページのユーザーインターフェイスに表示されます。 |
| [!DNL csegID] | [!DNL Legacy Segment ID]をインストールします。この ID は、[!DNL Audience Manager] 環境内のセグメントを一意に識別します。 | `741232` | [!UICONTROL Legacy Segment ID] は各セグメントに割り当てられ、[特性](../features/segments/segment-summary-view.md)ページのユーザーインターフェイスに表示されます。 |
| [!DNL destID] | [!UICONTROL Destination ID]をインストールします。[!UICONTROL Destination ID] は、[!DNL Audience Manager] 環境内で一意に [!DNL destinations] を識別します。ユーザーインターフェイスの各[!DNL destination]に、ID が割り当てられます。 | `2523` | [!UICONTROL Destination ID] は各[!DNL destination]に割り当てられ、[宛先](../features/destinations/destinations-home.md)ページのユーザーインターフェイスに表示されます。 |
| [!DNL DPID] | [!UICONTROL Data Source ID]（別名 [!UICONTROL Data Provider ID]）。[!UICONTROL Data Source ID] は、ID または[!DNL traits]用の名前空間です。ユーザーインターフェイスの各[!DNL data source]（データプロバイダー）に、ID が割り当てられます。 | [!DNL DCS] 呼び出しでは、`dpid` の前に `d_` プレフィックスが付きます。<br>例：`d_dpid=39217`。 | [!UICONTROL Data Provider ID] は各[!DNL data source]に割り当てられ、[データソース](../features/datasources-list-and-settings.md)ページのユーザーインターフェイスに表示されます。 |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID] は、[!DNL CRM ID] または [!UICONTROL Cross-Device ID] とも呼ばれます。サードパーティ ID。[!DNL CRM] システムのエンドユーザーを識別するための ID です。[!DNL DPUUIDs] を [!DNL Audience Manager] の [!DNL UUIDs] と同期したり、ID 同期プロセスで別の[!UICONTROL Data Sources]（[!DNL DPIDs]）の [!DNL DPUUIDs] を同期したりできます。 | [!DNL DCS] 呼び出しでは、`dpuuid` の前に `d_` プレフィックスが付きます。<br>例：`d_dpuuid=2132-3423vn-343fds-3432r`。 | [類似（look-alike）モデル](../features/algorithmic-models/create-model.md)をの作成時や[セグメントの作成](../features/segments/segment-builder.md)時には、[!UICONTROL Cross-Device ID] で[!DNL traits]をフィルタリングできます。また、[特性に関する一般レポート](../reporting/general-reports.md)および[特性に関するトレンドレポート](../reporting/trend-reports.md)を実行中に、[!UICONTROL Cross-Device ID] で結果をフィルタリングできます。 |
| [!DNL CRM ID] | `DPUUID` を参照してください。 | `DPUUID` を参照してください。 | `DPUUID` を参照してください。 |
| [!DNL CID]、[!DNL CID_IC] | [!UICONTROL Customer ID]、[!UICONTROL Customer ID Integration Code]。[!DNL CID] と [!DNL CID_IC] のキー値ペアは、[!DNL DPID] と [!DNL DPUUID] を置き換えます。[!DNL DPID] および [!DNL DPUUID] と同じ機能ですが、1 つのキー値ペアにデータプロバイダー ID とユーザー ID（または統合コード）が含まれるので、より効率的です。 | [!DNL DCS] 呼び出しでは、これらの ID の前に `d_` プレフィックスが付きます。<br>例：`d_cid_ic=39217_myIntegrationCode`。 | `DPID` と `DPUUID` を参照してください。 |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]をインストールします。各ハードウェアデバイスに一意の ID で、広告目的で使用されます。通常は、デバイスの製造元またはデバイスのオペレーティングシステムにより設定されます。 | 詳しくは、[グローバルデバイス ID](#global-device-ids) を参照してください。 |  |

## [!DNL Global Device IDs] {#global-device-ids}

グローバルデバイス ID は、デバイスの製造元またはオペレーティングシステムが提供する、各デバイスに固有のデバイス広告 ID です。次の表に、これらの ID の内容と形式を示します。グローバルデバイス ID の概要、および [!DNL Audience Manager] での使用方法について詳しくは、[グローバルデータソース](/help/using/features/global-data-sources.md)を参照してください。

| ID | [!DNL Global Data Source ID] | 名前と説明 | 例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID はモバイルデバイス識別子で、デバイスの製造元により設定されます。これらの ID は [!DNL iOS] オペレーティングシステムを使用するデバイスを表します。 | 形式は厳密に 32 文字の大文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`AEBE52E7-03EE-455A-B3C4-E57283966239`。 |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID] はモバイルデバイス識別子で、Android デバイスの製造元により設定されます。これらの ID は [!DNL Android] オペレーティングシステムを使用するデバイスを表します。 | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`e4fe9bde-caa0-47b6-908d-ffba3fa184f2`。 |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] は、[!DNL Roku] ストリーミングデバイスを表します。 | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`fcb2a29c-315a-5e6b-bcfd-d889ba19aada`。 |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID] は、デバイスごと、ユーザーごとに [!DNL Windows 10] で生成されるデバイス識別子です。 | [!DNL MAID] は英数字の形式です。 |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] は、[!DNL Samsung] スマートテレビが提供するデバイス識別子です。 | [!DNL Samsung] [!DNL TIFA] ID は英数字の形式です。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | [!DNL Fire OS] オペレーティングシステムを実行しているデバイスを表すデバイス識別子。 | 形式は厳密に 32 文字の小文字の 16 進数で、ハイフンで区切られた 5 つのグループとして表示されます。形式は 8-4-4-4-12 で、合計 36 文字です。<br>例：`df07c7dc-cea7-4a89-b328-810ff5acb15d` |
