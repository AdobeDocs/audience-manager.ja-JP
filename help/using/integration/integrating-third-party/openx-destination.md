---
description: OpenX を送信先に設定し、Audience Manager のセグメントデータをこのプラットフォームに送信します。
seo-description: OpenX を送信先に設定し、Audience Manager のセグメントデータをこのプラットフォームに送信します。
seo-title: Audience Manager の送信先として OpenX を設定
solution: Audience Manager
title: Audience Manager の送信先として OpenX を設定
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Manager の宛先としての OpenX{#openx-as-an-audience-manager-destination}

[!DNL OpenX] を送信先に設定し、Audience Manager のセグメントデータをこのプラットフォームに送信します。

>[!NOTE]
>
>オンサイトの広告サーバーによるターゲティングのみが対象となります。

## OpenX の送信先に関する要件 {#openx-requirements}

コードの配置、サポートされるキー値の形式、レポート、および [!DNL OpenX] に送信されるセグメントデータのタイプに関する要件。

<!-- aam-openx-requirements.xml -->

Audience Manager の送信先として [!DNL OpenX] を設定する前に、以下を確認してください。

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] コードをサイトに導入する必要があります。[!UICONTROL DIL] を使用することで、データ収集、統合、Cookie 値の読み込み、およびページデータのリカバリのための専用コードを記述する手間を省くことができます。
* **`get_aamCookie`Function：** Audience Manager のユーザー ID および Cookie データを取得するためのコード。[このコード](../../features/destinations/get-aam-cookie-code.md)をページの先頭または `<head>` コードブロック内に配置します。
* **Audience Manager に配信ログを送信：**&#x200B;セグメントの配信レポート（オプション）が必要である場合、インプレッションレベルの配信データが含まれる日単位のログを Audience Manager に送信します。The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager は [!DNL FTP] を介してこれらを受け取ることができます。

### キーと値のデータ：形式の要件

Audience Manager はデータをキーと値のペアとして送信します。以下の仕様に従って、キーと値のペアを作成してください。

* キーの前に `c.` を付けます（`c.color` または `c.price` など）。
* 単一のキーにシリアル化された値を割り当てる場合、コンマで区切ります（`c.color = red, green, blue` など）。
* 複数のキーと値のペアは、アンパサンドで区切ります（`c.color=red & c.price = 100 & c.condition = new` など）。
* キー名にアクセントや句読点、その他の記号などの特殊文字を含めることはできません。

### 適合するセグメントのみ OpenX に送信

[!DNL OpenX] に渡されるデータの量は、特定のユーザーが適合するセグメントの数によって異なります。例えば、Audience Management のセグメントを 100 件設定したとします。サイト訪問者がそのうち 5 件を認定した場合、その 5 件のセグメントだけが [!DNL OpenX] に送信されます（100 件全部ではありません）。

## OpenX の送信先の作成 {#openx-destination}

Create a cookie destination for [!DNL OpenX] in Audience Management.

<!-- aam-openx-destination.xml -->

Audience Manager では、データを共有したい他のあらゆるシステム（広告サーバー、広告ネットワークなど）を&#x200B;*送信先*&#x200B;にできます[!DNL DSP]宛先になります。[!UICONTROL Destination Builder] は、これらのデータ配信プロセスを作成および管理するためのツールです。Audience Manager の宛先に関する機能は、*Audience Data／Destinations* からアクセスできます。To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### 手順 1：基本情報

To complete the [!UICONTROL Basic Information] section:

1. 宛先の名前を入力します。
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

### 手順 2：設定情報

To complete the [!UICONTROL Configuration] section:

1. **Cookie Name：** Cookie の短くてわかりやすい名前を指定します。
1. **Cookie Domain：**&#x200B;ユーザーが現在見ているページのドメインの Cookie を設定する場合は空のままとします。ドメインを指定する場合は、`.mydomain.com` のように、ピリオドを使用して名前にプレフィックスを付けます。
1. [!UICONTROL Data Format] セクションでキーオプションを選択します。
1. シリアル化された値のデータを使用するキーの場合、**[!UICONTROL Serialize]** コントロールを選択し、シリアル値の区切り文字（シリアル化された値を区切るための文字）を指定します。
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

### 手順 3：セグメントマッピング

以下の手順で Cookie の宛先にセグメントを追加します。 

1. **Find segments：**「[!UICONTROL Segment Mappings]」セクションには、セグメントを検索するための 2 つの検索ツールが用意されています。セグメントを検索するには、
   * オプション 1：検索フィールドにセグメント名を入力します。その文字列に基づきフィールドが自動で更新されます。使用するセグメントが見つかったら、「**[!UICONTROL Add]**」をクリックします。
   * オプション 2：「**[!UICONTROL Browse All Segments]**」をクリックし、名前または保存場所に基づきセグメントを参照できるウィンドウを開きます。Click **[!UICONTROL Add Selected Segments]** when done.
1. **Add Mappings：**&#x200B;マッピングのポップアップ表示で、マッピングのフィールドにセグメント ID を入力し、「**[!UICONTROL Save]**」をクリックします。
1. **[!UICONTROL Done]**&#x200B;をクリックします。

## OpenX の設定 {#openx-code-setup}

Audience Manager のセグメントデータを処理するよう [!DNL OpenX] 設定を変更します。

<!-- aam-openx-code.xml -->

次の手順で [!DNL OpenX] を設定します。

* サイト全体にわたり、[!UICONTROL DIL] コードをインストールします。
* Audience Manager で Cookie の送信先として [!DNL OpenX] を作成します。
* `get_aamCookie` 関数をページの先頭、可能であれば `<head>` コードブロック内に配置します。`get_aamCookie` コード [は以下から入手できます。](../../features/destinations/get-aam-cookie-code.md)
* `get_aamCookie`[!DNL OpenX] 関数を呼び出すよう広告タグを変更し、 の送信先を設定した際に指定した Cookie 名を含めます。例えば、Cookie の名前を `test_cookie` とした場合、広告タグは `get_aamCookie` を呼び出し、この Cookie 名を参照する必要があります。
* 広告タグは次に示す例のような形式になります。

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

必ず `xid=` = を含めてください。It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.

完全形式の広告呼び出しは以下のようになります。

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
