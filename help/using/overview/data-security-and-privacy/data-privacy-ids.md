---
description: このドキュメントでは、データのプライバシーリクエストで使用できるAudience Manager IDのタイプについて説明します。
seo-description: このドキュメントでは、データのプライバシーリクエストで使用できるAudience Manager IDのタイプについて説明します。
seo-title: 'Audience Manager 識別子（ID） '
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: 'Audience Manager 識別子（ID） '
translation-type: tm+mt
source-git-commit: 30352749e926d5730e9cc8beef3936c9ed6d2986

---


# Audience Manager 識別子（ID） {#aam-ids}

When submitting [data privacy requests](data-privacy-requests.md) to Adobe Audience Manager, you must include one of the identifiers (IDs) listed below. ID形式について詳しくは、Audience Manager IDのインデッ [クスを参照してください](../../reference/ids-in-aam.md)。

## Adobe Audience Manager の一意のユーザー ID

* **User ID**: `aam_uuid`
* **定義**：Adobe Audience Manager の一意のユーザー ID
* **名前空間 ID**：0

**JSON の例**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

>[!NOTE]
>
>You can also use the [!DNL CORE] namespace.

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

## Adobe Experience Cloud ID

* **User ID**: `mid`
* **定義**: [!DNL Adobe Experience Cloud ID]旧称または [!DNL Visitor ID][!DNL Marketing Cloud ID]
* **名前空間 ID**：4

>[!NOTE]
>
>You can also use the [!DNL ECID] namespace. See the second [!DNL JSON] example.

**JSON の例**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

## 顧客 ID

**User ID**: `cid`

**定義**:顧客ID。匿名サイト訪問者に対して設定したcookieや、オフラインシステムからの [!DNL CRM] ID、ハッシュ化されたユーザー名など。

**名前空間 ID**：顧客固有。Audience Manager インスタンスから検索します。

**JSON の例**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

## モバイル広告 ID

**User ID**: `d_cid`

**定義**：モバイル広告 ID。

**名前空間 ID**：

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

詳しくは、「[グローバルデータソース](../../features/global-data-sources.md)」を参照してください。

>[!IMPORTANT]
>
> If you are using the Mobile [!DNL SDK], then you should also send the Experience Cloud ID (`MID`) along with mobile advertising IDs for complete Access and Delete responses.

**JSON の例**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

## 統合コード

**User ID**: `d_cid_ic`

**定義**：データソースの統合コード。これは、に対するリクエストで、データソースIDや名前空間IDの代わりに使 [!DNL API] 用できま [!DNL Adobe Experience Cloud Privacy Core Service]す。

**名前空間 ID**：非該当

**JSON の例**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
