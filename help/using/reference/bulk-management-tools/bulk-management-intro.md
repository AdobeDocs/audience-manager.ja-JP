---
description: 一括管理ツールを使用すると、複数のオブジェクトを一度に 1 回の操作で作成および管理できます。一括管理ツールを使用して、データソース、派生シグナル、宛先、フォルダー、セグメントおよび特性を処理できます。
keywords: baaam;BAAAM;download baaam
seo-description: 一括管理ツールを使用すると、複数のオブジェクトを一度に 1 回の操作で作成および管理できます。一括管理ツールを使用して、データソース、派生シグナル、宛先、フォルダー、セグメントおよび特性を処理できます。
seo-title: 一括管理の概要
solution: Audience Manager
title: 一括管理の概要
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 100%

---


# 一括管理の概要 {#getting-started-with-bulk-management}

[!DNL Bulk Management Tools] を使用すると、複数のオブジェクトを一度に 1 回の操作で作成および管理できます。[!DNL Bulk Management Tools] を使用して、[!UICONTROL data sources]、[!UICONTROL derived signals]、[!UICONTROL destinations]、[!UICONTROL folders]、[!UICONTROL models]、[!UICONTROL segments]、および [!UICONTROL traits] を操作できます。

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[!DNL Audience Manager] インターフェイスで割り当てられる [RBAC グループ権限](../../features/administration/administration-overview.md)は、[!UICONTROL Bulk Management Tools] に対しても適用されます。

## 概要 {#overview}

この機能では、[!DNL Microsoft Excel] スプレッドシートのマクロを使用して、[!DNL Audience Manager] API の認証済みの安全な呼び出しをおこないます。API には、一括変更をおこなうためのメソッドおよびサービスが用意されています。これを使用するにあたって、コーディングや API の使用方法についての知識は必要ありません。ワークシートには特定の一括変更関数を実行するための列見出しとタブがあります。一括変更を実行するには単に、事前定義済みのヘッダーを特定のワークシートに追加し、一括変更する情報を指定し、アクションボタンをクリックします。後はワークシートと API が処理してくれます。

## ダウンロード {#download}

**[こちら](assets/BAAAM_V2_20200502.xlsm)** で最新のワークシートをダウンロードします。

## 前提条件 {#prereqs}

[!DNL Bulk Management Tools] を使用するには、以下が必要です。

* [!DNL Experience Cloud] へのログイン。お客様が既にお持ちの資格情報です。
* [!DNL Bulk Management Tools] ワークシート。最新版を入手するには、[ワークシートをダウンロード](assets/BAAAM_V2_20200502.xlsm)してください。
* [!DNL Microsoft Excel][!DNL macOS] または 64 ビット版 [!DNL Microsoft Windows] で実行している最新バージョンの [!DNL Microsoft Excel] を使用することをお勧めします。
* ワークシートを開く場合は、[!DNL Bulk Management Tools] で&#x200B;**マクロを有効にする**&#x200B;必要があります。

## 認証の要件およびオプション {#auth-reqs}

一括変更には認証が必要となります。操作を開始する前に、ログインする必要があります。ワークシートでは API 呼び出しがおこなわれるので、ユーザーアカウントで認証するよう設定する必要はありません。

**API 認証の要件**

2019 年 10 月にリリースされた一括管理ツールの 2 つ目のバージョンである [!DNL Bulk Management Tools] は、認証プロセスを簡素化します。このバージョンの認証手順を以下に示します。

1. スプレッドシートを開き、**[!UICONTROL Config]** シートに移動します。
2. シートに示されている手順に従います。
   ![](assets/baaam-authentication.png)
3. 手順が完了すると、一括変更をおこなう権限が与えられます。

一括変更をおこなう場合、変更をおこなう権限があることを確認する必要がありますが、API 認証は自動的におこなわれます。

**ドメイン認証のオプション**

ドメイン認証では、一括リクエストをテストすることも、直接実稼動アカウントに適用することもできます。テスト環境で一括変更をおこなっても、実稼動アカウントには反映されません。実稼動アカウントへの変更は即座に反映されます。一括管理シートを使用すると、次の環境で作業できます。

* ベータ
* 実稼動

## アクションおよび操作 {#actions-ops}

[!UICONTROL Bulk Management Tools]ワークシートは、認証ボタン、アクションタブ、アクションボタンおよび「**[!UICONTROL Headers]**」タブで構成されています。「**[!UICONTROL Headers]**」タブには、アクションタブで使用される整形済みの列ヘッダーがあります。アクションタブには選択した一括操作を実行するためのマクロが用意されています。一括操作を実行するには、該当するアクションタブにヘッダーをまとめてコピーし、ヘッダーデータを入力し、アクションボタンをクリックします。

[認証](#auth-reqs)後、アクションボタンをクリックして開始します。

![](assets/baaam-worksheet.png)

次の表は、実行できる操作、および[!UICONTROL Bulk Management Tools]ワークシートを使用して操作できる項目を示したものです。

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> アクション </th> 
   <th colname="col2" class="entry"> オブジェクト </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>一括アクションはワークシートの一番下のタブに表示され、次の項目などがあります。 </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Requests </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Update </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Create </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Estimate </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Delete </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>一括変更できるオブジェクトは、「<b><span class="uicontrol">Headers</span></b>」タブに配置されており、次の項目などがあります。 </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> データソース</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> 派生シグナル</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> 宛先</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> モデル</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> 特性フォルダー</a>およびセグメントフォルダー </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> セグメント</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> 特性</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**一括操作の例**

例えば、複数の特性を一度に作成する方法を見てみましょう。一括操作で複数の特性を作成するには、次の手順に従います。

1. 「**[!UICONTROL Headers]**」タブをクリックし、「[!UICONTROL Create a Trait]」オプション配下のすべてのラベルをコピーします。
2. 「**[!UICONTROL Create]**」タブをクリックし、1 行目の列 A を先頭にラベルをペーストします。
3. 各列ヘッダーに関する情報を入力し、「**[!UICONTROL Create Traits]**」をクリックします。このアクションにより、認証を確認するプロンプトが表示されます。一括ジョブは、認証を確認した後で実行されます。ワークシートの左下隅に表示されるジョブステータス通知を確認してください。


>[!NOTE]
>
>大量のリクエストを処理する場合、ワークシートが低速になり、非アクティブであるように見えることがあります。その場合、そのままにしておきます。一括要求が完了すると、ワークシートは反応するようになります。ワークシートが長時間反応しない場合、[トラブルシューティングのセクション](../../reference/bulk-management-tools/bulk-troubleshooting.md)を参照してください。

