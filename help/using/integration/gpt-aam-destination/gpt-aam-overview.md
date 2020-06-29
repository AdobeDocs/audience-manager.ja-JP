---
description: Google Publisher Tags（GPT）を使用した DFP の統合方法の概要です。
seo-description: Adobe Audience Manager（AAM）で Google Publisher Tags（GPT）を使用した DFP の統合方法の概要です。
seo-title: Adobe Audience Manager（AAM）で Google Publisher Tags（GPT）を使用した DFP の統合
title: Google サイト運営者タグ（GPT）を使用した DFP の統合
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 100%

---


# Google サイト運営者タグ（GPT）を使用した DFP の統合

Google サイト運営者タグ（GPT）を使用した DFP との統合方法の概要が以下の記事に記載されています。サーバー側で統合することも、Audience Manager のセグメントデータを DFP に送信するための宛先として GPT を設定することもできます。DFP ログファイルを取り込み、Audience Manager でレポートするために必要なステップも確認できます。

* [Google サイト運営者タグ（GPT）を使用して DFP にセグメントを送信する際の要件と方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   クライアント側またはサーバー側の統合を通じて、適格なセグメントを DFP に送信できます。この両方のメソッドに関する要件と関連情報を以下に示します。

* [GPT 宛先の作成](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   認定されたセグメントを、クライアント側（ブラウザー側）の統合、またはサーバー側の統合により DFP に送信することができます。クライアント側の統合を選択した場合、Audience Manager で Google サイト運営者タグの Cookie ベースの宛先を作成する必要があります。

* [GPT setTargeting API 呼び出しの変更](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Google サイト運営者タグの .setTargeting メソッドを呼び出す前に、Audience Manager の Cookie を確認するための if 文を追加します。

* [Google サイト運営者タグ用の Audience Manager コード](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt は、Audience Manager の Cookie データを読み取り、Google サイト運営者タグに情報を送信する JavaScript 関数です。
