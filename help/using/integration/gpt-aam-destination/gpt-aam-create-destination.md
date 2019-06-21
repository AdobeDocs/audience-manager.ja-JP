---
description: 認定されたセグメントを、クライアント側（ブラウザー側）の統合、またはサーバー側の統合により DFP に送信することができます。クライアント側の統合を選択した場合、Audience Manager で Google サイト運営者タグの Cookie ベースの宛先を作成する必要があります。
seo-description: 認定されたセグメントを、クライアント側（ブラウザー側）の統合、またはサーバー側の統合により DFP に送信することができます。クライアント側の統合を選択した場合、Audience Manager で Google サイト運営者タグの Cookie ベースの宛先を作成する必要があります。
seo-title: GPT 宛先の作成
solution: Audience Manager
title: GPT 宛先の作成
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# GPT 宛先の作成 {#create-a-gpt-destination}

認定されたセグメントを、クライアント側（ブラウザー側）の統合またはサーバー側の統合により [!DNL DFP] に送信することができます。クライアント側の統合を選択した場合、Audience Manager で [!DNL Google Publisher Tags] の Cookie ベースの宛先を作成する必要があります。

## 宛先

Audience Manager での *`destination`* とは、他のシステム（広告サーバー、広告ネットワークなど）の[!DNL DSP]宛先になります。[!UICONTROL Destination Builder] は、これらのデータ配信プロセスを作成および管理するためのツールです。Audience Manager destination features are located in *[!UICONTROL Audience Data] &gt; [!UICONTROL Destinations]*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

## 基本情報

To complete the [!UICONTROL Basic Information] section:

1. 宛先の名前を入力します。
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

## Cookie の設定

以下の項目を指定して、「[!UICONTROL Configuration]」セクションでの設定を完了します（その他のフィールドはオプションです）。

1. **Cookie Name：** Cookie の短くてわかりやすい名前を指定します。
1. **データ形式:****[!UICONTROL "Single Key"]** このオプションを選択します。
1. **Key**：キー名を指定します。
1. **Serialize**：「**[!UICONTROL Enable]**」チェックボックスをオンにします。
1. **Serial Delimiter**：コンマのみを使用します。

## Segment Mappings

以下の手順で Cookie の宛先にセグメントを追加します。 

1. セグメントを検索：「[!UICONTROL Segment Mappings]」セクションでは、2 通りの方法でツールの検索とセグメントの検索ができます。セグメントを検索するには、

   * オプション 1：検索フィールドにセグメント名を入力します。入力されたテキストに基づいて、フィールドが自動的に更新されます。使用するセグメントが見つかったら、「**[!UICONTROL Add]**」をクリックします。
   * オプション 2：「**[!UICONTROL Browse All Segments]**」をクリックし、名前または保存場所に基づきセグメントを参照できるウィンドウを開きます。Click **[!UICONTROL Add Selected Segments]** when done.

1. **Add Mappings：** マッピングのポップアップ表示で、マッピングのフィールドにセグメント ID を入力し、「**[!UICONTROL Save]**」をクリックします。

1. **[!UICONTROL Done]** をクリックします。