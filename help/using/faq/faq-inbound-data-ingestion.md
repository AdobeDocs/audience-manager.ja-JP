---
description: Audience Manager へのオフラインデータの取り込みに関するよくある質問です。
keywords: FTP または s3;s3 または FTP
seo-description: Audience Manager へのオフラインデータの取り込みに関するよくある質問です。
seo-title: 受信顧客データ取り込みの FAQ
solution: Audience Manager
title: 受信顧客データ取り込みの FAQ
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 受信顧客データ取り込みの FAQ{#inbound-customer-data-ingestion-faq}

Audience Manager へのオフラインデータの取り込みに関するよくある質問です。

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**オンボーディングプロセスについて要約してください。**

オンボーディングプロセスは、[バッチデータ転送プロセスの説明](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process)で説明されている 2 つのコアコンポーネントで構成されています。以下に示します。

* ID 同期
* 受信データファイル（[!DNL .sync] ファイルまたは [!DNL .overwrite] ファイル）

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

ドキュメントの確認後に役立つ可能性のある質問および回答を以下に示します。

>[!NOTE]
>
>ここに記載する例は、簡潔さを重視して簡略化または短縮化されています。ファイル形式および構文に関する詳細な仕様については、受信データ取り込みに関するドキュメントを参照してください。

<br> 

**デプロイメントプロセスについて要約してください。**

アドビでは、以下をお勧めします。

* データプロバイダーと協力して、[!DNL Adobe]の仕様に応じて、毎日の受信データファイルの形式を設定します。
* 形式の検証のために、テストデータファイルを[!DNL Adobe]に転送します。
* [!DNL Adobe]のコンサルタントと協力して、データファイルのコンテンツを解釈するのに適した分類を作成します。
* ステージング／開発環境では、データプロバイダーの訪問者 ID を適切に選択し、[!DNL Audience Manager] サーバーにリアルタイムに転送するように ID 同期が設定されていることを確認します。
* DIL／ID 同期を実稼動環境にデプロイします。ID 同期は、アドビのコンサルタントによって既に DIL コード内のモジュールとして設定されています。
* 実稼動データファイルを [!DNL Audience Manager] に転送します。コードを実稼動に移行してからすぐにデータファイルの転送を開始できますが、ID 同期マッピングに基づいていることを考慮すると、実稼動コードのデプロイメントから最大 1 週間後にデータの転送を開始するとよいでしょう。

<br> 

**圧縮または暗号化ファイルの転送には、どの FTP モードを使用するとよいですか？**

詳しくは、[受信データ転送ファイルのファイル圧縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)を参照してください。

<br> 

**[!DNL Audience Manager]コードを実稼動環境にデプロイする前に、受信データファイル（[!DNL .sync]または[!DNL .overwrite]ファイル）をアップロードできますか？**

* データプロバイダーがクロスデバイスターゲティングで [プロファイルリンク](../features/profile-merge-rules/merge-rules-overview.md)を使用するように設定されている場合、ID 同期後すぐに、ターゲティングに利用可能なデータと一致する [!DNL Audience Manager] 訪問者 ID が特定されます。

* データプロバイダーが [!UICONTROL Profile Link] 機能を使用するように設定されていない場合、[!DNL Audience Manager] は、以前 [!DNL Audience Manager] 訪問者 ID と同期／マッチングし直した受信データファイルにある訪問者 ID のデータのみを処理します。

データプロバイダーが [!UICONTROL Profile Merge] を使用するように設定されていない場合、以下のユースケースを検討します。

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ユースケース </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>例 1</b> </p> </td> 
   <td colname="col2"> <p>月曜日に、訪問者が CRM データベースで訪問者 ABC ログインとして特定され、これによりクライアント側 ID 同期が開始されます。<span class="keyword">Audience Manager</span> は、訪問者 ABC のマッピングを <span class="keyword">Audience Manager</span> 訪問者 123 に格納します。 </p> <p>火曜日に、CRM データベースはデータファイル（<span class="filepath">.sync</span>）を <span class="keyword">Audience Manager</span> サーバーに以下のレコードと共に転送します。 </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>この場合、<span class="keyword">Audience Manager</span> では、以下のことがおこなわれます。 </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">格納された ID 同期マッピングから訪問者 ABC を認識します。 </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> 特性 <code>male</code> および <code>luxury_shopper</code> を訪問者 123 プロファイルに関連付けます。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>例 2</b> </p> </td> 
   <td colname="col2"> <p>月曜日に、CRM データベースはデータファイル（<span class="filepath">.sync</span>）を <span class="keyword">Audience Manager</span> サーバーに以下のレコードと共にプッシュします。 </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword">Audience Manager</span> は、この訪問者（または関連する訪問者 ID）のレコードを持たないので、このレコードは処理されません。 </p> <p>火曜日に、訪問者 DEF がログインします。このアクションにより、この訪問者の最初のクライアント側 ID 同期が開始されます。このアクションにより、訪問者 DEF が <span class="keyword">Audience Manager</span> ID 456 にマッピングされます。ただし、この訪問者は、そのプロファイルに関連付けられた CRM データを持ちません。結果として、<span class="keyword">Audience Manager</span> は、古いファイルに戻って再処理しません。 </p> <p>水曜日に、CRM データベースは別のデータファイルを <span class="keyword">Audience Manager</span> サーバーに以下のレコードと共にプッシュします。 </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>この場合、<span class="keyword">Audience Manager</span> では、以下のことがおこなわれます。 </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">格納された ID 同期マッピングから訪問者 DEF を認識します。 </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">特性 <code>female</code>、<code>paris</code> および <code>wine_enthusiast</code> を訪問者 456 プロファイルに関連付けます。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>例 3</b> </p> </td> 
   <td colname="col2"> <p>月曜日に、次のレコードを含んだ 2 つのファイルを <span class="keyword">Audience Manager</span> サーバーが受信します。 </p> <p> 次の内容の <code>.sync</code> ファイル： </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> 次の内容の <code>.overwrite</code> ファイル： </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword">Audience Manager では、以前の ID 同期から訪問者 JKL のマッピング済みレコードを ID 789 に格納します。</span> </p> <p>この場合、<span class="keyword">Audience Manager</span> では、以下のことがおこなわれます。 </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">格納された ID 同期マッピングから訪問者 JKL を認識します。 </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">特性 <code>female</code> および <code>wine_enthusiast</code> を訪問者 ID 789 のプロファイルに関連付けます。 </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">訪問者 GHI の ID は現在のバッチでのみ同期されたものなので、GHI の特性関連付けは無視されます。特性を訪問者 GHI に関連付けるには、今後の <code>.overwrite</code> ファイルにそれらの特性を含める必要があります。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**1 日のうちどの時刻にファイルを転送するとよいですか？**

[!DNL Audience Manager] は、1 日を通じて複数回ファイルをチェックおよび処理します。準備ができたらいつでも、ファイルをアップロードしてください。

<br> 

**アップロードされたファイルのデータがターゲット設定で使用できるようになるまで、どれくらいかかりますか？**

データは、48 時間後にターゲット設定に使用できます。また、「アップロードに成功しました」という内容の電子メールが届いても、データが使用できるようになったと解釈しないでください。これは、単に [!DNL Audience Manager] がファイルを選択して処理の最初のステップを完了したことを意味します。

<br> 

**どのくらいの頻度でファイルを送信するとよいですか？ また、完全なファイルを送信するのと増分ファイルを送信するのとでは、どちらがよいですか？**

ベストプラクティスとして、新しい訪問者およびデータが変更された訪問者について、1 日に 1 回、増分ファイルを送信します。多くの [!DNL Audience Manager] のお客様は、月に 1 回すべてのファイルを送信します。ただし、これらのファイルの間隔および増分には柔軟性があります。お客様にとって意味のあるタイミングで徐々にデータを送信する必要があります。

<br> 

**Audience Manager は、どれくらいの間ファイルをサーバーに保持しますか？**

FTP ファイルは、処理された後で削除されます。[!DNL S3] ファイルは、30 日後に削除されます。形式、構文または他のエラーによって処理できなかったファイルは、削除されます。また、[プライバシーとデータ保持についてよくある質問](../faq/faq-privacy.md)も参照してください。

<br> 

**完全なファイルと増分ファイルの違いは何ですか？**

* **完全：** 完全なファイルは、既存のすべての訪問者プロファイルを上書きし、ファイルのデータで置き換えます。完全なファイルは、ファイル名に追加された `.overwrite` タグで特定されます。`.overwrite` ファイルを使用して、訪問者の特性をリセットしたり、古くなって使用されない特性を削除したりできます。

   >[!NOTE]
   >
   >[!DNL .overwrite] ファイルは、このデータプロバイダーに関連付けられた [!DNL Audience Manager] プロファイルデータのみを上書きします。つまり、この訪問者に関連付けられたすべての [!DNL Adobe Analytics] データは、[!DNL .overwrite] ファイルが処理された後も、元の状態のままです。

* **増分：** 増分ファイルは、新しいデータを既存の訪問者プロファイルに追加します。増分ファイルは、ファイル名に追加された `.sync` タグで特定されます。増分ファイルを送信しても、既存のプロファイルを消去または上書きしません。

以下のユースケースに、これらのファイルタイプがどのように格納した訪問者プロファイルに影響するかを示します。

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ユースケース </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>増分および完全</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">1 日目 <code>.sync</code> ファイルコンテンツ：<code>visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">2 日目 <code>.overwrite</code> ファイルコンテンツ：<code>visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> 3 日目 訪問者プロファイル ID 123 には <code>c,d,e</code> が含まれている </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>増分のみ</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">1 日目 <code>.sync</code> ファイルコンテンツ：<code>visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">2 日目 <code>.sync</code> ファイルコンテンツ：<code>visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">3 日目 訪問者プロファイル ID 123 には <code>a,b,c,d,e</code> が含まれている </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

完全および増分ファイルタイプについて詳しくは、以下を参照してください。

* [Amazon S3 での受信データファイルの名前とファイルサイズの要件](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [FTP での受信データファイルの名前とサイズの要件...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**オンページ ID 同期を実行したことのない訪問者の ID を含むファイルを送信するとどうなりますか？**

処理の間、[!DNL Audience Manager] は、単にそのレコードをスキップして次に移行します。DPID（データプロバイダー ID）がデバイス間 DPID として設定されている場合、ID 同期前に取り込まれたデータが保存され、ID 同期の発生後すぐに使用できます。

<br> 

**タイムスタンプとは何ですか？ 何のために使用するのでしょうか？ また、例を提示してください。**

タイムスタンプは、ログおよび記録の保持のために使用されます。適切な形式の受信ファイル名に使用される構文で必要になります。以下を参照してください。

* [受信データファイルの Amazon S3 の名前に関する要件](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [FTP での受信データファイルの名前とサイズの要件...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**データプロバイダー ID（DPID）とは何ですか？ どうすれば入手できますか？**

アドビのコンサルタントが 3 桁または 4 桁の DPID を特定のデータソースに割り当てます。この ID は一意で、変更できません。

<br> 

**毎日のデータファイルはどのくらいの大きさになりますか？**

詳しくは、[受信データ転送ファイルのファイル圧縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)を参照してください。

<br> 

**Audience Manager はファイル圧縮をサポートしますか？**

はい。以下を参照してください。

* [受信データ転送ファイルのファイル圧縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [受信データファイルの Amazon S3 の名前に関する要件](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [受信データファイルの FTP の名前に関する要件](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**データソースデータベースのプライマリキーが電子メールアドレスです。これは、個人を特定できる情報と見なされますか？**

はい。[!DNL Audience Manager] では、アドビのデータベースに電子メールアドレスを格納しません。訪問者は、ID 同期を開始する前に、ランダムな ID または 1 方向のハッシュ化されたバージョンの電子メールアドレスを割り当てられる必要があります。

<br> 

**データファイルコンテンツでは大文字と小文字が区別されますか？ID 同期の場合はどうですか？**

データファイルには、一意のユーザー ID（UUID）とプロファイルデータという 2 つの基本的な構成要素があります。通常は、キー値ペアまたはコードの形式です。UUID は、大文字小文字が区別されます。通常、プロファイルまたはキー値ペアのデータは、大文字と小文字が区別されません。

<br> 

**ファイルを転送するために FTP または[!DNL Amazon S3]を使用する必要がありますか？**

ベストプラクティスとしては、プロセスがよりシンプルなので、[!DNL Amazon S3] をお勧めします。[!DNL Audience Manager] では FTP ファイルが [!DNL S3] に自動転送されるので、ファイルを自分で [!DNL Amazon S3] に配置するよりもプロセスの効率が向上します。さらに、FTP に同時にアップロードするお客様は、FTP の帯域幅を共有するので、アップロード速度が遅くなることが予想されます。[!DNL Amazon S3]また、 は、レプリケートされて配布されているので、通常、FTP サーバーよりも安全で信頼性が高くなります。詳しくは、[Amazon S3 について](../reference/amazon-s3.md)を参照してください。

<br> 

**Audience Manger で受信ファイルはどう処理されますか？**

[!DNL Audience Manager] では、[!DNL Amazon Simple Queue Service (SQS)] を使用して受信データを処理しています。その動作の仕組みは次のとおりです。

1. [!DNL Audience Manager] のお客様が受信データを [!DNL Amazon S3] バケットにアップロードします。

2. データが [!DNL Amazon SQS] キューに入り、[!DNL Audience Manager] で処理されるのを待ちます。

3. [!DNL Audience Manager] は、[!DNL Amazon SQS] キューから最大 119000 個のエントリを読み取って、最大 3 つのバッチに分割します。各バッチのファイルは同時に処理されます。

<br> 

**複数のファイルを同時にアップロードする必要があります。ファイルは同時に処理されますか？**

場合によります。[!DNL Audience Manager] は、[!DNL Amazon SQS] キューから最大 119000 個のエントリを読み取って、最大 3 つのバッチに分割します。同じバッチ内のファイルであれば、同時に処理されます。ただし、毎日大量のデータが [!DNL Audience Manager] に取り込まれるので、ファイルの処理順序は保証できません。

>[!MORE_LIKE_THIS]
>
>* [バッチデータ転送プロセスの説明](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process)

