---
description: リアルタイムの送信データ転送プロセスでは、POST メソッドで渡された一連の JSON オブジェクトとしてユーザーデータを返します。
seo-description: リアルタイムの送信データ転送プロセスでは、POST メソッドで渡された一連の JSON オブジェクトとしてユーザーデータを返します。
seo-title: リアルタイム送信データ転送
solution: Audience Manager
title: リアルタイム送信データ転送
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 100%

---


# リアルタイム送信データ転送 {#real-time-outbound-data-transfers}

リアルタイムの送信データ転送プロセスでは、ユーザーデータを一連の [!DNL JSON] 形式のメッセージとして宛先プラットフォームに配信します。

<!-- c_outbound_json.xml -->

## 推奨事項

この方法を使用するには、宛先プラットフォームが以下の要件を満たしている必要があります。

* Audience Manager から大量のメッセージを受信するために拡大縮小できるエンドポイント [!DNL URL] を提供する必要があります。
* [!DNL JSON] 形式（`Content-type: application/json`）のデータを受け入れる必要があります。
* 安全な `HTTPS` データ転送を受け入れる必要があります。[!DNL Audience Manager] では、安全でない `HTTP` プロトコルを使用してメッセージを送信しません。

## 頻度

このデータ転送方法は、ユーザーがセグメントの対象となるときにほぼリアルタイムでデータを送信できます。リアルタイムメッセージは、ユーザーがオンラインで、Audience Manager Edge ネットワークに対してアクティブに表示できる場合にみ配信されます。オプションで、この方法では、24 時間ごとに、オフラインまたはオンボード済みデータのバッチを送信することもできます。

## バッチ転送

リアルタイム転送およびバッチ転送は、両方とも、同じエンドポイントに送信され、同じメッセージ形式を使用します。バッチ転送が有効な場合、バッチメッセージが配信される際に、宛先プラットフォームでメッセージ量にスパイクが表示されます。リアルタイムメッセージで送信されたセグメント資格の多くは、バッチメッセージで繰り返されます。バッチ転送は、最後のバッチが配信されてから変更されたセグメント資格（または無資格）のみを含みます。

## レート制限

配信されたメッセージのスループットに対してレート制限は設定されていません。レート制限を設定すると、データ損失につながる可能性があります。

## 必要な応答

デフォルトでは、受信サーバーは、正常な受信を示すために `200 OK` コードを返す必要があります。他のコードは失敗と解釈されます。この応答は、3000 ミリ秒以内に返されることを想定しています。失敗の場合、[!DNL Audience Manager] は、1 回のみ再試行します。

## パラメーター

次のテーブルは、宛先に送信する [!DNL JSON] データファイル内の要素を定義します。

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> データタイプ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>ProcessTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>リクエストが実行された時間。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>デバイス ID のタイプを示す ID は、メッセージ内の、User.DataPartner_UUID プロパティに含まれます。 </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID（GAID）：<code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID（IDFA）：<code> 20915</code> </li>
     <li>Web／Cookie ID：宛先プラットフォームによって異なる</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p>宛先プラットフォームのターゲットアカウントを表します。この ID は、宛先プラットフォームから生成されます。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>Audience Manager「宛先」オブジェクトの ID。この ID は、Audience Manager から生成されます。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p><code> POST</code> リクエストのユーザーの合計数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>配列 </p> </td> 
   <td colname="col3"> <p>ユーザーオブジェクトの配列。デフォルトでは、各メッセージは、最適なメッセージサイズを維持するために、1 ～ 10 ユーザーを含みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> UUID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p>宛先プラットフォーム UUID またはグローバルデバイス ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 配列 </td> 
   <td colname="col3"> このデバイスが確認された<span class="keyword"> Audience Manager</span> 地域 ID。例えば、デバイスがパリ（ヨーロッパ）であるアクティビティをおこなった場合、地域 ID は <code> 6</code> になります。<a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地域 ID、場所、ホスト名</a>を参照してください。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>配列 </p> </td> 
   <td colname="col3"> <p>セグメントオブジェクトの配列。リアルタイムメッセージの場合、配列には、ユーザーが属するすべてのセグメントが含まれます。バッチメッセージの場合、配列には、最後のバッチ以降に変更されるセグメントのみが含まれます。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmnent.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>セグメントの識別子。ほとんどの場合、これは、Audience Managerで生成されたセグメント ID です（整数）。場合によっては、宛先プラットフォームが許可している場合、お客様は、Audience Manager ユーザーインターフェイス（テキストフィールドを開く）でセグメント識別子を定義でき、それがこのプロパティに反映されます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>セグメント内のユーザーのステータスを定義します。以下の値を受け入れます。 </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>：アクティブ（デフォルト） </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>：非アクティブ、オプトアウト済みまたは非セグメント化。 </li> 
    </ul> <p>以下の場合、ユーザーはセグメントへの認定を解除されます。 </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">セグメントから削除された（セグメントルールに基づいて）。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">セグメントから削除された（セグメントの<a href="../../../features/traits/segment-ttl-explained.md">有効期間</a>に基づいて）。 </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">過去 120 日の間確認されず、非アクティブ状態に移行した。 </li>
     <li>プライバシー変更リクエスト（例：<span class="keyword">GDPR</span>）により削除された</li>
    </ul> <p><span class="keyword">Audience Manager</span> ID と同期されたすべてのパートナー ID は、ユーザーが非セグメント化されると、<code> "Status":"0"</code> フラグを受け取ります。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>最後にユーザーセグメント資格が検証された時間。</p> </td> 
  </tr> 
 </tbody> 
</table>

## セキュリティ

秘密鍵で [HTTP 要求に署名](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md)するか、[!DNL Audience Manager] で [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) プロトコルを使用して認証することで、リアルタイム送信データ転送プロセスを保護できます。

## リクエスト

リアルタイムリクエストは、以下のようになります。

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}
```
