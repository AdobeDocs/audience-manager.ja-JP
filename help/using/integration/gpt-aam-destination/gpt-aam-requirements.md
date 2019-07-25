---
description: クライアント側またはサーバー側の統合を通じて、絞り込んだセグメントを DFP に送信できます。この両方の方法に関する要件と関連情報を以下に示します。
seo-description: クライアント側またはサーバー側の統合を通じて、適格なセグメントを DFP に送信できます。この両方の方法に関する要件と関連情報を以下に示します。
seo-title: Google サイト運営者タグ（GPT）を使用して DFP にセグメントを送信する際の要件と方法
solution: Audience Manager
title: Google サイト運営者タグ（GPT）を使用して DFP にセグメントを送信する際の要件と方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Google サイト運営者タグ（GPT）を使用して DFP にセグメントを送信する際の要件と方法{#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

You can send qualified segments to [!DNL DFP] either through a client-side or through a server-side integration. この両方の方法に関する要件と関連情報を以下に示します。

## クライアント側の統合 {#client-side-integration}

クライアント側の統合では、Audience Manager で [!DNL GPT] 宛先を設定する必要があります。[!DNL GPT]を Audience Manager 宛先として設定する場合、次の点を考慮してください。

* **追加[!UICONTROL DIL]:** ターゲットにするすべてのページに [!UICONTROL Data Integration Library (DIL)] コードをデプロイします。[!UICONTROL DIL] は Audience Manager のセグメントデータとユーザー ID を、ターゲット化のため [!DNL GPT] が使用する Cookie に書き込みます。

* **作成[!UICONTROL Cookie Destination]:**[!DNL GPT] は、Audience Managerでcookieベースの宛先として設定する必要があります。

* **Cookie チェックコードの実装**：[!DNL GPT] の `.setTargeting` API メソッドを、推奨される [Cookie チェックコード](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)でラップします。このコードにより、`.setTargeting`.メソッドを呼び出す前に有効な AAM Cookie が検索されるので、エラーが回避されます。

* **`AamGpt`関数の追加：**`AamGpt` コードは Audience Manager の Cookie からデータをキャプチャして、[!DNL GPT]に送信します。[Google サイト運営者タグ用の Audience Manager コード](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)（`AamGpt`）をページの最上部または `<head>` コードブロック内に配置します。

   >[!NOTE]
   >
   >独自のコードを使用して Audience Manager の Cookie データを読み取る場合、`AamGpt` 関数は必要ありません。

* **Audience Manager に配信ログを送信：**&#x200B;セグメントの配信レポート（オプション）が必要である場合、インプレッションレベルの配信データが含まれる日単位のログを Audience Manager に送信します。The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager は [!DNL FTP] を介してこれらを受け取ることができます。

### GPT に送信されるのは認定されたセグメントのみ

[!DNL GPT] に渡されるデータの量は、特定のユーザーが認定するセグメントの数によって異なります。例えば、100 件の Audience Manager セグメントを設定したとします。サイト訪問者がそのうち 5 件を認定した場合、その 5 件のセグメントだけが [!DNL GPT] に送信されます（100 件全部ではありません）。

>[!NOTE]
>
>There are no limits to the number of key-values you can send, but the [!DNL Google] request [!DNL URL] does have limits to the number of characters it can accept. [GPT でのターゲットとサイズの設定](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712)を参照してください。

## サーバー側の統合 {#server-side-integration}

[!DNL GPT] を使用して [!DNL DFP] でサーバー側の統合を設定する場合は、Audience Manager コンサルタントまたはカスタマーケアにお問い合わせください。[!DNL DFP] アカウントネットワークIDとオーディエンスリンクIDを指定する必要があります。

>[!IMPORTANT]
>
>If your web pages are running the [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) library, you must use the server-side integration with Audience Manager. [!DNL AMP]を使用していて、[!DNL AMP] によるクライアント側の統合がある場合、サーバー側の統合に移行する必要があります。移行については、Audience Manager コンサルタントまたはカスタマーケアにお問い合わせください。

>[!MORE_LIKE_THIS]
>
>* [GPT API リファレンスガイド](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

