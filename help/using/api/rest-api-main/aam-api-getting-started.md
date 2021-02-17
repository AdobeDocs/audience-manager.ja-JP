---
description: 一般的な要件、認証、オプションのクエリパラメーター、リクエスト URL およびその他の参考資料についての情報です。
seo-description: 一般的な要件、認証、オプションのクエリパラメーター、リクエスト URL およびその他の参考資料についての情報です。
seo-title: REST API の使用の手引き
solution: Audience Manager
title: REST API の使用の手引き
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: ab8745a8ba24154793201893a39a039b5a098833
workflow-type: tm+mt
source-wordcount: '1860'
ht-degree: 100%

---


# [!DNL REST] [!DNL APIs] の使用の手引き {#getting-started-with-rest-apis}

一般的な要件、認証、オプションのクエリパラメーター、リクエスト [!DNL URLs] およびその他の参考資料についての情報です。

<!-- c_rest_api_overview.xml -->

## API の要件と推奨事項 {#api-requirements-recommendations}

 [!DNL Audience Manager] を使用する際に留意すべき事項の説明です。[!DNL API]

<!-- aam-api-requirements.xml -->

[Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) コードを操作する場合は、以下の点に注意してください。

* **リクエストパラメーター：**&#x200B;特に指定のない限り、すべてのリクエストパラメーターが必要となります。
* **リクエストヘッダー**：[Adobe I/O](https://www.adobe.io/) トークンを使用する場合、`x-api-key` ヘッダーを提供する必要があります。[!DNL API] キーは、[サービスアカウント統合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)ページの手順に従って取得できます。
* **[!DNL JSON]コンテンツタイプ：** コード内で、`content-type: application/json` *および* `accept: application/json` を指定してください。
* **要求と応答：**&#x200B;適切な形式の [!DNL JSON] オブジェクトとして要求を送信してください。[!DNL Audience Manager] は [!DNL JSON] 形式のデータで応答します。サーバーの応答には要求されたデータもしくはステータスコード、またはその両方を含めることができます。
* **アクセス：**&#x200B;担当の[!DNL Audience Manager] コンサルタントによって、[!DNL API] 要求をおこなうために必要なクライアント ID およびキーが提供されます。
* **ドキュメントおよびコードサンプル：** *斜体* のテキストは、[!DNL API] データを作成または受け取る際に指定または渡される変数を示します。*斜体*&#x200B;のテキストを独自のコード、パラメーターまたは他の必要な情報に置き換えてください。

## 認証 {#authentication}

[!DNL Audience Manager] [!DNL REST APIs] は、2 つの認証方法をサポートします。

* [JWT（サービスアカウント）認証](#jwt)（[Adobe I/O](https://www.adobe.io/) を使用）[!DNL Adobe I/O] は、アドビの開発者エコシステムおよびコミュニティです。これには、[Adobe I/O 開発者ツールと API ](https://www.adobe.io/apis/experienceplatform.html)、および[すべてのアドビ製品用 API](https://www.adobe.io/apis.html) が含まれます。[!DNL Adobe] [!DNL APIs] を設定して使用する場合は、次の方法をお勧めします。
* [OAuth 認証（非推奨）](#oauth)：この方法は非推奨ですが、既存の [!DNL OAuth] 統合を使用するお客様は、引き続きこの方法を使用できます。

>[!IMPORTANT]
>
>認証方法に応じて、リクエスト [!DNL URLs] を調整する必要があります。使用すべきホスト名について詳しくは、[環境](#environments)の節を参照してください。

## [!DNL JWT]（[!DNL Service Account]）Adobe I/O による認証 {#jwt}

### Adobe I/O の概要 {#adobeio}

[!DNL Adobe I/O] は、アドビの開発者エコシステムおよびコミュニティです。これには、[Adobe I/O 開発者ツールと API ](https://www.adobe.io/apis/experienceplatform.html)、および[すべてのアドビ製品用 API](https://www.adobe.io/apis.html) が含まれます。

[!DNL Adobe] [!DNL APIs] を設定して使用する場合は、次の方法をお勧めします。

### 前提条件 {#prerequisites}

[!DNL JWT] 認証を設定する前に、[Adobe I/O](https://www.adobe.io/) の [Adobe Developer Console](https://console.adobe.io/)にアクセスできることを確認します。アクセスリクエストについては、組織の管理者にお問い合わせください。

### 認証 {#auth}

次の手順に従って、[!DNL Adobe I/O] を使用して [!DNL JWT (Service Account)] 認証を設定します。

1. [Adobe Developer Console](https://console.adobe.io/) にログインします。
1. [サービスアカウント接続](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)の手順に従います。
   * [手順 2：サービスアカウント認証を使用してプロジェクトに API を追加する](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)で、[!DNL Audience Manager] [!DNL API] オプションを選択します。
1. [手順 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) の指示に基づいて最初の [!DNL API] 呼び出しをおこない、接続を試します。

>[!NOTE]
>
>[!DNL Audience Manager] [!DNL REST APIs] を自動的に設定および操作するため、プログラムによって [!DNL JWT] を生成できます。詳しい手順については、[JWT（サービスアカウント）認証](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)を参照してください。

## [!DNL OAuth] 認証（廃止予定）{#oauth}

>[!WARNING]
> [!DNL Audience Manager]  [!UICONTROL REST API] トークン認証および [!DNL OAuth 2.0] を使用した更新は、非推奨（廃止予定）となりました。
>
> 代わりに、[JWT（サービスアカウント）認証](#jwt-service-account-authentication-jwt)を使用してください。

[!DNL Audience Manager] [!UICONTROL REST API] では、[!DNL OAuth 2.0] 標準規格に従って、トークンの認証と更新をおこないます。以下のセクションでは、[!DNL API] を認証し、使用を開始する方法について説明します。

### 汎用の [!DNL API] ユーザーの作成 {#requirements}

 [!DNL Audience Manager] を使用するための個別の技術的なユーザーアカウントを作成することをお勧めします。これは、組織の特定ユーザーに関連していない、または関連付けられていない一般的なアカウントです。[!DNL API]このような [!DNL API] ユーザーアカウントによって 2 つのことが可能になります。

* [!DNL API] の呼び出し元のサービスを特定する（アドビの [!DNL API] を使用するアプリケーションからの呼び出し、または [!DNL API] 要求をおこなう他のツールからの呼び出しなど）。
* [!DNL API] への妨げられることのないアクセスを提供する。特定ユーザーが退社すると、そのユーザーに関連するアカウントが無効になることがあります。すると、利用可能な [!DNL API] コードを使用できなくなってしまいます。特定の従業員に関連付けられていない汎用のアカウントを使用することで、この問題を回避できます。

このようなアカウントのユースケースとして、[一括管理ツール](../../reference/bulk-management-tools/bulk-management-intro.md)を参照してください。これをおこなうためには、ユーザーアカウントに [!DNL API] へのアクセス権が付与されている必要があります。特定のユーザーに対して権限を追加するのではなく、適切な資格情報、キー、および [!DNL API] 呼び出し用の暗号鍵を持つ汎用の [!DNL API] ユーザーアカウントを作成します。これは、 [!DNL Audience Manager] [!DNL API]を使用する独自のアプリケーションを開発する場合にも便利です。

担当の [!DNL Audience Manager] コンサルタントにご相談のうえ、[!DNL API] 専用のユーザーアカウントの設定をおこなってください。

### パスワード認証ワークフロー {#password-authentication-workflow}

パスワード認証により、 [!DNL REST API] へのアクセスが保護されます。以下の手順は、ブラウザーで [!DNL JSON] クライアントからパスワードを認証する際のワークフローの概要を示しています。

>[!TIP]
>
>更新トークンをデータベースに保存する場合は、アクセスと更新トークンを暗号化します。

#### 手順 1：[!DNL API] アクセスのリクエスト

パートナーソリューションソリューションに問い合わせます。[!DNL API] クライアント ID と暗号鍵が通知されます。この ID と暗号鍵により、[!DNL API] での認証をおこないます。

注意：更新トークンを受け取る場合は、[!DNL API] アクセスをリクエストする際にその旨を申告してください。

#### ステップ 2：トークンのリクエスト

[!DNL JSON] クライアントでトークンのリクエストを渡します。リクエストをおこなうには、次の手順に従います。

* `POST` メソッドを使用して `https://api.demdex.com/oauth/token` を呼び出します。
* クライアント ID と暗号鍵を、base-64 でエンコードされた文字列に変換します。この変換では、ID と暗号鍵はコロンで区切ります。例えば、資格情報 `testId : testSecret` は `dGVzdElkOnRlc3RTZWNyZXQ=` に変換されます。
* [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` および `Content-Type: application/x-www-form-urlencoded` で渡します。ヘッダーの例を次に示します。<br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=`<br/>`Content-Type: application/x-www-form-urlencoded`
* リクエストの本文を次のように設定します。
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### ステップ 3：トークンの受け取り

[!DNL JSON]応答にはアクセストークンが含まれています。応答は次のようになっています。

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in` キーは、アクセストークンの有効期間を秒単位で表しています。トークンが公開される場合、ベストプラクティスとして、有効期間を短く設定し、公開時間を制限します。

### 更新トークン  {#refresh-token}

更新トークンは、元のトークンの有効期間が終了した後、[!DNL API] アクセスを更新します。リクエストがあれば、パスワードワークフローの応答 [!DNL JSON] に更新トークンが含まれます。更新トークンを受け取らない場合、パスワード認証プロセスにより新しいトークンを作成します。

また、更新トークンを使用して、既存のアクセストークンの有効期間が終了する前に新しいトークンを作成することもできます。

アクセストークンの有効期間が終了している場合、`401 Status Code` が生成され、応答のヘッダーが次のようになります。

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

次の表は、更新トークンを使用してブラウザーの [!DNL JSON] クライアントから新しいアクセストークンを作成するワークフローを示しています。

#### ステップ 1：新しいトークンのリクエスト

優先 [!DNL JSON] クライアントで更新トークンのリクエストを渡します。リクエストをおこなうには、次の手順に従います。

* `POST` メソッドを使用して `https://api.demdex.com/oauth/token` を呼び出します。
* クライアント ID と暗号鍵を、base-64 でエンコードされた文字列に変換します。この変換では、ID と暗号鍵はコロンで区切ります。例えば、資格情報 `testId : testSecret` は `dGVzdElkOnRlc3RTZWNyZXQ=` に変換されます。
* HTTP ヘッダー `Authorization:Basic <base-64 clientID:clientSecret>` と `Content-Type: application/x-www-form-urlencoded` を渡します。ヘッダーの例を次に示します。<br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* リクエストの本文で、`grant_type:refresh_token` を指定し、前のアクセスリクエストで受け取った更新トークンを渡します。リクエストは次のようになっています。<br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### ステップ 2：新しいトークンの受け取り

[!DNL JSON] 応答に新しいアクセストークンが含まれます。応答は次のようになっています。

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### 認証コードと暗黙的な認証  {#authentication-code-implicit}

[!DNL Audience Manager] は、認証コードを暗黙的な認証をサポートしています。[!UICONTROL REST API]これらのアクセス方法を利用するには、ユーザーが `https://api.demdex.com/oauth/authorize` にログインし、アクセス権と更新トークンを取得する必要があります。

## 認証済み [!DNL API] リクエストの作成 {#authenticated-api-requests}

認証トークン受信後の [!DNL API] メソッドの呼び出しの要件。

使用可能な [!DNL API] メソッドに対する呼び出しをおこなうには：

* `HTTP` ヘッダーで `Authorization: Bearer <token>` を設定します。
* [JWT（サービスアカウント）認証](#jwt)を使用する場合、`x-api-key` ヘッダー（`client_id` と同じ）を提供する必要があります。`client_id` は、[Adobe I/O 統合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)ページから取得できます。
* 必要な [!DNL API] メソッドを呼び出します。

## オプションの [!DNL API] クエリパラメーター {#optional-api-query-parameters}

オブジェクトのすべてのプロパティを返すメソッドに使用可能なオプションのパラメーターを設定します。

オブジェクトの[!DNL API]すべて&#x200B;*のプロパティを返す* メソッドで、これらのオプションパラメーターを使用できます。そのクエリを [!DNL API] に渡す際に、リクエスト文字列にこれらのオプションを設定します。

| パラメーター | 説明 |
|--- |--- |
| `page` | ページ番号を返します。番号は 0 から始まります。 |
| `pageSize` | リクエストによって返された応答結果の番号を設定します（10 がデフォルト）。 |
| `sortBy` | 指定された [!DNL JSON] プロパティに従って、結果を並べ替えて返します。 |
| `descending` | 結果を降順で並べ替えて返します。`ascending` がデフォルトです。 |
| `search` | 検索パラメーターとして使用する指定文字列に基づいて結果を返します。例えば、項目の任意のフィールドに「Test」という語があるすべてのモデルの結果を探したい場合は、サンプルリクエストは次のようになります。   `GET https://aam.adobe.io/v1/models/?search=Test`「[!DNL get all]」メソッドで返されるすべての値を検索できます。 |
| `folderId` | 指定されたフォルダー内の[!UICONTROL traits]のすべての ID を返します。すべてのメソッドに対して使用できるわけではありません。 |
| `permissions` | 指定された権限に基づいて、セグメントのリストを返します。`READ` がデフォルトです。権限には以下のものがあります。<ul><li>`READ`：セグメントに関する情報を返して表示します。</li><li>`WRITE`：`PUT` を使用してセグメントを更新します。</li><li>`CREATE`：`POST` を使用してセグメントを作成します。</li><li>`DELETE`：セグメントの削除。基になる特性がある場合、その特性へのアクセス権が必要です。例えば、特性を削除する場合、セグメントに属する特性を削除する権限が必要です。</li></ul><br>複数の権限を個別のキーと値のペアで指定します。例えば、`READ` および `WRITE` 権限だけを持っているセグメントのリストを返すには、`"permissions":"READ"`、`"permissions":"WRITE"` を渡します。 |
| `includePermissions` | （[!DNL Boolean]）`true` に設定して、セグメントの権限を返します。初期設定は `false` です。 |

### ページオプションに関する注意

ページ情報が指定&#x200B;*されていない*&#x200B;場合、リクエストは、プレーンな [!DNL JSON] 結果を配列で返します。ページ情報が指定&#x200B;*されている*&#x200B;場合、返されるリストは、合計結果と現在のページに関する情報を含んだ [!DNL JSON] オブジェクトにラッピングされます。ページオプションを使用したサンプルリクエストは次のようになります。

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

リクエストの [!DNL URLs]、ステージング環境および実稼動環境、バージョンの説明です。

## リクエスト [!DNL URLs] {#request-urls}

次の表は、[!DNL API] リクエストを渡すためのリクエスト [!DNL URLs] のリストを、メソッド別に示しています。

使用する認証方法に応じて、次の表に従ってリクエスト [!DNL URLs] を調整する必要があります。

### [!DNL JWT] 認証のリクエスト [!DNL URLs] {#request-urls-jwt}

| [!DNL API] メソッド | リクエスト [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | 特性：`https://aam.adobe.io/v1/folders/traits /`<br>セグメント：`https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### [!DNL OAuth] 認証のリクエスト [!DNL URLs]（廃止予定）{#request-urls-oauth}

| [!DNL API] メソッド | リクエスト [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | 特性：`https://api.demdex.com/v1/folders/traits /`<br>セグメント：`https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## 環境 {#environments}

[!DNL Audience Manager] [!DNL API] では、複数の作業環境にアクセスできます。これらの環境では、使用中の実稼動データに影響することなく、個別のデータベースについてコードをテストすることができます。次の表は、使用可能な [!DNL API] 環境と、対応するリソースホスト名のリストです。

使用する認証方法に応じて、次の表に従って環境 [!DNL URLs] を調整する必要があります。

| 環境 | ホスト名（[!DNL JWT] 認証） | ホスト名（[!DNL OAuth] 認証） |
|---|---|---|
| **実稼動** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **ベータ** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>[!DNL Audience Manager] ベータ環境は、実稼動環境の小規模なスタンドアロンバージョンです。テストするデータはすべてこの環境で入力および収集する必要があります。

## バージョン  {#versions}

これらの [!DNL API] では、新しいバージョンが定期的にリリースされています。新しいリリースでは、[!DNL API] バージョン番号が増加しています。リクエスト [!DNL URL] では、バージョン番号は次の例のように `v<version number>` として参照されます。

`https://<host>/v1/...`

## レスポンスコードの定義 {#response-codes-defined}

[!DNL Audience Manager] [!UICONTROL REST API] によって返される `HTTP` ステータスコードおよび応答テキスト。

| レスポンスコード ID | レスポンスのテキスト | 定義 |
|---|---|---|
| `200` | `OK` | リクエストは正常に処理されました。必要があれば、予期されたコンテンツまたはデータを返します。 |
| `201` | `Created` | リソースが作成されました。`PUT` および `POST` リクエストに対して返されます。 |
| `204` | `No Content` | リソースが削除されました。レスポンス本文は空白になります。 |
| `400` | `Bad Request` | サーバーがリクエストを理解できませんでした。通常は、構文が正しくないことが原因です。リクエストを確認して、再試行してください。 |
| `403` | `Forbidden` | このリソースへのアクセス権がありません。 |
| `404` | `Not Found` | 指定されたパスでリソースが見つかりません。 |
| `409` | `Conflict` | リソースの状態に競合が発生しているので、リクエストを完了できません。 |
| `500` | `Server Error` | サーバーで予期しないエラーが発生し、リクエストを完了できません。 |

>[!MORELIKETHIS]
>
>* [JWT（サービスアカウント）認証](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth 認証](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 Simplified](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

