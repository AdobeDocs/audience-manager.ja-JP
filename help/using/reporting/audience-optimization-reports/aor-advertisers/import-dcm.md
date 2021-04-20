---
description: Gogle グループを設定して、Google Campaign Manager データファイルを Audience Manager に取り込みます。この節では、統合プロセスの概要を説明し、Google Campaign Manager の導入時に役立つリソースへのリンクを提供します。
seo-description: Gogle グループを設定して、Google Campaign Manager データファイルを Audience Manager に取り込みます。この節では、統合プロセスの概要を説明し、Google Campaign Manager の導入時に役立つリソースへのリンクを提供します。
seo-title: Google キャンペーンマネージャーデータファイルを Audience Manager に読み込む
solution: Audience Manager
title: Google キャンペーンマネージャーデータファイルを Audience Manager に読み込む
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 100%

---

# Google キャンペーンマネージャーデータファイルを Audience Manager に読み込む {#import-dcm-data-files-into-audience-manager}

[!DNL Google] グループを設定して [!DNL Google Campaign Manager] データファイルを Audience Manager に取り込みます。この節では、統合プロセスの概要を説明し、[!DNL Google Campaign Manager] の導入時に役立つリソースへのリンクを提供します。

## 統合の概要

[!DNL Google Campaign Manager] は、[!DNL Google]（DFA）に対する [!DNL DoubleClick for Advertisers] の置き換えです。DFA と同様に [!DNL Google Campaign Manager] ユーザーは [!DNL Audience Manager] でデータの読み込み、表示、操作ができます。ただし、[!DNL Audience Manager] は [!UICONTROL Data Transfer] ファイルと [!UICONTROL Match Table] ファイルに直接アクセスしてインポートすることはできません。これらのファイルをインポートする場合、顧客側での努力が必要になります。

その設定手順については、[DoubleClick Campaign Manager ヘルプ](https://support.google.com/dcm/partner/answer/2941575?hl=ja&amp;ref_topic=6107456)で詳細に説明しています。また、基本的な手順については以下で説明しています。

>[!CAUTION]
>
>[!DNL Google Campaign Manager] データファイルには、すべての広告主やクライアントのデータが含まれています。特定のクライアントを省略する必要がある場合、このファイルを [!DNL Audience Manager] で使用できるようにする前にこのファイルを編集する必要があります。

## データ転送の頻度と可用性

[!DNL Audience Manager] は毎日データを確認して転送します。データが [!DNL Audience Manager] で使用できるようになるのは通常 24 時間後です。

## 手順

1. [グループを作成](https://support.google.com/dcm/partner/answer/3370419?hl=ja&amp;ref_topic=6107456)します。

   グループは、[!DNL Google Campaign Manager] データへのアクセスを制御します。最終的に、[!DNL Audience Manager] をこのグループに招待して追加します。

1. [ Google Cloud Storage のステータスを確認](https://support.google.com/dcm/partner/answer/3370481?hl=ja&amp;ref_topic=6107456)します。

   Google Cloud Storage には、[!UICONTROL Data Transfer] と [!UICONTROL Match Tables] が格納されるデータバケットがあります。バケットを設定するか、新しいグループが既存のデータストレージバケットにアクセスできるようにする必要があります。

1. [ データファイルの URL を取得](https://support.google.com/dcm/partner/answer/3370482?hl=ja&amp;ref_topic=6107456)します。

   [!DNL Google Campaign Manager] アカウントマネージャーまたはプラットフォームソリューションコンサルタントにお問い合わせのうえ、データファイルの URL を確認してください。[!DNL Google] は将来のリリースでバケットの形式やファイル名を変更する場合があります。これも [!DNL Google Campaign Manager] アカウントマネージャーにお問い合わせのうえ、正しい形式を使用しているか確認してください。

1. [ バケットの権限を設定](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)します。

   [!DNL Cloud Storage Manager] では、データの共有とバケットへのアクセスを制御できます。自分のグループに、[!UICONTROL Data Transfer] ファイルと [!UICONTROL Match Table] ファイルを含むバケットへの読み取りアクセス権を付与します。

1. [ データの共有を設定](https://support.google.com/dcm/partner/answer/6206106?hl=ja)します。

   プライバシー保護のため、共有 [!DNL Google Campaign Manager] ユーザー ID は暗号化されます。暗号化の結果、Data Transfer ファイルの末尾に `PartnerId1` と `PartnerId2` の 2 つの列が追加されます。これらの列には、これらのファイルを受け取る会社ごとに特有のユーザー ID がエンコードされて格納されます。

   [!DNL Audience Manager] は、認証されたサードパーティとして データを受け取ることはできますが、ID をデコードすることはできません[!DNL Google Campaign Manager]ただし、エンコードされた ID を [!DNL Audience Manager] 側の ID と照合することはできます。そのため、ユーザーの照合と同期を確実かつ正確におこなうことができます。

   >[!NOTE]
   >ただし、他の 2 件のサードパーティパートナーと既にデータを共有している場合、[!DNL Google Campaign Manager] ファイルを [!DNL Audience Manager] に読み込むことはできません。

1. [!DNL Audience Manager]をグループに参加するよう招待します。

   グループを作成して、データバケットへのアクセス権を付与したら、[!DNL Audience Manager] をそのグループに参加するよう招待します。DFA-AAM@adobe.com に招待の電子メールを送信します。手順 3 のデータファイル URL を必ずその中に入れてください。当社の内部チームが招待を受け取った後にアクセス権を確認します。1. [!DNL Audience Manager] ユーザーインターフェイスで [!DNL Google Campaign Manager] データの 2 つのデータソースを設定します。

   データソース `Advertiser Analytics: DCM Platform` と `Advertiser Analytics: AAM+DCM Platform` の名前を入力します。「[Create Data Sources](../../../features/manage-datasources.md#create-data-source)」ワークフローで、ID タイプを「`Cookie`」に設定します。2 つの新しいデータソースの ID を、当社の内部チームと共有します。

1. [!DNL Audience Manager] に読み込んだ [!DNL Google Campaign Manager] ファイルから、簡単に特性を作成できます。[アクションにつながるログファイル](../../../integration/media-data-integration/actionable-log-files.md)を参照し、[!DNL Audience Manager] コンサルタントまたはカスタマーケアにこの機能を有効にするよう依頼してください。
