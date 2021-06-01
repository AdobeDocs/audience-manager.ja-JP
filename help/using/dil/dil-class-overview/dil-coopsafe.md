---
description: DIL から Adobe Experience Cloud Device Co-op にデータを送信するかどうかを指定する任意のブール型設定です。
seo-description: DIL から Adobe Experience Cloud Device Co-op にデータを送信するかどうかを指定する任意のブール型設定です。
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
feature: DIL の実装
exl-id: 33dca495-6923-4966-9ec3-8b0fd2f17649
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 100%

---

# isCoopSafe{#iscoopsafe}

DIL から Adobe Experience Cloud Device Co-op にデータを送信するかどうかを指定する任意のブール型設定です。

## 要件 {#requirements}

`isCoopSafe` を使用するには、以下の要件を満たす必要があります。

* [!UICONTROL DIL] v6.11 以降を使用する。
* [Experience Cloud Device Co-op](https://docs.adobe.com/content/help/ja-JP/device-co-op/using/home.html) に参加する。Co-op への参加を検討している場合は、このドキュメントをよく読み、デバイスグラフの作成にデータがどのように使用されるかに関する懸念に `isCoopSafe` で対処できるかどうかを確認する必要があります。

* [!DNL Adobe] コンサルタントに依頼して、Device Co-op アカウントで許可リストまたはブロックリストのフラグを設定する。これらのフラグをセルフサービスで有効にする方法はありません。

## ユースケース {#use-cases}

`isCoopSafe` は、Device Co-op に既に参加しているお客様や、参加を検討しているお客様によるデータ収集に関連した 2 つのユースケースの解決に役立ちます。これらのユースケースは、サイト訪問者のデータが Device Co-op にどのように渡され、デバイスグラフの作成にどのように役立てられるかということに関連しています。これらのユースケースで `isCoopSafe` がデータをどのようにブロックまたは送信するかを次の表で説明します。

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ユースケース </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>認証済み訪問者</b> </p> </td> 
   <td colname="col2"> <p><code> isCoopSafe </code> を <span class="wintitle">DIL</span> コードに追加して、使用規約同意書に同意した（または同意していない）認証済み訪問者のデータを Device Co-op がデバイスグラフの作成にどのように使用するかを管理します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>サードパーティサイトの DIL</b> </p> </td> 
   <td colname="col2"> <p><code> isCoopSafe </code> を <span class="wintitle">DIL</span> コードに追加して、次の場合にサードパーティサイトで使用します。 </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">認証済み訪問者が使用規約同意書に同意したかどうかを確認できない。 </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">Device Co-op によるデバイスグラフの作成でデータがどのように利用されるかを管理する必要がある。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 構文およびコードサンプル {#syntax-code-sample}

**構文：** `isCoopSafe: true | false`

Device Co-op で顧客データを利用するか利用しないかをブール型オプションで指定します。

* `isCoopSafe: true`：モバイル SDK または Web サイトが収集した訪問者データをデバイスグラフの作成に利用&#x200B;*できます*。

* `isCoopSafe: false`：モバイル SDK または Web サイトが収集した訪問者データをデバイスグラフの作成に利用&#x200B;*できません*。

**コードサンプル**

これは、DIL がインスタンス化されるときに設定します。

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## イベント呼び出し POST パラメーター {#post-parameters}

設定したフラグ（`true` または `false`）に応じて、[!UICONTROL DIL] は `isCoopSafe` をこれらの POST パラメーターに変換し、イベント呼び出しで [!DNL Adobe] に送信します。

* `d_coop_safe=1`
* `d_coop_unsafe=1`

POST パラメーターは、ユーザーデータをデバイスグラフに含めてもよいかどうかを [!DNL Experience Cloud] Device Co-op に通知します。次の表で `isCoopSafe` のブール型フラグとイベント呼び出し時に渡される POST パラメーターの関係について説明します。`isCoopSafe` を使用しない場合、イベント呼び出しにおいて、これらのいずれも渡されません。

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定ステータス </th> 
   <th colname="col2" class="entry"> POST パラメーター </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: true </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_safe=1 </code> </p> <p>Device Co-op は訪問者データをデバイスグラフの作成に利用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: false </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_unsafe=1 </code> </p> <p>Device Co-op は訪問者データをデバイスグラフの作成に利用できません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## インスタンス化後の API {#post-instantiation}

これらの API を使用すると `isCoopSafe` のステータスを変更できます。これらを使用すると、ページが更新されない場合にサイトやシングルページアプリで訪問者のインスタンス化後またはログイン後のステータスを変更できます。例えば、ユーザーがサイトやアプリで認証をおこない、後で Device Co-op によるデータ利用を許可する使用規約ポリシーに同意した場合に、これらの API を呼び出す必要があります。

<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopSafe(); </code> </p> </td> 
   <td colname="col2"> <p>後続のすべてのイベント呼び出しで POST パラメーター <code> d_coop_safe=1 </code> を設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>後続のすべてのイベント呼び出しで POST パラメーター <code> d_coop_unsafe=1 </code> を設定します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->
