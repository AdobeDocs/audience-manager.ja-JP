---
description: OpenX を宛先に設定し、Audience Manager のセグメントデータをこのプラットフォームに送信します。
seo-description: OpenX を宛先に設定し、Audience Manager のセグメントデータをこのプラットフォームに送信します。
seo-title: Audience Manager の宛先としての OpenX
solution: Audience Manager
title: Audience Manager の宛先としての OpenX
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 98%

---


# Audience Manager の宛先としての OpenX{#openx-as-an-audience-manager-destination}

[!DNL OpenX] を宛先として設定し、Audience Manager のセグメントデータをこのプラットフォームに送信します。

>[!NOTE]
>
>オンサイトの広告サーバーによるターゲティングのみが対象となります。

## OpenX の宛先に関する要件 {#openx-requirements}

コードの配置、サポートされるキー値の形式、レポート、および [!DNL OpenX] に送信されるセグメントデータのタイプに関する要件。

<!-- aam-openx-requirements.xml -->

Audience Manager の宛先として [!DNL OpenX] を設定する前に、以下を確認してください。

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] コードをサイトに導入する必要があります。 [!UICONTROL DIL] を使用することで、データ収集、統合、Cookie 値の読み込み、およびページデータのリカバリのための専用コードを記述する手間を省くことができます。
* **`get_aamCookie`関数：** Audience Manager のユーザー ID および Cookie データを取得するためのコード。[このコード](../../features/destinations/get-aam-cookie-code.md)をページの先頭または `<head>` コードブロック内に配置します。
* **Send Delivery Logs to Audience Manager：**&#x200B;セグメントの配信レポート（オプション）が必要である場合、インプレッションレベルの配信データが含まれる日単位のログを Audience Manager に送信します。データは raw 形式でもかまいませんが、各レコードには Audience Manager `UUID` が含まれている必要があります。Audience Manager は [!DNL FTP] を介してこれらを受け取ることができます。

### キーと値のデータ：形式の要件

Audience Manager はデータをキーと値のペアとして送信します。以下の仕様に従って、キーと値のペアを作成してください。

* キーの前に `c.` を付けます（`c.color` または `c.price` など）。
* 単一のキーにシリアル化された値を割り当てる場合、コンマで区切ります（`c.color = red, green, blue` など）。
* 複数のキーと値のペアは、アンパサンドで区切ります（`c.color=red & c.price = 100 & c.condition = new` など）。
* キー名にアクセントや句読点、その他の記号などの特殊文字を含めることはできません。

### 適合するセグメントのみ OpenX に送信

[!DNL OpenX] に渡されるデータの量は、特定のユーザーが適合するセグメントの数によって異なります。例えば、100 件の Audience Manager セグメントを設定したとします。サイト訪問者がそのうち 5 件を認定した場合、その 5 件のセグメントだけが [!DNL OpenX] に送信されます（100 件全部ではありません）。

## OpenX の宛先の作成 {#openx-destination}

Audience Manager で、[!DNL OpenX] の cookieookie の宛先を作成します。

<!-- aam-openx-destination.xml -->

Audience Manager において、*宛先*&#x200B;とは、データを共有したい他システム（広告サーバー、[!DNL DSP]、広告ネットワークなど）になります。[!UICONTROL Destination Builder] は、これらのデータ配信プロセスを作成および管理するためのツールです。Audience Manager の宛先に関する機能は、*Audience Data／Destinations* からアクセスできます。まず、**[!UICONTROL Add New Destination]**&#x200B;をクリックし、以下の手順に従います。

### 手順 1：基本情報

「[!UICONTROL Basic Information]」セクションを完了するには：

1. 宛先の名前を入力します。
1. [!UICONTROL Type] ドロップダウンリストから&#x200B;**[!UICONTROL "Cookie"]**&#x200B;を選択します。
1. **[!UICONTROL Next]**&#x200B;をクリックし、「[!UICONTROL Configuration]」および「[!UICONTROL Segment Mappings]」セクションを開きます。

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

## OpenX の設定 {#openx-code-setup}

Audience Manager のセグメントデータを処理するよう [!DNL OpenX] 設定を変更します。

<!-- aam-openx-code.xml -->

次の手順で [!DNL OpenX] を設定します。

* サイト全体にわたり、[!UICONTROL DIL] コードをインストールします。
* Audience Manager で Cookie の宛先として [!DNL OpenX] を作成します。
* `get_aamCookie` 関数をページの先頭、可能であれば `<head>` コードブロック内に配置します。`get_aamCookie` コード は[こちら](../../features/destinations/get-aam-cookie-code.md)から入手できます。
* `get_aamCookie` 関数を呼び出すよう広告タグを変更し、[!DNL OpenX] の宛先を設定した際に指定した Cookie 名を含めます。例えば、Cookie の名前を `test_cookie` とした場合、広告タグは `get_aamCookie` を呼び出し、この Cookie 名を参照する必要があります。
* 広告タグは次に示す例のような形式になります。

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

必ず `xid=`を含めてください。この変数は、広告呼び出しの際に実際に渡された一意のユーザー ID （[!UICONTROL UUID]）を保持します。

完全形式の広告呼び出しは以下のようになります。

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
