---
description: アドビは、オプトアウト管理に関する業界全体のすべての標準に準拠しています。Audience Manager でサポートされているオプトアウトのタイプについて詳しくは、以降の説明を参照してください。
seo-description: アドビは、オプトアウト管理に関する業界全体のすべての標準に準拠しています。Audience Manager でサポートされているオプトアウトのタイプについて詳しくは、以降の説明を参照してください。
seo-title: オプトアウト管理
solution: Audience Manager
title: オプトアウト管理
uuid: 61b43e0e-bfe3-497e-ade2-6a942a98407e
translation-type: ht
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# オプトアウト管理{#opt-out-management}

アドビは、オプトアウト管理に関する業界全体のすべての標準に準拠しています。Audience Manager でサポートされているオプトアウトのタイプについて詳しくは、以降の説明を参照してください。

## グローバルオプトアウト {#global-opt-out}

グローバルオプトアウトは、すべてのブランドにおける Audience Manager およびその他の Adobe Experience Cloud ソリューションにまたがるオプトアウトです。次の表は、グローバルオプトアウトに使用する手法の一覧です。

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> オプトアウトの対象 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p><a href="https://www.adobe.com/jp/privacy/opt-out.html#customeruse" format="http" scope="external">プライバシーの設定ページ</a>には、エンドユーザーが Adobe Experience Cloud 広告ソリューション（Audience Manager など）によるデータ収集の制御やオプトアウトをおこなうための 1 クリック機能があります。特に、プライバシーの選択肢ページの<a href="https://www.adobe.com/jp/privacy/opt-out.html#customeruse" format="http" scope="external">ビジネス関連の顧客のセクション</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audience Manager に対する直接 API 呼び出し </p> </td> 
   <td colname="col2"> <p>すべての Audience Manager ブランドによるデータ収集からオプトアウトするには、以下のように DCS API を呼び出し、<a href="../../reference/ids-in-aam.md">Audience Manager ユーザー ID</a> を指定します。 </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>その結果、送信された Audience Manager ユーザー ID に対して <code>demdex=NOTARGET</code> および <code>dextp=NOTARGET Cookie</code> が設定されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>モバイルデバイス </p> </td> 
   <td colname="col2"> <p>以下のデバイスに対するオプトアウト設定とプライバシー設定を確認します。 </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/ja_JP/mobile/android/privacy.html" format="https" scope="external"> Android デバイス </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/ja_JP/mobile/ios/privacy.html" format="https" scope="external"> iOS デバイス </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

エンドユーザーは、アドビの業界標準パートナーの Web サイトを訪問してグローバルデータ収集からオプトアウトすることもできます。

* [Digital Advertising Alliance（DAA）](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative（NAI）](https://optout.networkadvertising.org/?c=1#!/).

上記のオプトアウトリクエストをおこなうと、次の処理がおこなわれます。

* Audience Manager は進行中のすべてのデータ収集、セグメント化、アクティブ化を停止します。
* 120 日後にユーザープロファイルから履歴データが削除されます。

## パートナーレベルのオプトアウト{#partner-opt-out}

パートナーレベルのオプトアウトでは、特定の Audience Manager パートナーによるデータ収集からオプトアウトすることができます。パートナーレベルのオプトアウトでは、後述のとおり[宣言済みID](../../features/declared-ids.md) 呼び出しおよびデバイス ID 呼び出し（下記の節で説明）。

### 宣言された ID 呼び出しを使用するパートナーレベルのオプトアウト

宣言された ID 呼び出しを使用するパートナーレベルのオプトアウトの後：

* [CRM ID](../../reference/ids-in-aam.md) にリンクされている最後のデバイス ID（[Audience Manager の一意のユーザー ID](../../reference/ids-in-aam.md)）は、データ収集からオプトアウトされます。
* Audience Manager は、CRM ID にリンクされている最後のデバイス ID について、進行中のすべてのデータ収集、セグメント化、アクティブ化を停止します。
* 履歴データは削除されません。

<br/>

**オプトアウト呼び出し**

Audience Manager がパートナーレベルのオプトアウトリクエストを受信すると、DCS により返される JSON には[エラーコード 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes) が含まれます。ここには、Audience Manager ユーザー ID ではなく、[!UICONTROL "Encountered opt out tag"] というメッセージが表示されます。

<!-- 

<p> 
 <ul id="ul_65EF2E1ED8F24457A35299E38AFE1DBE"> 
  <li id="li_832D0B507BC64782A5D3662FD5173A37">Audience Manager can pass in a declared ID opt-out alongside an Audience Manager UUID in the URL. </li> 
  <li id="li_D6C41CB385C5401D98156E5A3D79AAEE">The declared ID opt-out is stored in the Profile Cache Server (PCS) on a per-partner basis. There is no platform-level opt-out using declared IDs. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross DCS regions). </li> 
 </ul> </p>

 -->

<!-- 

<p>See <a href="../../overview/data-security-and-privacy/data-privacy.md"> Data Privacy </a> for more information about opting-out of data collection. </p>

 -->



**例**

`d_cid` および `d_cid_ic` のキーと値のペアを使用して宣言済み ID のオプトアウトリクエストを作成できます。`d_dpid` や `d_dpuuid` などの従来のパラメーターはまだ機能しますが、既に廃止されています。詳しくは、 [従来の DPID と DPUUID に代わる CID](../../reference/cid.md) を参照してください。以下の例で、*斜体*&#x200B;の部分には実際の情報が入ります。

**CID および CID_IC を使用したオプトアウト**

説明と構文については、[宣言済み ID の URL 変数および構文](../../features/declared-ids.md#variables-and-syntax)を参照してください。

| オプトアウト方法 | コードサンプル |
|--- |--- |
| データプロバイダー ID およびユーザー ID | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| 統合コードおよびユーザー ID | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| 複数の d_cid および d_cid_ic キー値ペア | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### デバイス ID 呼び出しを使用するパートナーレベルのオプトアウト

[DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) に対して次の呼び出しを行うことにより、ブランドの指定デバイス ID でのデータ収集からオプトアウトできます。

| オプトアウト方法 | コードサンプル |
|--- |--- |
| Audience Manager の一意のユーザー ID（`uuid`） | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Experience Cloud ID（`mid`） | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

詳しくは、[Audience Manager で使用される ID の一覧](/help/using/reference/ids-in-aam.md)の `uuid`、`mid`、および `imsOrgId` を参照してください。

デバイス ID 呼び出しを使用するパートナーレベルのオプトアウトの後：

* デバイス ID がデータ収集からオプトアウトされます。
* Audience Manager は、そのデバイス ID に転送される、パートナーのすべてのデータ収集、セグメント化またはアクティブ化を停止します。
* 履歴データは削除されません。
