---
description: Audience Manager の訪問者認証ステータスによって、新しい特性情報が訪問者の認証済みプロファイルに書き込まれるか、デバイスプロファイルに書き込まれるかが決まります。Audience Manager は、イベント呼び出しの訪問者 ID 認証ステータス UNKNOWN および LOGGED_OUT を同じ方法で処理します。
keywords: dpm.demdex.net
seo-description: Audience Manager の訪問者認証ステータスによって、新しい特性情報が訪問者の認証済みプロファイルに書き込まれるか、デバイスプロファイルに書き込まれるかが決まります。Audience Manager は、イベント呼び出しの訪問者 ID 認証ステータス UNKNOWN および LOGGED_OUT を同じ方法で処理します。
seo-title: Audience Manager の訪問者認証ステータス
solution: Audience Manager
title: Audience Manager の訪問者認証ステータス
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: リファレンス
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: c3c829ef1335d1e073b719f8252103fa578bb4e6
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 100%

---

# Audience Manager の訪問者認証ステータス {#visitor-authentication-states-in-audience-manager}

Audience Manager の訪問者認証ステータスによって、新しい特性情報が訪問者の認証済みプロファイルに書き込まれるか、デバイスプロファイルに書き込まれるかが決まります。Audience Manager は、イベント呼び出しの訪問者 ID 認証ステータス UNKNOWN および LOGGED_OUT を同じ方法で処理します。

[!DNL Experience Cloud] ID サービス v1.5 以降の `setCustomerID` メソッドには、オプションの `AuthState` オブジェクトが含まれています。`AuthState` は、訪問者の[認証ステータス](https://docs.adobe.com/content/help/ja-JP/id-service/using/reference/authenticated-state.html)に従って訪問者を識別します。[!DNL Audience Manager] での適合する特性の処理は、呼び出し、およびセグメント化に使用する[プロファイル結合ルール](../features/profile-merge-rules/merge-rules-dashboard.md)に渡される認証ステータスによって異なります。

## 認証ステータス：UNKNOWN {#auth-status-unknown}

| リクエスト値 | 認証済みプロファイルから情報を読み取る | 認証済みプロファイルに新しい特性を書き込む |
|---|---|---|
| 0 | <ul><li>はい（[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles]の場合）。</li><li>いいえ（[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles]または[!UICONTROL No Authenticated Profile]の場合）。</li></ul> | ×（特性データはデバイスプロファイルに追加される） |

サンプルの呼び出し（認証ステータスに対応するリクエスト値はハイライト表示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 認証ステータス：AUTHENTICATED {#auth-status-authenticated}

| リクエスト値 | 認証済みプロファイルから情報を読み取る | 認証済みプロファイルに新しい特性を書き込む |
|---|---|---|
| 1 | <ul><li>はい（[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] または [!UICONTROL Last Authenticated Profiles] の場合）。</li><li>いいえ（[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile] の場合）。</li></ul> | ○（特性データは認証済みプロファイルに追加される） |

サンプルの呼び出し（認証ステータスに対応するリクエスト値はハイライト表示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 認証ステータス：LOGGED_OUT {#auth-status-logged-out}

| リクエスト値 | 認証済みプロファイルから情報を読み取る | 認証済みプロファイルに新しい特性を書き込む |
|---|---|---|
| 2 | <ul><li>はい（[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles] の場合）。</li><li>いいえ（[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] または [!UICONTROL No Authenticated Profile] の場合）。</li></ul> | ×（特性データはデバイスプロファイルに書き込まれる） |

サンプルの呼び出し（認証ステータスに対応するリクエスト値はハイライト表示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] は、[CID と UUID](../reference/ids-in-aam.md) 間の ID 同期を 3 つすべてのケースで実行します。

>[!MORELIKETHIS]
>
>* [顧客 ID と認証状態](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

