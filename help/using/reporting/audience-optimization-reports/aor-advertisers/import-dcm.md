---
description: GoogleキャンペーンマネージャーのデータファイルをAudience Managerに取り込むためのGoogleグループを設定します。 この節の内容は、統合プロセスの概要と、使い始める際に役立つGoogleキャンペーンマネージャーのリソースへのリンクを示しています。
seo-description: GoogleキャンペーンマネージャーのデータファイルをAudience Managerに取り込むためのGoogleグループを設定します。 この節の内容は、統合プロセスの概要と、使い始める際に役立つGoogleキャンペーンマネージャーのリソースへのリンクを示しています。
seo-title: Google キャンペーンマネージャーデータファイルを Audience Manager にインポート
solution: Audience Manager
title: Google キャンペーンマネージャーデータファイルを Audience Manager にインポート
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 62%

---


# Google キャンペーンマネージャーデータファイルを Audience Manager にインポート {#import-dcm-data-files-into-audience-manager}

Set up a [!DNL Google] group to bring your [!DNL Google Campaign Manager] data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to [!DNL Google Campaign Manager] resources to help you get started.

## 統合の概要

[!DNL Google Campaign Manager] は、[!DNL Google]（DFA）に対する [!DNL DoubleClick for Advertisers] の置き換えです。Similar to DFA, [!DNL Google Campaign Manager] customers can import, view, and work with their data in [!DNL Audience Manager]. ただし、[!DNL Audience Manager] は [!UICONTROL Data Transfer] ファイルと [!UICONTROL Match Table] ファイルに直接アクセスしてインポートすることはできません。これらのファイルをインポートする場合、顧客側での努力が必要になります。

その設定手順については、[DoubleClick Campaign Manager ヘルプ](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)で詳細に説明しています。また、基本的な手順については以下で説明しています。

>[!CAUTION]
>
>[!DNL Google Campaign Manager] データファイルには、すべての広告主やクライアントのデータが含まれています。特定のクライアントを省略する必要がある場合、このファイルを [!DNL Audience Manager] で使用できるようにする前にこのファイルを編集する必要があります。

## データ転送の頻度と可用性

[!DNL Audience Manager] は毎日データを確認して転送します。データが [!DNL Audience Manager] で使用できるようになるのは通常 24 時間後です。

## 手順

1. [グループを作成](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456)します。

   Groups control access to your [!DNL Google Campaign Manager] data. 最終的に、[!DNL Audience Manager] をこのグループに招待して追加します。

1. [ Google Cloud Storage のステータスを確認](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)します。

   Google Cloud Storage には、[!UICONTROL Data Transfer] と [!UICONTROL Match Tables] が格納されるデータバケットがあります。バケットを設定するか、新しいグループが既存のデータストレージバケットにアクセスできるようにする必要があります。

1. [ データファイルの URL を取得](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456)します。

   Work with your [!DNL Google Campaign Manager] Account Manager or Platform Solutions Consultant. データファイルの URL を確認してください。[!DNL Google] は将来のリリースでバケットの形式やファイル名を変更する場合があります。Again, work with your [!DNL Google Campaign Manager] Account Manager to make sure you&#39;re using the right formats.

1. [ バケットの権限を設定](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)します。

   [!DNL Cloud Storage Manager] では、データの共有とバケットへのアクセスを制御できます。自分のグループに、[!UICONTROL Data Transfer] ファイルと [!UICONTROL Match Table] ファイルを含むバケットへの読み取りアクセス権を付与します。

1. [ データの共有を設定](https://support.google.com/dcm/partner/answer/6206106?hl=ja)します。

   Shared [!DNL Google Campaign Manager] user IDs are encrypted to protect privacy. 暗号化の結果、Data Transfer ファイルの末尾に `PartnerId1` と `PartnerId2` の 2 つの列が追加されます。これらの列には、これらのファイルを受け取る会社ごとに特有のユーザー ID がエンコードされて格納されます。

   [!DNL Audience Manager] は、認証されたサードパーティとして データを受け取ることはできますが、ID をデコードすることはできません[!DNL Google Campaign Manager]ただし、エンコードされた ID を [!DNL Audience Manager] 側の ID と照合することはできます。そのため、ユーザーの照合と同期を確実かつ正確におこなうことができます。

   >[!NOTE]
   >You cannot import [!DNL Google Campaign Manager] files into [!DNL Audience Manager] if you&#39;re already sharing data with 2 other third-party partners.

1. [!DNL Audience Manager]をグループに参加するよう招待します。

   グループを作成して、データバケットへのアクセス権を付与したら、[!DNL Audience Manager] をそのグループに参加するよう招待します。DFA-AAM@adobe.com に招待の電子メールを送信します。手順 3 のデータファイル URL を必ずその中に入れてください。当社の内部チームが招待を受け取った後にアクセス権を確認します。1. Set up two data sources for [!DNL Google Campaign Manager] data in the [!DNL Audience Manager] User Interface.

   データソース `Advertiser Analytics: DCM Platform` と `Advertiser Analytics: AAM+DCM Platform` の名前を入力します。「[Create Data Sources](../../../features/manage-datasources.md#create-data-source)」ワークフローで、ID タイプを「`Cookie`」に設定します。2 つの新しいデータソースの ID を、当社の内部チームと共有します。

1. You can easily create traits from the [!DNL Google Campaign Manager] files you import into [!DNL Audience Manager]. [実用的なログファイル](../../../integration/media-data-integration/actionable-log-files.md)を参照し、[!DNL Audience Manager] コンサルタントまたはカスタマーケアにこの機能を有効にするよう依頼してください。
