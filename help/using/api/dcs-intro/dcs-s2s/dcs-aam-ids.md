---
description: この節では、DCS 応答を解析して、DCS へのリアルタイム呼び出しに必要な訪問者 ID と地域 ID を取得する方法について説明します。
seo-description: This section describes how to parse a DCS response to retrieve the visitor and region IDs required to make real-time calls to the DCS.
seo-title: Get User IDs and Regions From a DCS Response
solution: Audience Manager
title: DCS 応答からのユーザー ID と地域 ID の取得
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
exl-id: 3c0c5e57-2d59-4938-9bbd-761495142c31
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 100%

---

# DCS 応答からのユーザー ID と地域 ID の取得 {#get-user-ids-and-regions-from-a-dcs-response}

この節では、[!DNL DCS] 応答を解析して、[!DNL DCS] へのリアルタイム呼び出しに必要な訪問者 ID と地域 ID を取得する方法について説明します。

## ユーザー ID と地域 ID {#user-region-ids}

[!DNL DCS] 応答には、サイト訪問者に関するデータが含まれています。[!DNL DCS] へのサーバー間呼び出しをおこなうには、訪問者 ID と地域 ID が必要です。

* ユーザー ID は、データを識別し特定の訪問者に関連付けるのに必要になります。
* 地域 ID が必要なのは、地域サーバー名に関連付けられているからです。地域サーバー名は [!DNL DCS] へのデータ送信に必要になります。[!DNL DCS] では、サイト訪問者に地理的に最も近いデータセンターに情報を保存します。[DCS 地域 ID、場所、ホスト名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)を参照してください。

これらのパラメーターは次のとおりです。コードの&#x200B;*斜体*&#x200B;の部分には実際の情報が入ります。

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> データタイプ </th> 
   <th colname="col3" class="entry"> 例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code></span> </p> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## レスポンスのサンプル {#sample-response}

この単純な応答では、`UUID` と地域 `ID` を示しています。なお、これはサンプルデータにすぎません。実際のログファイルは、より長くより複雑になります。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 次の手順 {#next-steps}

ユーザー ID と地域サーバー名が用意できたら、[!DNL DCS] データの送受信を開始できます。[DCS API 呼び出しの実行](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)を参照してください。
