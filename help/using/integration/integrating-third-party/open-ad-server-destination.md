---
description: Open Ad サーバーを宛先に設定し、Audience Manager のデータをこのプラットフォームに送信します。
seo-description: Open Ad サーバーを宛先に設定し、Audience Manager のデータをこのプラットフォームに送信します。
seo-title: Audience Manager の宛先としての OAS
solution: Audience Manager
title: Audience Manager の宛先としての OAS
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: サードパーティ統合
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 100%

---

# Audience Manager の宛先としての OAS {#oas-as-an-audience-manager-destination}

[!DNL Open Ad Server] を宛先に設定し、Audience Manager のセグメントデータをこのプラットフォームに送信します。

## OAS の宛先に関する要件 {#oas-requirements}

コードの配置、サポートされるキー値の形式、レポート、および [!DNL OAS] に送信されるセグメントデータのタイプに関する要件。

<!-- aam-oas-requirements.xml -->

この宛先タイプには次の項目が必要となります。

* **[!UICONTROL DIL]：**[!UICONTROL Data Integration Library] コードはインベントリ上にデプロイする必要があります。[!UICONTROL DIL] を使用することで、データ収集、統合、Cookie 値の読み込み、およびページデータのリカバリのための専用コードを記述する手間を省くことができます。
* **`get_aamCookie`関数：** Audience Manager のユーザー ID および Cookie データを取得するためのコード。[このコード](../../features/destinations/get-aam-cookie-code.md)をページの先頭または `<head>` コードブロック内に配置します。
* **Send Delivery Logs to Audience Manager：**&#x200B;セグメントの配信レポート（オプション）が必要である場合、インプレッションレベルの配信データが含まれる日単位のログを Audience Manager に送信します。データは raw 形式でもかまいませんが、各レコードには Audience Manager [!UICONTROL UUID] が含まれている必要があります。Audience Manager は [!DNL FTP] を介してこれらを受け取ることができます。

### Cookie 形式およびキーと値のデータ

Audience Manager はブラウザー Cookie に対してセグメントデータを次のように送信できます。 

* 単一のキー（`x=1&x=2`）
* 複数のキー（`x=1&x=2&y=3&y=4`）
* シリアル化された値（`x=1,2,3`）
* 個々のキーと値のペアが区切られる標準的な値の区切り文字

### 適合するセグメントのみ OAS に送信

[!DNL OAS] に渡されるデータの量は、特定のユーザーが適合するセグメントの数によって異なります。例えば、100 件の Audience Manager セグメントを設定したとします。サイト訪問者が適合しているのがその内の 5 件であった場合、100 件すべてではなく、これらの 5 件のセグメントのみが OAS に送信されます。

>[!MORELIKETHIS]
>
>* [get_aamCookie コード](../../features/destinations/get-aam-cookie-code.md)
* [キーと値のペアの解説 ](../../reference/key-value-pairs-explained.md)


## OAS の宛先の作成 {#oas-dest-setup}

Audience Manager で、[!DNL OAS] に Cookie ベースの宛先を作成します。

<!-- aam-oas-destination-setup.xml -->

Audience Manager において、*宛先*&#x200B;とは、データを共有したい他システム（広告サーバー、[!DNL DSP]、広告ネットワークなど）になります。[!UICONTROL Destination Builder] は、これらのデータ配信プロセスを作成および管理するためのツールです。Audience Manager の宛先に関する機能は、*Audience Data／Destinations* からアクセスできます。まず、**[!UICONTROL Add New Destination]**&#x200B;をクリックし、以下の手順に従います。

### 手順 1：基本情報

「[!UICONTROL Basic Information]」セクションを完了するには：

1. 宛先の名前を入力します。
1. **[!UICONTROL "Cookie"]** ドロップダウンリストから「[!UICONTROL Type]」を選択します。
1. **[!UICONTROL Save]**&#x200B;をクリックし、「[!UICONTROL Configuration]」および「[!UICONTROL Segment Mappings]」セクションを開きます。

### 手順 2：設定情報

「[!UICONTROL Configuration]」セクションを完了するには：

1. **Cookie Name：** Cookie の短くてわかりやすい名前を指定します。
1. **Cookie Domain：**&#x200B;ユーザーが現在表示しているページのドメインで Cookie を設定する場合は空のままとします。ドメインを指定する場合は、`.mydomain.com` のように、ピリオドを使用して名前にプレフィックスを付けます。
1. 「[!UICONTROL Data Format]」セクションでキーオプションを選択します。
1. シリアル化された値のデータを使用するキーの場合、**[!UICONTROL Serialize]** コントロールを選択し、シリアル値の区切り文字（シリアル化された値を区切るための文字）を指定します。
1. **[!UICONTROL Save]**&#x200B;をクリックし、「[!UICONTROL Segment Mappings]」セクションを展開します。

### 手順 3：セグメントマッピング

以下の手順で Cookie の宛先にセグメントを追加します。

1. **Find segments：**「[!UICONTROL Segment Mappings]」セクションには、セグメントを検索するための 2 つの検索ツールが用意されています。セグメントを検索するには、
   * オプション 1：検索フィールドにセグメント名を入力します。その文字列に基づきフィールドが自動で更新されます。使用するセグメントが見つかったら、**[!UICONTROL Add]**&#x200B;をクリックします。
   * オプション 2：**[!UICONTROL Browse All Segments]**&#x200B;をクリックし、名前または保存場所でセグメントを参照できるウィンドウを開きます。終了したら、「**[!UICONTROL Add Selected Segments]**」をクリックします。
1. **Add Mappings：**&#x200B;マッピングのポップアップ表示で、マッピングのフィールドにセグメント ID を入力し、**[!UICONTROL Save]**&#x200B;をクリックします。
1. 「**[!UICONTROL Done]**」をクリックします。

## OAS 設定 {#oas-code-setup}

Audience Manager のセグメントデータを処理するよう [!DNL OAS] 設定を変更します。

<!-- aam-oas-code.xml -->

次の手順で [!DNL OAS] を設定します。

* サイト全体にわたり、[!UICONTROL DIL] コードをインストールします。
* Audience Manager で Cookie の宛先として OAS を作成します。
* `get_aamCookie` 関数をページの先頭、可能であれば `<head>` コードブロック内に配置します。`get_aamCookie` コード は[こちら](../../features/destinations/get-aam-cookie-code.md)から入手できます。
* `get_aamCookie` 関数を呼び出すよう広告タグを変更し、[!DNL OAS] の宛先を設定した際に指定した Cookie 名を含めます。例えば、Cookie の名前を `test_cookie` とした場合、広告タグは `get_aamCookie` を呼び出し、この Cookie 名を参照する必要があります。
* 広告タグは次に示す例のような形式になります。

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

必ず `u=` 変数を含めてください。この変数は、広告呼び出しの際に実際に渡された一意のユーザー ID （[!UICONTROL UUID]）を保持します。
