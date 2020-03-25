---
description: Audience Manager へのオフラインデータの取り込みに関するよくある質問です。
keywords: ftp or s3;s3 or ftp
seo-description: Audience Manager へのオフラインデータの取り込みに関するよくある質問です。
seo-title: 顧客データのインバウンドの取得に関するよくある質問
solution: Audience Manager
title: 顧客データのインバウンドの取得に関するよくある質問
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: 187874fb5d0c4363f771297766f3c4bc9d967c9b

---


# 顧客データのインバウンドの取得に関するよくある質問 {#inbound-customer-data-ingestion-faq}

Audience Manager へのオフラインデータの取り込みに関するよくある質問です。

 

**オンボーディングプロセスについて要約してください。**

オンボーディングプロセスは、Audience Managerへのバッチデータの [送信の概要で説明する2つの手順で構成されます](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)。

* 手順1:ユーザーIDの同期；
* 手順2:ファイル形式の要件に従って、受信データファイルを作成し、転送します。

 

**デプロイメントプロセスについて要約してください。**

アドビでは、以下をお勧めします。

* データプロバイダーと協力して、アドビの仕様に従って日別受信データファイルの形式を設定します。 ファイルの命名と構文の要件については、次のドキュメントを参照してください。
   * [ID 同期ファイルの名前およびコンテンツの要件](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [受信データファイルコンテンツ：構文、無効な文字、変数、例](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [受信データファイルの Amazon S3 名とファイルサイズの要件](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* フォーマット検証のた [!DNL Adobe] めに、コンサルタントにテストデータファイルをに転 [!DNL Adobe] 送するよう依頼します。
* [!DNL Adobe]のコンサルタントと協力して、データファイルのコンテンツを解釈するのに適した分類を作成します。
* In the staging/development environment, confirm that the ID synchronization is configured to properly pick up the data provider&#39;s visitor ID and transfer it to the [!DNL Audience Manager] servers in realtime.
* DIL/ID同期を実稼働環境にデプロイします。 ID同期は、アドビコンサルタントがDILコード内のモジュールとして既に設定します。
* 実稼動データファイルを [!DNL Audience Manager] に転送します。ID同期マッピングに依存しているので、実稼働コードのデプロイメントから最大1週間後にデータの転送を開始すると効果的ですが、コードが実稼働に移行したらすぐにデータファイルの転送を開始できます。

 

**圧縮または暗号化ファイルの転送には、どの FTP モードを使用するとよいですか？**

詳しくは、[受信データ転送ファイルのファイル圧縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)を参照してください。

>[!WARNING]
>
>FTP 設定のサポートは段階的に廃止されます。受信データファイルの取り込みは、既存の FTP 取り込みでサポートされますが、新しい取り込み用にオフラインデータをオンボードするには、Amazon S3 を使用することを強くお勧めします。詳細は、[受信データファイルの Amazon S3 名とファイルサイズの要件](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)を参照してください。

 

**[!DNL Audience Manager]コードを実稼動環境にデプロイする前に、受信データファイル（[!DNL .sync] または [!DNL .overwrite] ファイル）をアップロードできますか？**

はい。アップロードする CRM データを保存するためにクロスデバイスデータソースを使用している限り、Audience Manager では常にデータが保存されます。実際、2019 年 10 月に Audience Manager が開始した、オフラインのみの使用を許可するプロファイル結合ルールの機能強化に従って、Audience Manager コードを実稼働環境にデプロイしなくても、データをアップロードしてアクションを実行できます。以下を参照してください。

* [プロファイル結合ルールの強化の概要](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* ユーザーベースの宛先 — [オフラインのみのデータに基づくパーソナライゼーション](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

<br> 

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

**1 日のうちどの時刻にファイルを転送するとよいですか？**

[!DNL Audience Manager] は、1 日を通じて複数回ファイルをチェックおよび処理します。準備ができたらいつでも、ファイルをアップロードしてください。

 

**アップロードされたファイルのデータがターゲティングで使用できるようになるまで、どれくらいかかりますか？**

データは、48 時間後にターゲティングに使用できます。また、「アップロードに成功しました」という内容の電子メールが届いても、データが使用できるようになったと解釈しないでください。これは、単に [!DNL Audience Manager] がファイルを選択して処理の最初のステップを完了したことを意味します。

 

**どのくらいの頻度でファイルを送信するとよいですか？ また、完全なファイルを送信するのと増分ファイルを送信するのとでは、どちらがよいですか？**

ベストプラクティスとして、新しい訪問者およびデータが変更された訪問者について、1 日に 1 回、増分ファイルを送信します。多くの [!DNL Audience Manager] のお客様は、月に 1 回すべてのファイルを送信します。ただし、これらのファイルの間隔および増分には柔軟性があります。お客様にとって意味のあるタイミングで徐々にデータを送信する必要があります。

 

**Audience Manager は、どれくらいの間ファイルをサーバーに保持しますか？**

FTP ファイルは、処理された後で削除されます。[!DNL S3] ファイルは30日後に削除されます。 形式、構文、またはその他のエラーが原因で処理できないファイルは削除されます。 「プライバシーとデー [タ保持に関するFAQ」も参照してください](../faq/faq-privacy.md)。

 

**完全なファイルと増分ファイルの違いは何ですか？**

* **完全：**&#x200B;完全なファイルは、既存のすべての訪問者プロファイルを上書きし、ファイルのデータで置き換えます。完全なファイルは、ファイル名に追加された `.overwrite` タグで特定されます。`.overwrite` ファイルを使用して、訪問者の特性をリセットしたり、古くなって使用されない特性を削除したりできます。

   >[!NOTE]
   >
   >[!DNL .overwrite] ファイルは、このデータプロバイダーに関連付けられた [!DNL Audience Manager] プロファイルデータのみを上書きします。つまり、この訪問者に関連付けられたすべての [!DNL Adobe Analytics] データは、[!DNL .overwrite] ファイルが処理された後も、元の状態のままです。

* **増分：**&#x200B;増分ファイルは、新しいデータを既存の訪問者プロファイルに追加します。増分ファイルは、ファイル名に追加された `.sync` タグで特定されます。増分ファイルを送信しても、既存のプロファイルを消去または上書きしません。

以下のユースケースに、これらのファイルタイプがどのように格納した訪問者プロファイルに影響するかを示します。

| ユースケース | 説明 |
|---|---|
| 増分および完全 | <ul><li>1 日目の `.sync` ファイルコンテンツ `visitor123 = a,b,c`</li><li>2 日目の `.overwrite` ファイルコンテンツ `visitor123 = c,d,e`</li><li>Day 3 visitor profile ID 123 contents: `c,d,e`</li></ul> |
| 増分のみ | <ul><li>1 日目の `.sync` ファイルコンテンツ `visitor123 = a,b,c`</li><li>2 日目の `.sync` ファイルコンテンツ `visitor123 = c,d,e`</li><li>Day 3 visitor profile ID 123 contents: `a,b,c,d,e`</li></ul> |

完全および増分ファイルタイプについて詳しくは、以下を参照してください。

* [Amazon S3 での受信データファイルの名前とファイルサイズの要件](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**オンページ ID 同期を実行したことのない訪問者の ID を含むファイルを送信するとどうなりますか？**

During processing, [!DNL Audience Manager] skips that record and moves on to the next. If a [DPID (Data Provider ID)](../reference/ids-in-aam.md) is set up as a cross-device DPID, data that is ingested before an ID synchronization is saved and is available for use shortly after the ID synchronization occurs.

 

**タイムスタンプとは何ですか？ 何のために使用するのでしょうか？ また、例を提示してください。**

タイムスタンプは、ログおよび記録の保持のために使用されます。適切な形式の受信ファイル名に使用される構文で必要になります。以下を参照してください。

* [受信データファイルの Amazon S3 の名前に関する要件](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**データプロバイダー ID（DPID）とは何ですか？ どうすれば入手できますか？**

Your Adobe consultant will assign a three-digit or four-digit [DPID (Data Provider ID)](../reference/ids-in-aam.md) to your particular data source. この ID は一意で、変更できません。

 

**毎日のデータファイルはどのくらいの大きさになりますか？**

詳しくは、[受信データ転送ファイルのファイル圧縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)を参照してください。

 

**Audience Manager はファイル圧縮をサポートしますか？**

はい。以下を参照してください。

* [受信データ転送ファイルのファイル圧縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [受信データファイルの Amazon S3 の名前に関する要件](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**データソースデータベースのプライマリキーが電子メールアドレスです。これは、個人を特定できる情報と見なされますか？**

はい。[!DNL Audience Manager] データベースに電子メールアドレスを格納しません。 IDの同期を開始する前に、訪問者に、ランダムに生成されたIDまたは一方向にハッシュ化された電子メールアドレスのIDを割り当てる必要があります。

 

**データファイルコンテンツでは大文字と小文字が区別されますか？How about the ID synchronization?**

There are two basic components of a data file: A [!UICONTROL User ID] (see [!UICONTROL User ID] in [File Variables Defined](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) and profile data, usually in the form of key-value pairs or codes. The [!UICONTROL User ID] is case-sensitive. 通常、プロファイルまたはキーと値のペアのデータは、大文字と小文字が区別されません。

 

**ファイルを転送するために FTP または[!DNL Amazon S3]を使用する必要がありますか？**

ベストプラクティスとしては、プロセスがよりシンプルなので、[!DNL Amazon S3] をお勧めします。[!DNL Audience Manager] では FTP ファイルが [!DNL S3] に自動転送されるので、ファイルを自分で [!DNL Amazon S3] に配置するよりもプロセスの効率が向上します。さらに、FTP に同時にアップロードするお客様は、FTP の帯域幅を共有するので、アップロード速度が遅くなることが予想されます。[!DNL Amazon S3]また、 は、レプリケートされて配布されているので、通常、FTP サーバーよりも安全で信頼性が高くなります。詳しくは、[Amazon S3 について](../reference/amazon-s3.md)を参照してください。

>[!WARNING]
>
>FTP 設定のサポートは段階的に廃止されます。受信データファイルの取り込みは、既存の FTP 取り込みでサポートされますが、新しい取り込み用にオフラインデータをオンボードするには、Amazon S3 を使用することを強くお勧めします。詳細は、[受信データファイルの Amazon S3 名とファイルサイズの要件](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)を参照してください。

 

**Audience Manger で受信ファイルはどう処理されますか？**

[!DNL Audience Manager] では、[!DNL Amazon Simple Queue Service (SQS)] を使用して受信データを処理しています。その動作の仕組みは次のとおりです。

1. [!DNL Audience Manager] のお客様が受信データを [!DNL Amazon S3] バケットにアップロードします。
1. データが [!DNL Amazon SQS] キューに入り、[!DNL Audience Manager] で処理されるのを待ちます。
1. [!DNL Audience Manager] は、[!DNL Amazon SQS] キューから最大 119000 個のエントリを読み取って、最大 3 つのバッチに分割します。各バッチのファイルは同時に処理されます。

 

**複数のファイルを同時にアップロードする必要があります。ファイルは同時に処理されますか？**

場合によります。[!DNL Audience Manager] は、[!DNL Amazon SQS] キューから最大 119000 個のエントリを読み取って、最大 3 つのバッチに分割します。同じバッチ内のファイルであれば、同時に処理されます。ただし、毎日大量のデータが [!DNL Audience Manager] に取り込まれるので、ファイルの処理順序は保証できません。

>[!MORELIKETHIS]
>
>* [バッチデータ転送プロセスの説明](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

