---
description: Google サイト運営者タグ（GPT）を使用した Google Ad Manager の統合方法の概要です。
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: 'Google サイト運営者タグ（GPT）を使用した Google Ad Manager の統合 '
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
TQID: https://experienceleague.adobe.com/29V5C3MbEondd3-qWLBfi3jaGid1I1UM9nYIl9nZWVo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 212
ht-degree: 100%

---

# Google サイト運営者タグ（GPT）を使用した [!DNL Google Ad Manager]（旧称 DFP）の統合

Google サイト運営者タグ（GPT）を使用した [!DNL Google Ad Manager] との統合方法の概要が以下の記事に記載されています。サーバー側で統合することも、Audience Manager のセグメントデータを [!DNL Google Ad Manager] に送信するための宛先として GPT を設定することもできます。[!DNL Google Ad Manager] ログファイルを取り込み、Audience Manager でレポートするために必要なステップも確認できます。

* [Google サイト運営者タグ（GPT）を使用して Google Ad Manager にセグメントを送信する際の要件と方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

  クライアント側またはサーバー側の統合を通じて、絞り込んだセグメントを [!DNL Google Ad Manager] に送信できます。この両方のメソッドに関する要件と関連情報を以下に示します。

* [GPT 宛先の作成](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

  認定されたセグメントを、クライアント側（ブラウザー側）の統合またはサーバー側の統合により [!DNL Google Ad Manager] に送信することができます。クライアント側の統合を選択した場合、Audience Manager で Google サイト運営者タグの Cookie ベースの宛先を作成する必要があります。

* [GPT setTargeting API 呼び出しの変更](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

  Google サイト運営者タグの .setTargeting メソッドを呼び出す前に、Audience Manager の Cookie を確認するための if 文を追加します。

* [Google サイト運営者タグ用の Audience Manager コード](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

  AamGpt は、Audience Manager の Cookie データを読み取り、Google サイト運営者タグに情報を送信する JavaScript 関数です。
