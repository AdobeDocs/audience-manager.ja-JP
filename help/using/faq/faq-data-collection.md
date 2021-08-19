---
description: データ収集と統合に関するよくある質問と問題点の説明です。
seo-description: データ収集と統合に関するよくある質問と問題点の説明です。
seo-title: 'データ収集および製品統合に関するよくある質問 '
solution: Audience Manager
title: 'データ収集および製品統合に関するよくある質問 '
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP アドレス; STFP IP アドレス; FTP アドレス
feature: 管理
exl-id: 2951ab0c-6f1c-4126-b83e-ce4a33c0d4ab
source-git-commit: b8c8f35376c5a8a85fa4eeace7b447385ee9f339
workflow-type: ht
source-wordcount: '1215'
ht-degree: 100%

---

# データ収集および製品統合に関するよくある質問 {#data-collection-and-product-integration-faq}

データ収集と統合に関するよくある質問と問題点の説明です。

<br> 

**書き出した [!DNL DCS] ログファイルで受信トラフィックを [!DNL DCS] トラフィックと区別するには、どうすればよいですか？**

[!UICONTROL Inbound] を通じてオンボーディングされる特性は、[!DNL DCS] で生成されるのと同じように [!UICONTROL Inbound] で生成されます。[!UICONTROL Inbound] を識別するには、次のように、いくつか異なる方法があります。

* リモート IP は 68.67.173.18 に設定されます。
* DomainID は 5325 に設定されます。
* 地域は 0 に設定されます。

<br>

**dpm.demdex.net の許可リストに追加できる IP アドレスのリストを提供していただけますか。**

残念ながら、できません。これらの IP は、[!DNL Amazon Web Services] により地域ごとに動的に割り当てられます。結果的に、[!DNL Audience Manager] では、このアドレスに割り当てることができる IP の範囲を管理していません。

 

**インバウンドおよびアウト SFTP サーバーの許可リストに追加できる IP アドレスを教えてください。**

はい、以下を参照してください。

| サーバー | IP アドレス |
| ---------|----------|
| ftp-in-gtw.demdex.com | 52.3.74.119; 3.233.68.222 |
| ftp-out-gtw.demdex.com | 23.22.232.252; 18.211.109.184 |

 

以下の SFTP サーバーは非推奨です。これらのサーバーを使用して新しいアカウントをプロビジョニングすることはできません。

| サーバー | IP アドレス |
|---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

 

**新しい SFTP サーバーを使用するように Audience Manager インスタンスを設定する方法を教えてください。**

担当の [!DNL Audience Manager] コンサルタントまたはカスタマーケアに問い合わせて、新しい SFTP アカウントを設定してもらってください。

 

**新しい SFTP サーバーでサポートされている認証方法を教えてください。**

新しい SFTP サーバー（`ftp-in-gtw` および `ftp-out-gtw`）では [!DNL OpenSSH Key-Based Authentication] がサポートされます。お客様の [!DNL SSH] キーを生成するか、独自の公開鍵をお客様に提供していただけます。

 

**[!UICONTROL DIL]／[!DNL Analytics] データ統合のコード配置とページ読み込みの要件を教えてください。**

[!DNL Analytics] データを [!DNL Audience Manager] に取り込むには、`s_code` モジュールの後、`s.t()` 関数&#x200B;*より前*&#x200B;に [!UICONTROL DIL] を読み込みます。例えば、次の順でコードを配置するか、読み込まれるようにします。

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] モジュール

3. [!DNL Analytics] `s.t()` 関数

ベストプラクティスは、[!DNL Audience Manager] と [!DNL Analytics] の統合を次の 2 つの方法のどちらかでセットアップすることです。

* [!UICONTROL DIL] を `s_code` に直接組み込む。

* [!UICONTROL DIL] および `s_code` を [!DNL Adobe Experience Platform Launch] を通じて提供する。

詳しくは、[データ統合ライブラリ（DIL）API](../dil/dil-overview.md) を参照してください。

 

**[!DNL Analytics] 変数が [!DNL Audience Manager] イベント呼び出しに含まれていないのはなぜですか？**

これが起こるのは通常、次の場合です。

* ページ上の他のコード要素を使用して DIL を非同期的に読み込むタグ管理システムを通じて、[!UICONTROL DIL] を提供している。
* `s.t()` より先に [!UICONTROL DIL] 関数が読み込まれている。

 

**[!UICONTROL DIL] に対応している [!DNL Analytics] のバージョンは何ですか？**

[!DNL Analytics] を操作するには、[!DNL Adobe AppMeasurement AS] バージョン 20.2（またはそれ以降）と [!UICONTROL DIL] ライブラリバージョン 3.5.2（またはそれ以降）を使用する必要があります。使用している [!DNL Analytics] または [!DNL AppMeasurement] のバージョンが不明な場合は、ページからおこなわれる [!DNL Analytics] 呼び出しを確認してください。バージョン情報は次のように表示されます。

この顧客が [!DNL Analytics] バージョン 24.4 を使用している場合：

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

この顧客が [!DNL AppMeasurement] バージョン 3.5.2 を使用している場合：

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br>

**[!DNL Analytics] の顧客でなくても、ページデータを収集できますか？**

はい。[!UICONTROL DIL] モジュールを使用すれば、[!DNL Analytics] を利用していない場合でもページデータを収集できます。[!UICONTROL DIL] を適切にセットアップすると、次のデータをキャプチャできます。

* メタタグ
* URL および URL ヘッダー
* 検索エンジンタイプ
* キーワード

さらに、クライアントは簡単なオンサイトオブジェクトをデプロイし、[!UICONTROL DIL] でデータを収集するキー値ペアをそのオブジェクトに設定することもできます。これにより、[!DNL Audience Management] を更新しなくても、サイト上の特定のオーディエンスデータポイントを追加したり削除したりできます。パートナーソリューションの担当者と協力して、これを適切にセットアップし、[!DNL DIL] モジュールがこのページオブジェクトを正しく参照するようにしてください。

<br>

**[!UICONTROL DIL] で [!DNL Google Analytics] からデータを収集することはできますか？**

はい。[!UICONTROL DIL] では、一部の [!DNL Google Analytics]（GA）要素を収集し、そのデータを [!DNL Audience Manager] に渡すことができます。以下を参照してください。

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br>

**[!DNL Audience Manager] から生データを取得できますか？ また、その粒度はどの程度ですか？**

はい、[!DNL Audience Manager] では、インベントリに収集した既知のユーザーのデータを取得できます。これには以下が含まれます。

* [!DNL Audience Manager] から割り当てられた一意のユーザー ID（UUID）
* 特性およびセグメント ID
* 未使用シグネチャ
* タイムスタンプ
* ページの URL

<br>

**一方のサイトでデータ収集し、別のサイトで [!DNL Google Ad Manager] を通じてユーザーをターゲットにしたいと考えています。データを収集しない他の資産にもコードをデプロイする必要がありますか？**

いいえ。2 つ目のサイトのデータ収集が不要な場合は、そこに DIL をデプロイする必要はありません。[!DNL Google Ad Manager] 経由で 2 番目のサイトのインベントリにアクセスできれば、最初のサイトのデータ収集を使用して、[!DNL Google Ad Manager] 経由でのターゲット設定をおこなうことができます。

<br>

**最良のサードパーティデータプロバイダーは何ですか？**

各プロバイダーはそれぞれ固有の情報を提供するので、何を求めているかによって、答えは変わります。重複レポート（コストなしで）有効にできるので、どのプロバイダーが自分に最適かを判断するのに役に立ちます。

<br>

**[!DNL Audience Manager] はどのように Cookie を設定し変数を [!DNL Google Ad Manager] に渡しますか？**

[!DNL Audience Manager] では 2 つの Cookie を設定します。一方はセグメント変数を [!DNL Google Ad Manager] 広告タグに送信し、もう一方は一意のユーザー ID（UUID）を設定します。この ID は [!DNL Google Ad Manager] にも読み取られます。UUID を広告タグに追加することで、ユーザーレベルのレポートとオーディエンス検出を実行できます。

<br>

**ユーザーが到達したコンバージョンファンネルのポイントに関する DSP 情報を送信できますか？**

はい。ファンネルデータを送信できますが、DSP にはそれを使用する技術的能力が必要です。DSP は複数のセグメントを確実に処理できる必要があります。それができない場合、特定のセグメントを作成して、コンバージョンの進行状況（例：手順 1 と 2 は完了したが手順 3 は未完）に基づいて、他のセグメントからユーザーを取り出す必要があります。ユーザーをリターゲティングしたり、特定のランディングページに移動させたり、特定のクリエイティブを表示したりできるように、この情報を DSP に送信できます。

<br>

**FTP で送信したデータが [!DNL Audience Manager] で取得されたことを確認するには、どうすればよいですか？**

ファイルの拡張子が `.sync` から `.processed` に変わったら、ファイルが取得されたことになります。これが起こったとき、ファイルは取り込みキューに入っています。また、ファイルがアップロードされたとき、アカウントマネージャーがそれを確認できます。

<br>

**[DCS API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md) の機能をテストしたいと思っています。次のように、イベント呼び出しを送信します。呼び出しには[宣言された ID](../features/declared-ids.md) とシグナルが含まれており、それによって、セットアップ済みの特性とセグメントが認識されます。[!UICONTROL General Reports] と [!UICONTROL Trend Reports] を使用して、特性とセグメントのユーザー数が増加していることを確認できますか？**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

いいえ。この場合は [!UICONTROL General Reports] と [!UICONTROL Trend Reports] は参考にしないでください。

これらのレポートは、レポートの生成時にバックエンドで確認される認証されていないプロファイルレコード（UUID）に基づいてユーザー数を計算します。

[!DNL DCS] の最初の呼び出し時に、宣言された ID はどの UUID にもリンクされて&#x200B;*いません*（つまり、[demdex Cookie](https://docs.adobe.com/content/help/ja-JP/core-services/interface/ec-cookies/cookies-am.html) がクライアント側にありません）。[!DNL DCS] は UUID をランダムに生成し、[!DNL demdex] Cookie を設定してレスポンス呼び出しに含めて渡しますが、この場合、UUID はバックエンドに送信されません。

>[!NOTE]
>
>生成された UUID は、Cookie が設定されているデバイスでさらにアクティビティがトリガーされたときにのみ、バックエンドのデータストレージで実体化されます。

このため、これらのレポートは、呼び出しで宣言された ID によってトリガーされたイベントを反映していません。[!DNL DCS] へのイベントテスト呼び出しでは、UUID、ECID（旧 MID）、モバイルデバイス ID のいずれかを使用することをお勧めします。その後、[!UICONTROL General Reports] と [!UICONTROL Trend Reports] で特性およびセグメント適合を確認できます。

詳しくは、[Audience Manager で使用される ID の一覧](../reference/ids-in-aam.md)を参照してください。

<br>

**ユーザープロファイルがすべての[地域](../api/dcs-intro/dcs-api-reference/dcs-regions.md)に同期されるまで、どれくらいかかりますか？**

ユーザープロファイルがすべての地域にわたって同期するまでに、通常は 24 時間かかります。ただし、稀に、48 時間かかることもあります。

 

**非アクティブな Amazon S3 ユーザーアクセスキーはどうなりますか？**

アドビは、Audience Manager のお客様に Audience Manager [!DNL Amazon S3] バケットのユーザーアクセスキーを提供します。 セキュリティ上の理由から、100 日間操作がないと、キーは自動的に無効になります。

アクセスキーを再度有効にする、または新しいアクセスキーをリクエストするには、カスタマーサポートにお問い合わせください。
