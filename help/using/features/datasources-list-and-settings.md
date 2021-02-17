---
description: 現在設定されているデータソースの一覧表示、新規データソースの追加、既存データソースの編集について説明します。
seo-description: 現在設定されているデータソースの一覧表示、新規データソースの追加、既存データソースの編集について説明します。
seo-title: データソースリストと設定
solution: Audience Manager
title: データソースリストと設定
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 100%

---


# [!UICONTROL Data Sources] リストと設定 {#data-sources-list-and-settings}

現在設定されている[!UICONTROL data sources]のリストの表示、新しい[!UICONTROL data sources]の追加、既存の[!UICONTROL data sources]編集を行います。

また、[!DNL API] メソッドを使用して[!UICONTROL data sources]を管理することもできます。詳しくは、[データソース API メソッド](../api/rest-api-main/aam-api-data-sources.md)を参照してください。

## [!UICONTROL Data Sources]リスト表示 {#list-view}

[!UICONTROL Data Sources] ダッシュボードは、データソースを管理するための一元化されたワークスペースです。

[!UICONTROL Data Sources] ダッシュボード（**[!UICONTROL Audience Data]**／**[!UICONTROL Data Sources]**）には、以下をおこなうために役立つ機能およびツールが含まれています。

* 各データソースの説明やステータス、および [!UICONTROL Inbound]、[!UICONTROL Outbound]、両方、または [!UICONTROL Shared Provider]のどれかなど、既存のすべての[!UICONTROL data sources]を表示する。
* 名前による[!UICONTROL data sources]の検索。
* [!UICONTROL data sources]の作成、編集および削除。

## [!DNL Data Source]設定とメニューオプション {#settings-menu-options}

[!UICONTROL Data Source]管理インターフェイスの様々なセクションの設定によって、[!DNL data source]が特定され、データソースの使用および共有方法が決まり、[!UICONTROL Onboarding Status Report]でのエラー報告を有効にすることができます。

## [!DNL Data Source] 詳細 {#details}

テキストフィールドに加え、「[!UICONTROL Data Source Details]」セクションには、次のコントロールとオプションも含まれています。

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> メニューオプション </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID Type</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol">Cookie</span></b>：デバイスを識別する Cookie ID。これを選択するのは、データソースが Web ブラウザーである場合や、匿名データつまり特定の個人に関連付けることができないデータを扱う場合です。 </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol">Device Advertising ID</span></b>：モバイルデバイスの識別子。これを選択するのは、データソースがモバイルデバイスまたはインターネット対応デバイスである場合です。 </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol">Cross Device</span></b>：顧客が指定する認証済み ID。このオプションを選択するのは、次のものを作成する場合です。 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">クロスデバイス対応データソースと<span class="wintitle">プロファイル結合ルール</span>の構築 </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B"><a href="https://docs.adobe.com/content/help/ja-JP/device-co-op/using/about/overview.html" format="https" scope="external">Adobe Experience Cloud Device Co-op</a>、または <span class="keyword">Audience Manager</span> と統合されている別のサードパーティデバイスグラフで提供されるリンクを使用するデータソース。 </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID Definition</span></b> </p> </td> 
   <td colname="col2"> <p>「<b><span class="uicontrol">ID Definition</span></b>」のオプションは、<span class="keyword">Audience Manager</span> のユーザー ID（UUID）や、<span class="keyword">Adobe Experience Cloud Device Co-op</span>（または <span class="keyword">Audience Manager</span> と統合されている別のサードパーティデバイスグラフ）でリンクされる関連デバイスとデータソースとの関係を定義します。オプションは次のとおりです。 </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol">Person</span></b>： 1 人の個人を定義するのに使用される ID。この ID は複数の <span class="keyword">Audience Manager</span> ID にマッピングできます。 </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol">Household</span></b>：人々のグループを定義するのに使用される ID。この ID は複数の Audience Manager ID にマッピングできます。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[データ書き出しコントロール](../features/data-export-controls.md)は、[!UICONTROL data source] および [!UICONTROL destination] に適用できるオプションの分類ルールです。[!UICONTROL destination] へのデータ送信がデータのプライバシーや使用契約に違反する場合、データ送信を防止します。データ書き出しコントロールを使用しない場合は、「[!UICONTROL Data Export Controls]」セクションを省略してください。

>[!IMPORTANT]
>
>対応する書き出しラベルを[!UICONTROL destination]に設定しない限り、書き出し制限は機能しません。

オプションは次のとおりです。

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] 設定 {#data-source-settings}

「[!UICONTROL Data Source Settings]」セクションには、次のコントロールとオプションが含まれています。これらの設定の中には、データソースを変更するためのサブオプションやメニュー項目が追加されているものがあります。

### [!UICONTROL Inbound Data Source] 設定

データを受信するように設計されているデータソースの場合は、「**[!UICONTROL Inbound]**」チェックボックスを選択します。「**[!UICONTROL Inbound]**」チェックボックスを選択すると、次の 2 つのコントロールグループがさらに表示されます。

>[!NOTE]
>
>この **[!UICONTROL Inbound]** チェックボックスは、以下に説明する [!UICONTROL data source] コントロールの表示と非表示を切り替える目的でのみ有効です。この **[!UICONTROL Inbound]** オプションをオフにしても、データの取り込みには影響しません。オンボードされたデータは、このオプションがチェックされているかどうかに関係なく処理されます。

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> メニューオプション </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> IDタイプ</span></b> </p> </td> 
   <td colname="col2"> <p>「<b><span class="uicontrol">Inbound</span></b>」オプションには ID タイプが必要です。オプションは次のとおりです。 </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol">Customer ID</span></b>：受信データを顧客 ID で識別します。 </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol">Audience Manager ID</span></b>：受信データを <span class="keyword">Audience Manager</span> ID で識別します。 </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol">Experience Cloud ID</span></b>：受信データを <span class="keyword">Experience Cloud</span> ID で識別します。詳しくは、<a href="https://docs.adobe.com/content/help/ja-JP/id-service/using/intro/cookies.html" format="https" scope="external">Cookie と Experience Cloud ID</a>を参照してください。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> File Format Troubleshooting</span></b> </p> </td> 
   <td colname="col2"> <p>受信ファイル処理の問題をトラブルシューティングする必要がある場合は、「<b><span class="uicontrol">Enable file error sampling</span></b>」を選択します。ファイル形式および構文に関するエラーが表示されるエラーサンプルレポートが生成されるようになります。 </p> <p>詳しくは、<a href="../reporting/onboarding-status-report.md#onboarding-status-about">オンボーディングステータスレポート：概要</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### その他の[!UICONTROL Data Source]設定

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 次の場合に選択 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Outbound</span></b> </p> </td> 
   <td colname="col2"> <p>データソースが宛先にデータを送信する場合。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Share Enabled</span></b> </p> </td> 
   <td colname="col2"> <p>データソースを他のパートナーと共有できる場合。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Use as an Authenticated Profile</span></b> </p> </td> 
   <td colname="col2"> <p>認証済み ID がクロスデバイス対応データソースに含まれている場合。認証済み ID は、認証イベント（サイト上やアプリ内でのユーザーログインなど）の発生時に収集され、<span class="keyword">Audience Manager</span> ID に同期されます。認証済み ID は、この ID を格納した他のソースから得られるデータのオンボーディングに使用できます。また、複数のデバイス ID を<span class="wintitle">プロファイルリンク</span>でリンクする場合にも使用できます。 </p> <p>このオプションを選択すると、データソース名をエイリアスで変更できるテキストフィールドが表示されます。エイリアスを使用する場合、この新しい名前はデータソース名より優先され、<a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule">プロファイル結合ルールの作成</a>時に「<span class="wintitle">Authenticated Profile Options</span>」に表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Use as a Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> の他のお客様に提供できるデバイスグラフとしてデータソースを作成する場合。このオプションを選択する前に、この<span class="wintitle">データソース</span>の共有相手となるお客様を、担当の <span class="keyword">Audience Manager</span> コンサルタントに連絡してください。コンサルタントは、アドビの社内プロセスを通じてそれらの企業にプロビジョニングする必要があります。 </p> <p>このオプションを選択すると、データソース名をエイリアスで変更できるテキストフィールドが表示されます。エイリアスを使用する場合、この新しい名前はデータソース名より優先され、<a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule">プロファイル結合ルールの作成</a>時に「<span class="wintitle">Device Options</span>」に表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Share associated visitor or device IDs with specific Audience Manager Customers</span></b> </p> </td> 
   <td colname="col2"> <p>デバイスグラフから得られた ID がクロスデバイス対応データソースに含まれている場合。デバイスグラフは、1 つ以上の <span class="keyword"> Audience Manager</span> ID にマッピングされる ID の集まり（クラスター）です。このクラスターは通常、個人またはより人数の多い団体を表します。「データプロバイダー」として登録されているアカウントにのみ使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Share associated visitor or device IDs across the Audience Manager Platform</span></b> </p> </td> 
   <td colname="col2"> <p>他の <span class="keyword">Experience Cloud</span> ソリューションと共有できる訪問者 ID やデバイス ID がデータソースに含まれている場合。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 非アクティブな顧客 ID のデータ保持</span></b> </p> </td> 
   <td colname="col2"> <p>非アクティブな顧客 ID のデータ保持期間を設定できます。これにより、Audience Manager プラットフォームに Audience Manager が最後に表示された後、Audience Manager がデータベースに顧客 ID を保持する期間を決定します。</p> <p>デフォルト値は 24 か月（720 日）です。設定できる最小値は 1 か月、最大値は 5 年です。すべての月は 30 日としてカウントされます。</p> <p>Audience Manager は、非アクティブな顧客 ID に設定したデータ保持に従って、非アクティブな顧客 ID を週 1 度削除するプロセスを実行します。</p> <p>Audience Manager は、非アクティブな顧客 ID に設定したデータ保持に従って、非アクティブな顧客 ID を週 1 度削除するプロセスを実行します。</p> <p><b>注意</b>：このコントロールは、クロスデバイス対応データソースでのみ使用できます。<a href="../features/profile-merge-rules/merge-rules-start.md#settings">クロスデバイス対応データソースの作成</a>も参照してください。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unique Trait Integration Codes</span></b> </p> </td> 
   <td colname="col2"> <p>同じデータソースに含まれている 2 つの特性が同じ統合コードを持たないようにする必要がある場合。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unique Segment Integration Codes</span></b> </p> </td> 
   <td colname="col2"> <p>同じデータソースに含まれている 2 つのセグメントが同じ統合コードを持たないようにする必要がある場合。 </p> </td> 
  </tr>
 </tbody>
</table>
