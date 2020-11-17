---
description: Google Publisher Tags(GPT)を使用したGoogle Ad Managerの統合方法の概要です。
seo-description: Adobe Audience Manager(AAM)でGoogle Publisher Tags(GPT)を使用してGoogle Ad Managerを統合する方法の概要です。
seo-title: Adobe Audience Manager(AAM)でGoogle Publisher Tags(GPT)を使用してGoogle Ad Managerを統合する
title: 'Google Publisher Tags（GPT）を使用した Google Ad Manager の統合 '
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 50%

---


# Integrate [!DNL Google Ad Manager] (formerly DFP) using Google Publisher Tags (GPT)

The articles listed below provide an overview of how to integrate [!DNL Google Ad Manager] using Google Publisher Tags (GPT). You can use a server-side integration, or you can set up GPT as a destination to send Audience Manager segment data to [!DNL Google Ad Manager]. You will also learn the needed steps to ingest [!DNL Google Ad Manager] log files for reporting in Audience Manager.

* [Google Publisher Tags(GPT)を使用してGoogle Ad Managerにセグメントを送信するための要件と方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   クライアント側またはサーバー側の統合を通じて、絞り込んだセグメントを [!DNL Google Ad Manager] に送信できます。この両方のメソッドに関する要件と関連情報を以下に示します。

* [GPT 宛先の作成](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   認定されたセグメントを、クライアント側（ブラウザー側）の統合またはサーバー側の統合により [!DNL Google Ad Manager] に送信することができます。クライアント側の統合を選択した場合、Audience Manager で Google サイト運営者タグの Cookie ベースの宛先を作成する必要があります。

* [GPT setTargeting API 呼び出しの変更](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Google サイト運営者タグの .setTargeting メソッドを呼び出す前に、Audience Manager の Cookie を確認するための if 文を追加します。

* [Google サイト運営者タグ用の Audience Manager コード](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt は、Audience Manager の Cookie データを読み取り、Google サイト運営者タグに情報を送信する JavaScript 関数です。
