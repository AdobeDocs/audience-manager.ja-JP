---
description: DoubleClick Campaign Manager（DCM）データファイルを Audience Manager に取り込むには、Google グループをセットアップします。この節では、統合プロセスの概要を説明し、DCM の導入時に役立つリソースへのリンクを提供します。
seo-description: DoubleClick Campaign Manager（DCM）データファイルを Audience Manager に取り込むには、Google グループをセットアップします。この節では、統合プロセスの概要を説明し、DCM の導入時に役立つリソースへのリンクを提供します。
seo-title: DCM データファイルを Audience Manager にインポート
solution: Audience Manager
title: DCM データファイルを Audience Manager にインポート
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Manager への DCM データファイルのインポート {#import-dcm-data-files-into-audience-manager}

DoubleClick Campaign Manager（DCM）データファイルを Audience Manager に取り込むには、Google グループをセットアップします。この節では、統合プロセスの概要を説明し、DCM の導入時に役立つリソースへのリンクを提供します。

## 統合の概要

DCM は、[!DNL DoubleClick for Advertisers]（DFA）に対する [!DNL Google] の置き換えです。DFA と同様に DCM の顧客は [!DNL Audience Manager] でデータのインポート、表示、操作ができます。But [!DNL Audience Manager] cannot directly access and import your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. これらのファイルをインポートする場合、顧客側での努力が必要になります。

その設定手順については、[DoubleClick Campaign Manager ヘルプ](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456)で詳細に説明しています。また、基本的な手順については以下で説明しています。

>[!CAUTION]
>
>DCM データファイルには、すべての広告主やクライアントのデータが含まれています。特定のクライアントを省略する必要がある場合、このファイルを [!DNL Audience Manager] で使用できるようにする前にこのファイルを編集する必要があります。

## データ転送の頻度と可用性

[!DNL Audience Manager] は毎日データを確認して転送します。データが [!DNL Audience Manager] で使用できるようになるのは通常 24 時間後です。

## 手順

1. [グループを作成](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456)します。

   グループにより、DCM データへのアクセスが制御されます。最終的に、[!DNL Audience Manager] をこのグループに招待して追加します。

1. [ Google Cloud Storage のステータスを確認](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456)します。

   Google Cloud Storage contains the data bucket that holds your [!UICONTROL Data Transfer] and [!UICONTROL Match Tables]. バケットを設定するか、新しいグループが既存のデータストレージバケットにアクセスできるようにする必要があります。

1. [ データファイルの URL を取得](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456)します。

   DCM アカウントマネージャーまたはプラットフォームソリューションコンサルタントにお問い合わせのうえ、データファイルの URL を確認してください。[!DNL Google] は将来のリリースでバケットの形式やファイル名を変更する場合があります。これも DCM アカウントマネージャーにお問い合わせのうえ、正しい形式を使用しているか確認してください。

1. [ バケットの権限を設定](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)します。

   [!DNL Cloud Storage Manager] では、データの共有とバケットへのアクセスを制御できます。Give your group read access to the bucket that contains your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files.

1. [ データの共有を設定](https://support.google.com/dcm/partner/answer/6206106?hl=en)します。

   プライバシー保護のため、共有 DCM ユーザー ID は暗号化されます。暗号化の結果、Data Transfer ファイルの末尾に `PartnerId1` と `PartnerId2` の 2 つの列が追加されます。これらの列には、これらのファイルを受け取る会社ごとに特有のユーザー ID がエンコードされて格納されます。

   [!DNL Audience Manager] は、認証されたサードパーティとして DCM データを受け取ることはできますが、ID をデコードすることはできませんただし、エンコードされた ID を [!DNL Audience Manager] 側の ID と照合することはできます。そのため、ユーザーの照合と同期を確実かつ正確におこなうことができます。

   >[!NOTE]
   >ただし、他の 2 件のサードパーティパートナーと既にデータを共有している場合、DCM ファイルを [!DNL Audience Manager] にインポートすることはできません。

1. [!DNL Audience Manager]をグループに参加するよう招待します。

   グループを作成して、データバケットへのアクセス権を付与したら、[!DNL Audience Manager] をそのグループに参加するよう招待します。DFA-AAM@adobe.com に招待の電子メールを送信します。手順 3 のデータファイル URL を必ずその中に入れてください。当社の内部チームが招待を受け取った後にアクセス権を確認します。1. [!DNL Audience Manager] ユーザーインターフェイスで DCM データの 2 つのデータソースを設定します。

   データソース `Advertiser Analytics: DCM Platform` と `Advertiser Analytics: AAM+DCM Platform` の名前を入力します。「[Create Data Sources](../../../features/manage-datasources.md#create-data-source)」ワークフローで、ID タイプを「`Cookie`」に設定します。2 つの新しいデータソースの ID を、当社の内部チームと共有します。

1. [!DNL Audience Manager] にインポートした DCM ファイルから、簡単に特性を作成できます。[実用的なログファイル](../../../integration/media-data-integration/actionable-log-files.md)を参照し、[!DNL Audience Manager] コンサルタントまたはカスタマーケアにこの機能を有効にするよう依頼してください。
