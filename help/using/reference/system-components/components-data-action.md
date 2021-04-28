---
description: データアクションのコンポーネントには、顧客データフィード、データ収集サーバー、SFTP／S3／HTTP ベースのパブリッシャー、IRIS およびプロファイルキャッシュサーバーなどがあります。
seo-description: データアクションのコンポーネントには、顧客データフィード、データ収集サーバー、SFTP／S3／HTTP ベースのパブリッシャー、IRIS およびプロファイルキャッシュサーバーなどがあります。
seo-title: データアクションのコンポーネント
solution: Audience Manager
title: データアクションのコンポーネント
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: 'システムコンポーネント '
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
translation-type: ht
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: ht
source-wordcount: '682'
ht-degree: 100%

---

# データアクションのコンポーネント {#data-action-components}

データアクションのコンポーネントには、顧客データフィード、データ収集サーバー、SFTP／S3／HTTP ベースのパブリッシャー、IRIS およびプロファイルキャッシュサーバーなどがあります。

<!-- 

c_compact.xml

 -->

アクションコンポーネントとは、（ここでは便宜的に）[!DNL Audience Manager] とのデータの送受信および処理をおこなうことを可能にするシステムおよびプロセスとします。これらの [!DNL Audience Manager] コンポーネントには以下のようなものがあります。

## 顧客データフィード（CDF）{#cdf}

[!UICONTROL CDF] は、1 時間ごとにお客様に送信されるファイルです。これらのファイルには、ユーザー ID、関連付けられたセグメント ID、特性 ID などのデータが含まれます。詳しくは、[顧客データフィードの概要](../../features/cdf-files.md)を参照してください。

## データ収集サーバー（DCS）{#dcs}

[データ収集コンポーネント](../../reference/system-components/components-data-collection.md)を参照してください。

## SFTP／S3 {#sftp-s3}

[!UICONTROL SFTP/S3] パブリッシャーは [!UICONTROL Outbound Feed Converter] から同期済み ID データを取得します。これらのファイルが準備できたら、[!UICONTROL SFTP/S3 publishers]はこれらのデータをクライアントによって指定された宛先に送信します。これらのファイルには、[!DNL Audience Manager] ユーザー ID （UUID）が下記の項目と 1 対多でマッピングされた、同期された ID データが含まれます。

* デバイス ID／データプロバイダー ID（DPUUID）
* 適合したセグメント ID
* 特性 ID

[!DNL Audience Manager] をご利用のお客様は、[!UICONTROL SFPT/S3 publishers]を直接制御する機能にアクセスできません。お客様はデータを作成して宛先に送信する際に、このサービスを間接的に使用します。[!UICONTROL SFTP/S3] システムとは基本的に、スケジュールされた間隔で自動実行されるジョブプロセスです。

## IRIS {#iris}

[!UICONTROL Iris]とは、瞬く間に移動して神託を伝えるギリシャ神話の登場人物です。[!UICONTROL IRIS] システムも、古代神話のこの登場人物と同じ特性を備えています。現代用語における [!UICONTROL IRIS] とは、低遅延で高頻度の Cookie による同期およびデータ転送サービスを指します。

[!UICONTROL IRIS] では [!UICONTROL SFTP/S3] と同じタイプのデータが処理されます。ただ、[!UICONTROL IRIS] では宛先へのデータ送信が設定された間隔でではなく、リアルタイムでおこなわれるという点が異なります。[!UICONTROL SFTP/S3] ベースのパブリッシャーは HTTP ベースの宛先にデータを送信できず、またリアルタイムのデータ転送向けに設計されていないことから、これらは異なるシステムです。

お客様が直接 [!UICONTROL IRIS] を操作するための UI コントロールは用意されていません。お客様は、データを作成して宛先に送信するとき、および高速データ転送が必要な他のプロセスにおいて間接的に [!UICONTROL IRIS] を操作します。

[!UICONTROL IRIS] のサービスおよび機能の使用例には次のようなものがあります。

* Cookie およびセグメントを高速（30 秒以内）に同期する。[!DNL Audience Manager] の Cookie、パートナーの Cookie およびその両方を同期できます。
* リアルタイムのデータ転送。[!UICONTROL IRIS] は、パートナーまたは他の宛先にセグメントの適合イベントをリアルタイムで送信します。データは JSON 形式で、HTTP `POST` リクエストによって送信されます。

* サーバー間の一括データ転送：[!DNL Audience Manager] で大量のデータを送受信する場合、サーバーがデータ転送でやり取りするシステムは [!UICONTROL IRIS] となります。

* 幅広く使用でき、信頼性の高いフォールトトレラントなインフラストラクチャ。[!UICONTROL IRIS] を使用するシステムには、Amazon SQS、Amazon EC2 および Cassandra などがあります。

**セグメントマッピングルール**

[!UICONTROL IRIS] とセグメント宛先間のトラフィックを最適化するため、[!UICONTROL IRIS] はセグメントをルールセットに基づいて宛先に送信します。

1. **新しいセグメント承認**：デバイスが新しいセグメントを承認すると、[!UICONTROL IRIS] は、そのデバイスに関連するすべてのセグメントを、これらのセグメントにマッピングされたすべての宛先へと送信します。

1. **新しいセグメント不承認**：デバイスがセグメントを承認しない場合、[!UICONTROL IRIS] はそのデバイスに関連するすべてのセグメントの認定と不認定を、これらのセグメントにマッピングされたすべての宛先に送信します。

1. **宛先マッピング更新**：宛先マッピングが更新されると、[!UICONTROL IRIS] は次回 Audience Manager でデバイスが確認される際に、デバイスに関連するすべてのセグメントを、これらのセグメントにマッピングされたすべての宛先へと送信します。

1. **デバイスグラフの更新**：デバイス ID がセグメントの評価に使用されるデバイスグラフで追加または削除されると、[!UICONTROL IRIS] は次回 Audience Manager でデバイスが確認される際に、デバイスに関連するすべてのセグメントを、これらのセグメントにマッピングされたすべての宛先へと送信します。

>[!IMPORTANT]
>
>Audience Manager で上記の更新が 3 日間連続して検出されない場合、[!UICONTROL IRIS] は次回 Audience Manager でデバイスが確認される際にデバイスに関連するすべてのセグメントを、これらのセグメントにマッピングされたすべての宛先へと送信します。

**データファイルの例**

次の例では、[!UICONTROL IRIS] からのリアルタイムなセグメントデータを示します。これは一例にすぎないことにご注意ください。お客様ごとに書式要件が異なるので、その内容は異なる場合があります。

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## プロファイルキャッシュサーバー（PCS） {#pcs}

[データ収集コンポーネント](../../reference/system-components/components-data-collection.md)を参照してください。
