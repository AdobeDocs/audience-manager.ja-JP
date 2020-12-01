---
description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. クライアント側の統合を選択した場合、Audience Manager で Google サイト運営者タグの Cookie ベースの宛先を作成する必要があります。
seo-description: 条件を満たしたセグメントは、クライアント側（ブラウザー側）の統合またはサーバー側の統合を通じて、Google Ad Managerに送信できます。 クライアント側の統合を選択した場合、Audience Manager で Google サイト運営者タグの Cookie ベースの宛先を作成する必要があります。
seo-title: GPT 宛先の作成
solution: Audience Manager
title: GPT 宛先の作成
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 86%

---


# GPT 宛先の作成 {#create-a-gpt-destination}

認定されたセグメントを、クライアント側（ブラウザー側）の統合またはサーバー側の統合により [!DNL Google Ad Manager] に送信することができます。クライアント側の統合を選択した場合、Audience Manager で [!DNL Google Publisher Tags] の Cookie ベースの宛先を作成する必要があります。

## 宛先

Audience Manager において、*`destination`* とは、データを共有する他のシステム（広告サーバー、[!DNL DSP]、広告ネットワークなど）になります。[!UICONTROL Destination Builder] は、これらのデータ配信プロセスを作成および管理するためのツールです。*[!UICONTROL Audience Data][!UICONTROL Destinations]*&#x200B;まず、**[!UICONTROL Add New Destination]**&#x200B;をクリックし、以下の手順に従います。

## Basic Information

「[!UICONTROL Basic Information]」セクションを完了するには：

1. 宛先の名前を入力します。
1. [!UICONTROL Type] ドロップダウンリストから&#x200B;**[!UICONTROL "Cookie"]**&#x200B;を選択します。
1. **[!UICONTROL Next]**&#x200B;をクリックし、「[!UICONTROL Configuration]」および「[!UICONTROL Segment Mappings]」セクションを開きます。

## Cookie の設定

以下の項目を指定して、「[!UICONTROL Configuration]」セクションでの設定を完了します（その他のフィールドはオプションです）。

1. **Cookie Name：** Cookie の短くてわかりやすい名前を指定します。
1. **Data Format**：「**[!UICONTROL "Single Key"]**」オプションを選択します。
1. **Key**：キー名を指定します。
1. **Serialize**：「**[!UICONTROL Enable]**」チェックボックスをオンにします。
1. **Serial Delimiter**：コンマのみを使用します。

## Segment Mappings

以下の手順で Cookie の宛先にセグメントを追加します。

1. Find segments：「[!UICONTROL Segment Mappings]」セクションには、セグメントを検索するための 2 つの検索ツールが用意されています。セグメントを検索するには、

   * オプション 1：検索フィールドにセグメント名を入力します。入力されたテキストに基づいて、フィールドが自動的に更新されます。使用するセグメントが見つかったら、**[!UICONTROL Add]**&#x200B;をクリックします。
   * オプション 2：**[!UICONTROL Browse All Segments]**&#x200B;をクリックし、名前または保存場所でセグメントを参照できるウィンドウを開きます。終了したら、「**[!UICONTROL Add Selected Segments]**」をクリックします。

1. **Add Mappings：**&#x200B;マッピングのポップアップ表示で、マッピングのフィールドにセグメント ID を入力し、**[!UICONTROL Save]**&#x200B;をクリックします。

1. 「**[!UICONTROL Done]**」をクリックします。