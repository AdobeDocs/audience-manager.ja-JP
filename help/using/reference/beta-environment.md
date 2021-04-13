---
description: ベータ環境は、Audience Manager の実装をテストするために使用します。ベータ環境でおこなった変更は実稼動データに影響しません。ベータ環境の使用に関心がある場合は、Audience Manager パートナーソリューションの担当者にお問い合わせください。
keywords: サンドボックス
seo-description: ベータ環境は、Audience Manager の実装をテストするために使用します。ベータ環境でおこなった変更は実稼動データに影響しません。ベータ環境の使用に関心がある場合は、Audience Manager パートナーソリューションの担当者にお問い合わせください。
seo-title: ベータ環境
solution: Audience Manager
title: ベータ環境
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: リファレンス
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 100%

---

# ベータ環境 {#beta-environment}

ベータ環境は、Audience Manager の実装をテストするために使用します。ベータ環境でおこなった変更は実稼動データに影響しません。ベータ環境の使用に関心がある場合は、Audience Manager パートナーソリューションの担当者にお問い合わせください。

## 概要

ベータ環境は、実験的または未リリースの機能を持たない、実稼働環境の正確な複製です。実稼働環境のログイン資格情報は、ベータ環境でも有効です。

**更新のスケジュール**

ベータ環境は毎月末のオフピーク時間に更新されます。

**送信トラフィック**

ベータ環境では、送信トラフィックは有効になっていません。

<!-- 

Added re: AAM-30826.

 -->

## エンドポイント



| サービス | URL／ホスト名 | アクセス方法 |
|--- |--- | --- |
| S3 | Audience Manager パートナーソリューション担当者またはカスタマーケアにお問い合わせください。 | ベータインスタンス用の Amazon S3 バケットを設定するには、Audience Manager パートナーソリューション担当者またはカスタマーケアにお問い合わせください。[Amazon S3 を使用する利点](../reference/amazon-s3.md)を参照してください。 |
| DCS | `https://dcs-beta.demdex.net/...` | [ベータ環境で DCS にアクセスする方法](../reference/beta-environment.md#access-dcs-beta-environment)を参照してください。 |
| UI | `https://bank-beta.demdex.com` | 実稼働環境の資格情報は、ベータ環境でも有効です。 |
| API | `https://api-beta.demdex.com/...` | 実稼働環境の資格情報は、ベータ環境でも有効です。汎用的な API ユーザーを作成することをお勧めします。[詳細はこちらを参照](../api/rest-api-main/aam-api-getting-started.md#requirements)してください。 |

## ベータ環境で DCS にアクセスする方法 {#access-dcs-beta-environment}

1. curl[ コマンド](https://curl.haxx.se/docs/manpage.html)を使用して DCS 呼び出しをおこないます。curl は、サポートされている様々なプロトコルの中から 1 つを使用して、サーバー間データ転送をおこなうためのツールです。

   例：

   `curl -v https://dcs-beta.demdex.net/event`

1. DCS 応答ヘッダー内の「サンドボックス」を確認し、ベータ版 DCS によって要求が処理されたことを確認します。

   例：

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->
