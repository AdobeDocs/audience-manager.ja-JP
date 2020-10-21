---
description: Audience Manager の訪問者認証ステータスによって、新しい特性情報が訪問者の認証済みプロファイルに書き込まれるか、デバイスプロファイルに書き込まれるかが決まります。Audience Manager は、イベント呼び出しの訪問者 ID 認証ステータス UNKNOWN および LOGGED_OUT を同じ方法で処理します。
keywords: dpm.demdex.net
seo-description: Audience Manager の訪問者認証ステータスによって、新しい特性情報が訪問者の認証済みプロファイルに書き込まれるか、デバイスプロファイルに書き込まれるかが決まります。Audience Manager は、イベント呼び出しの訪問者 ID 認証ステータス UNKNOWN および LOGGED_OUT を同じ方法で処理します。
seo-title: Audience Manager の訪問者認証ステータス
solution: Audience Manager
title: Audience Manager の訪問者認証ステータス
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 100%

---


# Audience Manager の訪問者認証ステータス {#visitor-authentication-states-in-audience-manager}

Audience Manager の訪問者認証ステータスによって、新しい特性情報が訪問者の認証済みプロファイルに書き込まれるか、デバイスプロファイルに書き込まれるかが決まります。Audience Manager は、イベント呼び出しの訪問者 ID 認証ステータス UNKNOWN および LOGGED_OUT を同じ方法で処理します。

[!DNL Experience Cloud] ID サービス v1.5 以降の `setCustomerID` メソッドには、オプションの `AuthState` オブジェクトが含まれています。`AuthState` は、訪問者の[認証ステータス](https://docs.adobe.com/content/help/ja-JP/id-service/using/reference/authenticated-state.html)に従って訪問者を識別します。[!DNL Audience Manager] での適合する特性の処理は、呼び出し、およびセグメント化に使用する[プロファイル結合ルール](../features/profile-merge-rules/merge-rules-dashboard.md)に渡される認証ステータスによって異なります。

## 認証ステータス：UNKNOWN {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>リクエスト値 </p> </th> 
   <th colname="col2" class="entry"> <p> 認証済みプロファイルから情報を<b>読み取る</b> </p> </th> 
   <th colname="col3" class="entry"> <p> 認証済みプロファイルに新しい特性を<b>書き込む</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>○（「Authenticated Option Merge Rule」が「Last Authenticated Profiles」の場合） </p> </td> 
   <td colname="col3" morerows="1"> <p>×（特性データはデバイスプロファイルに追加される） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>×（「Authenticated Option Merge Rule」が「Current Authenticated Profiles」または「No Authenticated Profile」の場合） </p> </td> 
  </tr> 
 </tbody> 
</table>

サンプルの呼び出し（認証ステータスに対応するリクエスト値はハイライト表示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 認証ステータス：AUTHENTICATED {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>リクエスト値 </p> </th> 
   <th colname="col2" class="entry"> <p> 認証済みプロファイルから情報を<b>読み取る</b> </p> </th> 
   <th colname="col3" class="entry"> <p> 認証済みプロファイルに新しい特性を<b>書き込む</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>○（「Authenticated Option Merge Rule」が「Current Authenticated Profiles」または「Last Authenticated Profiles」の場合） </p> </td> 
   <td colname="col3" morerows="1"> <p>○（特性データは認証済みプロファイルに追加される） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>×（「Authenticated Option Merge Rule」が「No Authenticated Profile」の場合） </p> </td> 
  </tr> 
 </tbody> 
</table>

サンプルの呼び出し（認証ステータスに対応するリクエスト値はハイライト表示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 認証ステータス：LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>リクエスト値 </p> </th> 
   <th colname="col2" class="entry"> <p> 認証済みプロファイルから情報を<b>読み取る</b> </p> </th> 
   <th colname="col3" class="entry"> <p> 認証済みプロファイルに新しい特性を<b>書き込む</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> ○（「Authenticated Option Merge Rule」が「Last Authenticated Profiles」の場合） </td> 
   <td colname="col3" morerows="1"> <p>×（特性データはデバイスプロファイルに書き込まれる） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> ×（「Authenticated Option Merge Rule」が「Current Authenticated Profiles」または「No Authenticated Profile」の場合） </td> 
  </tr> 
 </tbody> 
</table>

サンプルの呼び出し（認証ステータスに対応するリクエスト値はハイライト表示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] は、[CID と UUID](../reference/ids-in-aam.md) 間の ID 同期を 3 つすべてのケースで実行します。

>[!MORELIKETHIS]
>
>* [顧客 ID と認証状態](https://docs.adobe.com/content/help/ja-JP/id-service/using/reference/authenticated-state.html)

