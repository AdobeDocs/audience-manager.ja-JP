---
description: リアルタイムの送信データ転送プロセスでは、POST メソッドで渡された一連の JSON オブジェクトとしてユーザーデータを返します。
seo-description: リアルタイムの送信データ転送プロセスでは、POST メソッドで渡された一連の JSON オブジェクトとしてユーザーデータを返します。
seo-title: リアルタイム送信データ転送
solution: Audience Manager
title: リアルタイム送信データ転送
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# リアルタイム送信データ転送 {#real-time-outbound-data-transfers}

The outbound real-time data transfer process returns user data as a series of [!DNL JSON] objects passed in with a `POST` method.

<!-- c_outbound_json.xml -->

## 推奨事項

このメソッドを使用するには、データパートナーが以下をおこなうことをお勧めします。

* [!DNL JSON] 形式のデータを受け入れる。
* データを返すために `POST` 呼び出しで使用できる URL を提供する。
* セキュリティで保護された `HTTPS` データ転送を受け入れる。[!DNL Audience Manager] は、セキュリティで保護されていない `HTTP` プロトコルでこのファイルを送信しません。

## 頻度

このデータ転送方法は、ユーザーがセグメントの対象となるときにほぼリアルタイムでデータを送信できます。また、この方法は、24 時間ごとの頻度で、オフラインまたはオンボードのデータをまとめて送信できます。

## 必要な応答

デフォルトでは、受信サーバーは、正常な受信を示すために `200 OK` コードを返す必要があります。他のコードは失敗と解釈されます。この応答は、3000 ミリ秒以内に返されることを想定しています。失敗の場合、[!DNL Audience Manager] は、1 回のみ再試行します。

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
   <td colname="col2"> <p>日時 </p> </td> 
   <td colname="col3"> <p>リクエストが実行された時間。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>ファイルに Android または iOS の ID が含まれているかどうかを示す ID。以下の ID 値を使用します。 </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID（GAID）：<code>20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID（IDFA）：<code>20915</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p>データ送信先のシステムで使用されるクライアント ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>宛先パートナーによって割り当てられた ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p><code>POST</code> リクエストのユーザーの合計数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>配列 </p> </td> 
   <td colname="col3"> <p>ユーザーオブジェクトの配列。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> UUID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p>データパートナー UUID。データパートナーが UUID を持っていない場合は、空のままにします。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Regions</i></code> </td> 
   <td colname="col2"> 配列 </td> 
   <td colname="col3"> このデバイスが確認された<span class="keyword"> Audience Manager</span> 地域 ID。例えば、デバイスがパリ（ヨーロッパ）であるアクティビティをおこなった場合、地域 ID は <code>6</code> になります。<a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地域 ID、場所、ホスト名</a>を参照してください。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>配列 </p> </td> 
   <td colname="col3"> <p>セグメントオブジェクトの配列。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>セグメント ID 宛先マッピング。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>ステータス</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>セグメント内のユーザーのステータスを定義します。指定可能な値は次のとおりです。 </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code>1</code>：アクティブ（デフォルト） </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code>0</code>：非アクティブ、オプトアウト済みまたは非セグメント化。 </li> 
    </ul> <p>以下の場合、ユーザーはセグメントへの認定を解除されます。 </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">セグメントから削除される（セグメントルールに基づいて）。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">セグメントから削除される（セグメントの<a href="../../../features/traits/segment-ttl-explained.md">有効期間</a>に基づいて）。 </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">過去 120 日で確認されなかった場合、非アクティブ状態に移動されます。 </li> 
    </ul> <p><span class="keyword">Audience Manager</span> ID と同期されたすべてのパートナー ID は、ユーザーが非セグメント化されると、<code>"Status":"0"</code> フラグを受け取ります。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DateTime</i></code> </td> 
   <td colname="col2"> <p>日時 </p> </td> 
   <td colname="col3"> <p>サイト訪問者が特性の対象として認定された日時。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## セキュリティ

You can secure your real-time outbound data transfer process by [signing HTTP requests](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) using private keys or by having [!DNL Audience Manager] authenticate through the [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) protocol.

## コードサンプル

リアルタイムデータ応答は次のようになります。

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
