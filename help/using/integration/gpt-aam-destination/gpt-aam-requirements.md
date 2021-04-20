---
description: クライアントサイドまたはサーバーサイドの統合を通じて、適格なセグメントを Google Ad Manager に送信できます。この両方のメソッドに関する要件と関連情報を以下に示します。
seo-description: クライアントサイドまたはサーバーサイドの統合を通じて、適格なセグメントを Google Ad Manager に送信できます。この両方のメソッドに関する要件と関連情報を以下に示します。
seo-title: Google サイト運営者タグ（GPT）を使用して Google Ad Manager にセグメントを送信する際の要件と方法
solution: Audience Manager
title: Google サイト運営者タグ（GPT）を使用して Google Ad Manager にセグメントを送信する際の要件と方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 99%

---

# Google サイト運営者タグ（GPT）を使用して Google Ad Manager にセグメントを送信する際の要件と方法 {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

クライアント側またはサーバー側の統合を通じて、適格なセグメントを [!DNL Google Ad Manager]（旧称 DFP）に送信できます。この両方のメソッドに関する要件と関連情報を以下に示します。

## クライアント側の統合 {#client-side-integration}

クライアント側の統合では、Audience Manager で [!DNL GPT] 宛先を設定する必要があります。[!DNL GPT]を Audience Manager 宛先として設定する場合、次の点を考慮してください。

* **を追加[!UICONTROL DIL]：**&#x200B;ターゲットに設定するすべてのページに [!UICONTROL Data Integration Library (DIL)] コードをデプロイします。[!UICONTROL DIL] は Audience Manager のセグメントデータとユーザー ID を、[!DNL GPT] がターゲティングに使用する Cookie に書き込みます。

* **の作成[!UICONTROL Cookie Destination]：**[!DNL GPT] は Audience Manager で Cookie ベースの宛先として設定しなければなりません。

* **Cookie チェックコードの実装**：[!DNL GPT] の `.setTargeting` API メソッドを、推奨される [Cookie チェックコード](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)でラップします。このコードにより、`.setTargeting`.メソッドを呼び出す前に有効な AAM Cookie が検索されるので、エラーが回避されます。

* **`AamGpt` 関数の追加：**`AamGpt` コードは Audience Manager の Cookie からデータをキャプチャして、[!DNL GPT]に送信します。[Google サイト運営者タグ用の Audience Manager コード](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)（`AamGpt`）をページの最上部または `<head>` コードブロック内に配置します。

   >[!NOTE]
   >
   >独自のコードを使用して Audience Manager の Cookie データを読み取る場合、`AamGpt` 関数は必要ありません。

* **Send Delivery Logs to Audience Manager：**&#x200B;セグメントの配信レポート（オプション）が必要である場合、インプレッションレベルの配信データが含まれる日単位のログを Audience Manager に送信します。データは raw 形式でもかまいませんが、各レコードには Audience Manager `UUID` が含まれている必要があります。Audience Manager は [!DNL FTP] を介してこれらを受け取ることができます。

### GPT に送信されるのは認定されたセグメントのみ

[!DNL GPT] に渡されるデータの量は、特定のユーザーが認定するセグメントの数によって異なります。例えば、100 件の Audience Manager セグメントを設定したとします。サイト訪問者がそのうち 5 件を認定した場合、その 5 件のセグメントだけが [!DNL GPT] に送信されます（100 件全部ではありません）。

>[!NOTE]
>
>送信できるキーと値の数に制限はありませんが、[!DNL Google] リクエスト [!DNL URL] で使用できる文字数には制限があります。[GPT でのターゲットとサイズの設定](https://support.google.com/dfp_premium/bin/answer.py?hl=ja&amp;answer=1697712)を参照してください。

## サーバー側の統合 {#server-side-integration}

[!DNL GPT] を使用して [!DNL Google Ad Manager] でサーバー側の統合を設定する場合は、Audience Manager コンサルタントまたはカスタマーケアにお問い合わせください。[!DNL Google Ad Manager] アカウントのネットワーク ID と Audience Link ID を提供する必要があります。

>[!IMPORTANT]
>
>Web ページが [Accelerated Media Pages](https://www.ampproject.org/)（[!DNL AMP]）ライブラリを実行している場合、Audience Manager でサーバー側の統合を使用する必要があります。[!DNL AMP] を使用していて、[!DNL AMP] によるクライアント側の統合がある場合、サーバー側の統合に移行する必要があります。移行については、Audience Manager コンサルタントまたはカスタマーケアにお問い合わせください。

>[!MORELIKETHIS]
>
>* [GPT API リファレンスガイド](https://support.google.com/dfp_premium/bin/answer.py?hl=ja&amp;answer=1650154)

