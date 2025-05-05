---
description: パートナー固有の DIL インスタンスを作成します。
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL create
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 92%

---

# DIL create メソッド {#dil-create}

>[!WARNING]
>
>2023 年 7 月以降、Adobeは [!DNL Data Integration Library (DIL)] と [!DNL DIL] の開発を廃止しました。
>
>既存のお客様は、[!DNL DIL] 実装を引き続き使用できます。 ただし、Adobeはこの先 [!DNL DIL] は発展しません。 お客様は、長期的なデータ収集戦略について [&#128279;](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)0&rbrace;Experience Platform Web SDK&rbrace; を評価することをお勧めします。
>
>2023 年 7 月以降、新しいデータ収集統合機能の実装を検討しているお客様は、代わりに [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) を使用する必要があります。

## DIL create {#dil-create-new}

パートナー専用の [!UICONTROL DIL] インスタンスを作成します。

**関数シグネチャ：**`DIL.create: function (initConfig) {}`

**initConfig の要素**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>`visitorService` プロパティは&#x200B;*常に*&#x200B;必須です。一覧にある他のプロパティは、別途指示がない限りオプションです。

`initConfig` では次の要素を使用できます。

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名前 </th> 
   <th colname="col2" class="entry"> のタイプ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>このプロパティは、ID 同期用に <span class="keyword">Audience Manager</span> で使用されるコンテナ ID を設定します。<span class="wintitle">DIL</span> が複数のサイトにまたがってデプロイされている場合は、<code> containerNSID </code> を設定します。このサイトのそれぞれに、個別のコンテナと ID 同期が設定されます。サイトが 1 つしかない場合は、コンテナ ID はデフォルトで 0 となり、このプロパティを設定する必要はありません。サイトと各サイトのコンテナ ID のリストについては、担当のコンサルタントにお問い合わせください。 </p> <p><a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja" format="https" scope="external">Adobe Experience Platform ID サービス</a>では、プロパティ <code> idSyncContainerID </code> は <span class="wintitle">DIL</span> の <code> containerNSID </code> に対応します。複数のサイトで <span class="wintitle">DIL</span> <i>と</i> ID サービスの両方を使用している場合は、次の点に注意してください。 </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">各サイトで、<code> containerNSID </code> と <code> idSyncContainerID </code> に同じコンテナ ID を設定します。 </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF"><span class="wintitle">DIL</span> と ID サービスの両方が、ID 同期をデータ収集 iFrame に送信しようと試みます。しかし、iFrame は <span class="wintitle">DIL</span> による ID 同期の実行を停止します。これにより、重複が防止されます。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F"><span class="wintitle">DIL</span> のみが <a href="../../features/destinations/destinations.md">URL の宛先</a>にデータを送信します。 </li> 
     </ul> </p> <p><a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html?lang=ja" format="https" scope="external">idSyncContainerID</a> も参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>オブジェクト </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> は、次のいずれかを渡すために使用されます。 </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>：<span class="keyword">Audience Manager</span> により割り当てられたデータパートナー ID。 </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>：ユーザーの一意の ID。 </li> 
    </ul> <p> <p>重要：エンコードされていない ID 値のみを使用してください。エンコードによって、識別子が二重にエンコードされます。 </p> </p> <p> <p>注意：<a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja" format="https" scope="external">Adobe Experience Platform ID サービス</a>を使用している場合、<span class="wintitle">DIL</span> ではなく <code> setCustomerIDs </code> メソッドを使用して顧客 ID を設定します。詳しくは、<a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=ja" format="https" scope="external">顧客 ID と認証状態</a>を参照してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>ブール値 </p> </td> 
   <td colname="col3"> <p> true の場合、<code> Page Load </code> イベントが実行されるまで、すべてのリクエスト（IFRAME、イベント呼び出し、ID 同期、宛先設定）が遅延されます。初期設定は <code> false </code> です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>ブール値 </p> </td> 
   <td colname="col3"> <p> デフォルトは false です。この場合、<span class="keyword">Audience Manager</span> はパートナーのドメインに Cookie （ファーストパーティの Cookie を設定）を設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>ブール値 </p> </td> 
   <td colname="col3"> <p> <p>重要：この要素は、<span class="wintitle">DIL</span> バージョン 8.0（2018 年 8 月にリリース）で非推奨（廃止予定）となりました。代わりに、Adobe Experience Platform ID サービスの <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=ja" format="https" scope="external">関数</a>を使用してください。 </p> </p> <p> <code> true </code> の場合、宛先パブリッシング IFRAME が DOM に付加されたり、宛先が有効になることはありません。初期設定は <code> false </code> です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>ブール値 </p> </td> 
   <td colname="col3"> <p> <p>重要：この要素は、<span class="wintitle">DIL</span> バージョン 8.0（2018 年 8 月にリリース）で非推奨（廃止予定）となりました。代わりに、Adobe Experience Platform ID サービスの <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=ja" format="https" scope="external">関数</a>を使用してください。 </p> </p> <p>ID 同期を無効にします。DIL v6.2 以降と訪問者 ID サービスを使用する場合、ID 同期を無効にする必要があります。この操作は <code> visitorService </code> 関数でおこないます（以下のサンプルコードを参照）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>ブール値 </p> </td> 
   <td colname="col3"> <p> <code> true </code> に設定すると、ページ上のすべての <span class="wintitle">DIL</span> インスタンスのエラーレポートが有効になります。ブール値 <code> true </code> のみ機能します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>ブール値 </p> </td> 
   <td colname="col3"> <p> <p>重要：この要素は、<span class="wintitle">DIL</span> バージョン 8.0（2018 年 8 月にリリース）で非推奨（廃止予定）となりました。代わりに、Adobe Experience Platform ID サービスの <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html?lang=ja" format="https" scope="external">関数</a>を使用してください。 </p> </p> <p> 宛先の公開テンプレートで HTTPS 接続に Akamai を使用するかを指定します。パートナーごとに有効化されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>オブジェクト </p> </td> 
   <td colname="col3"> <p>キー値ペアの値を、別のペアに関連付けます。<a href="../../dil/dil-use-cases.md#map-key-values">キーと値の他のキーへのマッピング</a>を参照してください。v2.4 でリリースされています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p>必須。 </p> <p><code> namespace </code> キー値ペアには、<span class="keyword">Experience Cloud</span> の組織 ID が格納されます。この ID がわからない場合、<span class="keyword">Experience Cloud</span> ダッシュボードの「<span class="wintitle">Administration</span>」セクションで確認できます。このダッシュボードを表示するには、管理者権限が必要です。<a href="../../faq/faq-features.md">製品の特長と機能の FAQ</a> と<a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html?lang=ja" format="https" scope="external">管理 - ユーザー管理と FAQ</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p>必須。 </p> <p> <span class="keyword">Audience Manager</span> で指定されたパートナー名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>ブール値 </p> </td> 
   <td colname="col3"> <p> スクリプトとコールバックを削除します。初期設定は <code> False </code> です。現在の <span class="wintitle">DIL</span> インスタンスにのみ適用されます。v3.3 でリリースされています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>オブジェクト </p> </td> 
   <td colname="col3"> <p><span class="keyword">Audience Manager</span> により返された一意のユーザー ID を Cookie に設定します。<a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props">uuidCookie プロパティ</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>オブジェクト </p> </td> 
   <td colname="col3"> <p><span class="wintitle">DIL</span> 6.2 以降で必要です。 </p> <p> DIL では、<span class="wintitle">Adobe Experience Platform ID サービス</span>で <code> setCustomerIDs </code> 関数を使用して、宣言された ID を <span class="keyword">Audience Manager</span> に渡します。詳しくは、<a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=ja" format="https" scope="external">顧客 ID および認証の状態</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**サンプルコード**

サンプルの [!UICONTROL DIL] 呼び出しとして、次のようなものが挙げられます。

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

成功すると、レスポンスで [!UICONTROL DIL] インスタンスが返されます。コードの設定が適切でない場合や、エラーが発生した場合、処理は失敗し、エラーオブジェクト（スローなし）が返されます。

## uuidCookie プロパティ {#uuidcookie-props}

`uuidCookie` 変数で使用するプロパティを定義します。この変数は `DIL.create` メソッドの一部です。

`uuidCookie` には次のプロパティがあります。

<!-- 

r_dil_uuid_cookie.xml

 -->

| 名前 | 説明 |
|---|---|
| `name` | Cookie の名前（デフォルトは `aam_did`）。 |
| `days` | Cookie の有効期間（デフォルトは 100 日）。 |
| `path` | Cookie のパス（`'/test'` など。デフォルトは `/`）。 |
| `domain` | Cookie が設定されているドメイン（`'adobe.com'` など。デフォルトは `'.'+document.domain`）。 |
| `secure` | データを HTTPS 接続経由でのみ送信するようフラグを設定します。 |

## visitorService プロパティ {#visitor-service-props}

`visitorService` 変数で使用するプロパティを定義します。この変数は `DIL.create` メソッドの一部です。

`visitorService` には次のプロパティがあります。

| 名前 | のタイプ | 説明 |
|---|---|---|
| `namespace` | 文字列 | 必須。Experience Cloud 組織 ID を表します。Experience Cloud コアサービス機能で必要となります。訪問者 ID 機能のインスタンス化に使用するパラメーターと同じです。 |

**コードサンプル:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
