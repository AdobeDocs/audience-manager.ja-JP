---
description: 一般的な要件、認証、オプションのクエリパラメーター、リクエスト URL およびその他の参考資料についての情報です。
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: REST API の使用の手引き
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 622664170f2a76039bcf2333bde43ce9e60b6af2
workflow-type: tm+mt
source-wordcount: '2558'
ht-degree: 73%

---

# [!DNL REST] [!DNL APIs] の使用の手引き  {#getting-started-with-rest-apis}

一般的な要件、認証、オプションのクエリパラメーター、リクエスト [!DNL URLs] およびその他の参考資料についての情報です。

## API の要件とレコメンデーション {#api-requirements-recommendations}

[Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) コードを操作する場合は、以下の点に注意してください。

* **リクエストパラメーター：**&#x200B;特に指定のない限り、すべてのリクエストパラメーターが必要となります。
* **リクエストヘッダー**：[Adobe Developer](https://www.adobe.io/) トークンを使用する場合、`x-api-key` ヘッダーを指定する必要があります。[!DNL API] キーは、[サービスアカウント統合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)ページの手順に従って取得できます。
* **[!DNL JSON]コンテンツタイプ：** コード内で、`content-type: application/json` *および* `accept: application/json` を指定してください。
* **要求と応答：**&#x200B;適切な形式の [!DNL JSON] オブジェクトとして要求を送信してください。[!DNL Audience Manager] は [!DNL JSON] 形式のデータで応答します。サーバーの応答には要求されたデータもしくはステータスコード、またはその両方を含めることができます。
* **アクセス：**&#x200B;担当の [!DNL Audience Manager] コンサルタントによって、[!DNL API] 要求をおこなうために必要なクライアント ID およびキーが提供されます。
* **ドキュメントおよびコードサンプル：** *斜体* のテキストは、[!DNL API] データを作成または受け取る際に指定または渡される変数を示します。*斜体*&#x200B;のテキストを独自のコード、パラメーターまたは他の必要な情報に置き換えてください。

## 認証 {#authentication}

[!DNL Audience Manager] は、3 つの認証方法をサポートする [!DNL REST APIs] 要があります。

* [!BADGE  推奨 ]{type=positive}[2}Developer Console](#oauth-adobe-developer) を使用した {OAuth サーバー間Adobe](https://www.adobe.io/)。 [[!DNL Adobe Developer] は、アドビの開発者エコシステムおよびコミュニティです。これには[すべてのアドビ製品の API](https://developer.adobe.com/apis/) が含まれます。[!DNL Adobe] [!DNL APIs] を設定および使用する場合は、この方法をお勧めします。 [OAuth サーバー間Adobe](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) について詳しくは、認証開発者ドキュメントを参照してください。
* [!BADGE  非推奨 ]{type=negative}[JWT （サービスアカウント）認証 ](#jwt)[Adobe開発者コンソールを使用 ](https://www.adobe.io/)。 [!DNL Adobe Developer] は、アドビの開発者エコシステムおよびコミュニティです。これには[すべてのアドビ製品の API](https://developer.adobe.com/apis/) が含まれます。
* [!BADGE  非推奨 ]{type=negative}[ 従来の OAuth 認証 ](#oauth-deprecated)。 この方法は非推奨ですが、既存の [!DNL OAuth] 統合を使用するお客様は、引き続きこの方法を使用できます。

>[!IMPORTANT]
>
>認証方法に応じて、リクエスト [!DNL URLs] を調整する必要があります。使用すべきホスト名について詳しくは、[環境](#environments)の節を参照してください。

## Adobe Developerを使用した OAuth サーバー間認証 {#oauth-adobe-developer}

この節では、以下のフローチャートに示すように、Audience ManagerAPI 呼び出しの認証に必要な資格情報の収集方法を説明します。 必要な資格情報のほとんどは、1 回限りの初期設定で収集できます。 ただし、アクセストークンは 24 時間ごとに更新する必要があります。

![Audience Manager認証のフロー図。](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Adobe Developer の概要 {#developer-overview}

[!DNL Adobe Developer] は、アドビの開発者エコシステムおよびコミュニティです。これには[すべてのアドビ製品の API](https://developer.adobe.com/apis) が含まれます。

[!DNL Adobe] [!DNL APIs] を設定および使用する場合は、この方法をお勧めします。

### 前提条件 {#prerequisites-server-to-server}

[!DNL OAuth Server-to-Server] 認証を設定する前に、[Adobe Developer](https://developer.adobe.com/) で [Adobe Developer Console](https://developer.adobe.com/console/home) にアクセスできることを確認します。アクセスリクエストについては、組織の管理者にお問い合わせください。

### 認証 {#oauth}

次の手順に従って、[!DNL Adobe Developer] を使用して [!DNL OAuth Server-to-Server] 認証を設定します。

1. [Adobe Developer Console](https://developer.adobe.com/console/home) にログインします。
1. [OAuth サーバー間資格情報実装ガイド ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) の手順に従います。
   * [手順 2：サービスアカウント認証を使用してプロジェクトに API を追加する](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)で、[!DNL Audience Manager] [!DNL API] オプションを選択します。
1. [手順 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) の指示に基づいて最初の [!DNL API] 呼び出しをおこない、接続を試します。

>[!NOTE]
>
>[!DNL Audience Manager] [!DNL REST APIs] を自動的に設定して操作するために、プログラムによってクライアントの秘密鍵を回転させることができます。 手順について詳しくは [ 開発者向けドキュメント ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) を参照してください。

### Audience ManagerAPI をプロジェクトに追加する {#add-aam-api-to-project}

[Adobe Developer Console](https://www.adobe.com/go/devs_console_ui) に移動し、Adobe IDでサインインします。 次に、Adobe Developer Console ドキュメントの [ 空のプロジェクトの作成 ](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) チュートリアルで説明されている手順に従います。

新しいプロジェクトを作成したら、**[!UICONTROL Project Overview]** の画面で **[!UICONTROL Add API]** を選択します。

>[!TIP]
>
>複数の組織用にプロビジョニングされている場合は、インターフェイスの右上隅にある組織セレクターを使用して、必要な組織に属していることを確認します。

![ 「API を追加」オプションがハイライト表示されたDeveloper Console画面 ](/help/using/api/rest-api-main/assets/add-api.png)

**[!UICONTROL Add an API]** 画面が表示されます。 Adobe Experience Cloudの製品アイコンを選択してから「**[!UICONTROL Audience Manager API]**」を選択し、「**[!UICONTROL Next]**」を選択します。

![Audience ManagerAPI を選択します ](/help/using/api/rest-api-main/assets/audience-manager-api.png)。

>[!TIP]
>
>**[!UICONTROL View docs]** オプションを選択して、別のブラウザーウィンドウに移動し、完全な [Audience ManagerAPI リファレンスドキュメント ](https://bank.demdex.com/portal/swagger/index.html#) を参照します。

### OAuth サーバー間認証タイプの選択 {#select-oauth-server-to-server}

次に、認証タイプを選択してアクセストークンを生成し、Audience ManagerAPI にアクセスします。

>[!IMPORTANT]
>
>今後サポートされる方法はこれのみなので、**[!UICONTROL OAuth Server-to-Server]** の方法を選択します。 **[!UICONTROL Service Account (JWT)]** メソッドは非推奨です。 JWT 認証方法を使用した統合は 2025 年 1 月 1 日（PT）まで引き続き機能しますが、Adobeでは、その日までに既存の統合を新しい OAuth サーバー間認証方法に移行することを強くお勧めします。

![OAuth 認証方法を選択します ](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)。

### 統合用の製品プロファイルの選択 {#select-product-profiles}

**[!UICONTROL Configure API]** 画面で、目的の製品プロファイルを選択します。 統合のサービスアカウントでは、ここで選択した製品プロファイルを通じて、詳細な機能にアクセスできます。

![ 統合用の製品プロファイルを選択します ](/help/using/api/rest-api-main/assets/select-product-profiles.png)。

準備が整ったら、「**[!UICONTROL Save configured API]**」を選択します。

### 資格情報の収集 {#gather-credentials}

API がプロジェクトに追加されると、Audience ManagerAPI へのすべての呼び出しで必要な次の資格情報がプロジェクトの **[!UICONTROL Audience Manager API]** ページに表示されます。

![Developer Consoleに API を追加した後の統合情報 ](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}`（[!UICONTROL Client ID]）
* `{ORG_ID}`（[!UICONTROL Organization ID]）

## アクセストークンの生成 {#generate-access-token}

次の手順では、Audience Manager API 呼び出しで使用する `{ACCESS_TOKEN}` 資格情報を生成します。 `{API_KEY}` と `{ORG_ID}` の値とは異なり、Audience ManagerAPI を引き続き使用するには、新しいトークンを 24 時間ごとに生成する必要があります。 「**[!UICONTROL Generate access token]**」を選択します（下図を参照）。

![ アクセストークンの生成方法を表示 ](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## API 呼び出しのテスト {#test-api-call}

Audience Managerベアラートークンを取得したら、API 呼び出しを実行して、認証 API にアクセスできることをテストします。

1. [API リファレンスドキュメント ](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_) に移動します。
2. **[!UICONTROL Authorize]** を選択し、[ アクセストークンを生成 ](#generate-access-token) 手順で取得したアクセストークンを貼り付けます。

   ![API 呼び出しを許可 ](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. `/datasources` API エンドポイントへのGET呼び出しを実行し、[API リファレンスドキュメント ](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_) に示されているように、グローバルに使用可能なすべてのデータソースのリストを取得します。 「**[!UICONTROL Try it out]**」を選択し、次に「**[!UICONTROL Execute]**」を選択します（下図を参照）。

   ![API 呼び出しの実行 ](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB API リクエスト ]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB  正しいベアラートークンを使用した場合の API 応答 ]


動作するアクセストークンを使用すると、API エンドポイントは、200 応答と、組織がアクセスできるすべてのグローバルデータソースを含む応答本文を返します。

```json
[
  {
    "pid": 1794,
    "name": "testdatasource1",
    "description": "Test data source",
    "status": "ACTIVE",
    "integrationCode": "test_ds1",
    "dataExportRestrictions": [],
    "updateTime": 1595340792000,
    "crUID": 0,
    "upUID": 15910,
    "linkNamespace": false,
    "type": "GENERAL",
    "subIdType": "CROSS_DEVICE_PERSON",
    "inboundS2S": true,
    "outboundS2S": true,
    "useAudienceManagerVisitorID": false,
    "allowDataSharing": true,
    "masterDataSourceIdProvider": true,
    "uniqueTraitIntegrationCodes": false,
    "uniqueSegmentIntegrationCodes": false,
    "marketingCloudVisitorIdVersion": 0,
    "idType": "CROSS_DEVICE",
    "samplingEndTime": 1596550392825,
    "allowDeviceGraphSharing": false,
    "supportsAuthenticatedProfile": true,
    "deviceGraph": false,
    "authenticatedProfileName": "testdatasource1",
    "deviceGraphName": "",
    "customNamespaceId": 29769,
    "customNamespaceCode": "silviu_ds1",
    "customerProfileDataRetention": 62208000,
    "samplingStartTime": 1595340792825,
    "dataSourceId": 29769,
    "containerIds": [],
    "samplingEnabled": false
  },
  {
    "pid": 1794,
    "name": "AAM Test Company Audiences",
    "description": "Automatically generated trait data source",
    "status": "ACTIVE",
    "integrationCode": "adobe-provided",
    "dataExportRestrictions": [
      "PII"
    ],

    [...]
```

>[!ENDTABS]

>[!ENDSHADEBOX]

## [!BADGE  非推奨 ]{type=negative}[!DNL JWT]（[!DNL Service Account]）Adobe Developer を使用した認証 {#jwt}

+++ 認証トークンを取得する、非推奨の [!DNL JWT] （[!DNL Service Account]）方式に関する情報を表示します。

### Adobe Developer の概要 {#adobeio}

[!DNL Adobe Developer] は、アドビの開発者エコシステムおよびコミュニティです。これには[すべてのアドビ製品の API](https://www.adobe.io/apis.html) が含まれます。

[!DNL Adobe] [!DNL APIs] を設定および使用する場合は、この方法をお勧めします。

### 前提条件 {#prerequisites}

[!DNL JWT] 認証を設定する前に、[Adobe Developer](https://www.adobe.io/) で [Adobe Developer Console](https://console.adobe.io/) にアクセスできることを確認します。アクセスリクエストについては、組織の管理者にお問い合わせください。

### 認証 {#auth}

次の手順に従って、[!DNL Adobe Developer] を使用して [!DNL JWT (Service Account)] 認証を設定します。

1. [Adobe Developer Console](https://console.adobe.io/) にログインします。
1. [サービスアカウント接続](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)の手順に従います。
   * [手順 2：サービスアカウント認証を使用してプロジェクトに API を追加する](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)で、[!DNL Audience Manager] [!DNL API] オプションを選択します。
1. [手順 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) の指示に基づいて最初の [!DNL API] 呼び出しをおこない、接続を試します。

>[!NOTE]
>
>[!DNL Audience Manager] [!DNL REST APIs] を自動的に設定および操作するため、プログラムによって [!DNL JWT] を生成できます。詳しい手順については、[JWT（サービスアカウント）認証](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)を参照してください。

### テクニカルアカウントの RBAC 権限

Audience Manager アカウントで[役割ベースのアクセス制御](../../features/administration/administration-overview.md)を使用する場合は、Audience Manager のテクニカルユーザーアカウントを作成し、API 呼び出しをおこなう Audience Manager の RBAC グループに追加する必要があります。

以下の手順に従って、テクニカルユーザーアカウントを作成し、RBAC グループに追加します。

1. `https://aam.adobe.io/v1/users/self` に対して `GET` 呼び出しを実行します。この呼び出しにより、[!UICONTROL Admin Console] の [!UICONTROL Users] ページに表示されるテクニカルユーザーアカウントが作成されます。

   ![テクニカルアカウント](assets/technical-account.png)

1. Audience Manager アカウントにログインし、API 呼び出しをおこなうユーザーグループに[テクニカルユーザーアカウントを追加します](../../features/administration/administration-overview.md#create-group)。

+++

## [!BADGE  非推奨 ]{type=negative}[!DNL OAuth] 認証（廃止予定） {#oauth-deprecated}

+++ 認証トークンを取得する、廃止された従来の [!DNL OAuth] 認証方法に関する情報を表示します。

>[!WARNING]
> [!DNL OAuth 2.0][!DNL Audience Manager] 介した [!UICONTROL REST API] トークンの認証と更新は非推奨（廃止予定）になりました。
>
> 代わりに、[JWT（サービスアカウント）認証](#jwt-service-account-authentication-jwt)を使用してください。

[!DNL Audience Manager] [!UICONTROL REST API] では、[!DNL OAuth 2.0] 標準規格に従って、トークンの認証と更新をおこないます。以下のセクションでは、[!DNL API] を認証し、使用を開始する方法について説明します。

### 汎用の [!DNL API] ユーザーの作成 {#requirements}

[!DNL Audience Manager] [!DNL API]を使用するための個別の技術的なユーザーアカウントを作成することをお勧めします。これは、組織の特定ユーザーに関連していない、または関連付けられていない一般的なアカウントです。このような [!DNL API] ユーザーアカウントによって 2 つのことが可能になります。

* [!DNL API] の呼び出し元のサービスを特定する（アドビの [!DNL API] を使用するアプリケーションからの呼び出し、または [!DNL API] 要求をおこなう他のツールからの呼び出しなど）。
* [!DNL API] への妨げられることのないアクセスを提供する。特定ユーザーが退社すると、そのユーザーに関連するアカウントが無効になることがあります。すると、利用可能な [!DNL API] コードを使用できなくなってしまいます。特定の従業員に関連付けられていない汎用のアカウントを使用することで、この問題を回避できます。

このタイプのアカウントの例やユースケースとして、[ 一括管理ツール ](../../reference/bulk-management-tools/bulk-management-intro.md) を使用して一度に多くのセグメントを変更するとします。 これをおこなうためには、ユーザーアカウントに [!DNL API] へのアクセス権が付与されている必要があります。特定のユーザーに対して権限を追加するのではなく、適切な資格情報、キー、および [!DNL API] 呼び出し用の暗号鍵を持つ汎用の [!DNL API] ユーザーアカウントを作成します。これは、[!DNL Audience Manager] [!DNL API] を使用する独自のアプリケーションを開発する場合にも便利です。

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

### 更新トークン {#refresh-token}

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

### 認証コードと暗黙的な認証 {#authentication-code-implicit}

[!DNL Audience Manager] は、認証コードを暗黙的な認証をサポートしています。[!UICONTROL REST API]これらのアクセス方法を利用するには、ユーザーが `https://api.demdex.com/oauth/authorize` にログインし、アクセス権と更新トークンを取得する必要があります。

+++

## 認証済み [!DNL API] リクエストの作成 {#authenticated-api-requests}

認証トークン受信後の [!DNL API] メソッドの呼び出しの要件。

使用可能な [!DNL API] メソッドに対する呼び出しをおこなうには：

* `HTTP` ヘッダーで `Authorization: Bearer <token>` を設定します。
* [JWT（サービスアカウント）認証](#jwt)を使用する場合、`x-api-key` ヘッダー（`client_id` と同じ）を提供する必要があります。`client_id` については、[Adobe Developer 統合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)ページから取得できます。
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
| `search` | 検索パラメーターとして使用する指定文字列に基づいて結果を返します。例えば、項目の任意のフィールドに「Test」という語があるすべてのモデルの結果を探したい場合は、サンプルリクエストは次のようになります。   `GET https://aam.adobe.io/v1/models/?search=Test`。  「[!DNL get all]」メソッドで返されるすべての値を検索できます。 |
| `folderId` | 指定されたフォルダー内の[!UICONTROL traits]のすべての ID を返します。すべてのメソッドに対して使用できるわけではありません。 |
| `permissions` | 指定された権限に基づいて、セグメントのリストを返します。`READ` がデフォルトです。権限には以下のものがあります。<ul><li>`READ`：セグメントに関する情報を返して表示します。</li><li>`WRITE`：`PUT` を使用してセグメントを更新します。</li><li>`CREATE`：`POST` を使用してセグメントを作成します。</li><li>`DELETE`：セグメントの削除。基になる特性がある場合、その特性へのアクセス権が必要です。例えば、特性を削除する場合、セグメントに属する特性を削除する権限が必要です。</li></ul><br>複数の権限を個別のキーと値のペアで指定します。例えば、`READ` および `WRITE` 権限だけを持っているセグメントのリストを返すには、`"permissions":"READ"`、`"permissions":"WRITE"` を渡します。 |
| `includePermissions` | （[!DNL Boolean]）`true` に設定して、セグメントの権限を返します。初期設定は `false` です。 |

{style="table-layout:auto"}

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

### [!BADGE  のリクエスト [!DNL URLs] ート ] 推奨）{type=positive}[!BADGE  非推奨 ]{type=negative}Adobe Developerによる [!DNL JWT] 認証 {#request-urls-jwt}

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

{style="table-layout:auto"}

### のリクエス [!DNL URLs] リクエスト [!BADGE  非推奨 ]{type=negative}[!DNL OAuth] 認証 {#request-urls-oauth}

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

{style="table-layout:auto"}

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

## バージョン {#versions}

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
