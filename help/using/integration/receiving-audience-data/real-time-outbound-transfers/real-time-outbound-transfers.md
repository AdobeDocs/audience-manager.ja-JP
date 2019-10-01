---
description: リアルタイムの送信データ転送プロセスでは、POST メソッドで渡された一連の JSON オブジェクトとしてユーザーデータを返します。
seo-description: リアルタイムの送信データ転送プロセスでは、POST メソッドで渡された一連の JSON オブジェクトとしてユーザーデータを返します。
seo-title: リアルタイム送信データ転送
solution: Audience Manager
title: リアルタイム送信データ転送
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# リアルタイム送信データ転送 {#real-time-outbound-data-transfers}

The outbound real-time data transfer process delivers user data as a series of [!DNL JSON] formatted messages to a destination platform.

<!-- c_outbound_json.xml -->

## 推奨事項

To use this method, the destination platform must meet the following requirements:

* It must provide an endpoint  that can scale to receive a high volume of messages from Audience Manager;[!DNL URL]
* It must accept data in  format ();[!DNL JSON]`Content-type: application/json`
* It must accept secure  data transfers. `HTTPS`[!DNL Audience Manager] will not send messages through the unsecure  protocol.`HTTP`

## 頻度

このデータ転送方法は、ユーザーがセグメントの対象となるときにほぼリアルタイムでデータを送信できます。Real-time messages are only delivered while the user is online and actively visible to the Audience Manager Edge network. Optionally, this method can also send batches of offline or onboarded data as frequently as every 24-hours.

## Batch Transfers

リアルタイム転送とバッチ転送の両方が同じエンドポイントに送信され、同じメッセージ形式を使用します。 バッチ転送が有効な場合、宛先プラットフォームは、バッチメッセージの配信中にメッセージ量にスパイクを確認します。 リアルタイムメッセージを通じて送信されるセグメントの資格の多くは、バッチメッセージで繰り返されます。 Batch transfers will include only the segment qualifications (or un-qualifications) that have changed since the last batch was delivered.

## レート制限

配信されるメッセージのスループットにレート制限は設定されません。 レート制限を設定すると、データが失われる可能性があります。

## 必要な応答

デフォルトでは、受信サーバーは、正常な受信を示すために `200 OK` コードを返す必要があります。他のコードは失敗と解釈されます。この応答は、3000 ミリ秒以内に返されることを想定しています。In response to a failure, [!DNL Audience Manager] will make one retry attempt only.

## パラメーター

返された [!DNL JSON] データファイルの要素の定義を次の表に示します。

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
   <td colname="col3"> <p>User.DataPartner_UUIDプロパティ内の、メッセージに含まれるデバイスIDのタイプを示すID。 </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID（GAID）：<code>20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID（IDFA）：<code>20915</code> </li>
     <li>Web/Cookie ID:目的地のプラットフォームによって異なる</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p>宛先プラットフォームのターゲットアカウントを表します。 このIDは、宛先プラットフォームから取得されます。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>Audience Managerの「destination」オブジェクトのID。 このIDはAudience Managerから取得されます。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p><code>POST</code> リクエストのユーザーの合計数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>配列 </p> </td> 
   <td colname="col3"> <p>ユーザーオブジェクトの配列。デフォルトでは、各メッセージに1 ～ 10人のユーザーが含まれ、最適なメッセージサイズを維持します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> UUID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p>宛先プラットフォームのUUIDまたはグローバルデバイスID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 配列 </td> 
   <td colname="col3"> このデバイスが確認された<span class="keyword"> Audience Manager</span> 地域 ID。例えば、デバイスがパリ（ヨーロッパ）であるアクティビティをおこなった場合、地域 ID は <code>6</code> になります。<a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地域 ID、場所、ホスト名</a>を参照してください。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>配列 </p> </td> 
   <td colname="col3"> <p>セグメントオブジェクトの配列。リアルタイムメッセージの場合、配列にはユーザーが属するすべてのセグメントが含まれます。 バッチ・メッセージの場合、配列には最後のバッチ以降のセグメント変更のみが含まれます。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>セグメントの識別子。 ほとんどの場合、これはAudience Managerによって生成されたセグメントID（整数）です。 場合によっては、宛先プラットフォームで許可されている場合、顧客がAudience Manager UI（開いたテキストフィールド）でセグメント識別子を定義でき、このプロパティに反映されます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>セグメント内のユーザーのステータスを定義します。次の値を受け入れます。 </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code>1</code>：アクティブ（デフォルト） </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code>0</code>：非アクティブ、オプトアウト済みまたは非セグメント化。 </li> 
    </ul> <p>以下の場合、ユーザーはセグメントへの認定を解除されます。 </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">セグメントから削除される（セグメントルールに基づいて）。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">セグメントから削除される（セグメントの<a href="../../../features/traits/segment-ttl-explained.md">有効期間</a>に基づいて）。 </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">過去 120 日で確認されなかった場合、非アクティブ状態に移動されます。 </li>
     <li>プライバシー変更のリクエスト([!DNL GDPR])</li>
    </ul> <p><span class="keyword">Audience Manager</span> ID と同期されたすべてのパートナー ID は、ユーザーが非セグメント化されると、<code>"Status":"0"</code> フラグを受け取ります。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>ユーザーセグメントの資格が最も新しく検証された時刻。</p> </td> 
  </tr> 
 </tbody> 
</table>

## セキュリティ

秘密鍵で [HTTP 要求に署名](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md)するか、[!DNL Audience Manager] で [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) プロトコルを使用して認証することで、リアルタイム送信データ転送プロセスを保護できます。

## リクエスト

リアルタイムリクエストは次のようになります。

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
