---
description: このドキュメントでは、データのプライバシーリクエストで使用できる Audience Manager ID のタイプについて説明します。
seo-description: このドキュメントでは、データのプライバシーリクエストで使用できる Audience Manager ID のタイプについて説明します。
seo-title: Audience Manager 識別子（ID）
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Audience Manager 識別子（ID）
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 100%

---


# Audience Manager 識別子（ID）{#aam-ids}

Adobe Audience Manager に対して[データプライバシーリクエスト](data-privacy-requests.md)を送信する際、以下のいずれかの識別子（ID）を含める必要があります。ID 形式について詳しくは、[Audience Manager ID のインデックス](../../reference/ids-in-aam.md)を参照してください。

## Adobe Audience Manager の一意のユーザー ID

* **ユーザー ID**：`aam_uuid`
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
>[!DNL CORE]名前空間を使用することもできます。

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

* **ユーザー ID**：`mid`
* **定義**：[!DNL Adobe Experience Cloud ID]、旧称：[!DNL Visitor ID][!DNL Marketing Cloud ID]
* **名前空間 ID**：4

>[!NOTE]
>
>[!DNL ECID]名前空間を使用することもできます。2 つ目の [!DNL JSON]の記述例を参照してください。

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

**ユーザー ID**：`cid`

**定義**：匿名のサイト訪問者に設定する Cookie やオフラインシステムからの [!DNL CRM] ID やハッシュ化されたユーザー名などの顧客 ID。

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

**ユーザー ID**：`d_cid`

**定義**：モバイル広告 ID。

**名前空間 ID**：

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

詳しくは、「[グローバルデータソース](../../features/global-data-sources.md)」を参照してください。

>[!IMPORTANT]
>
> モバイル[!DNL SDK]をご利用の場合、アクセスおよび削除に関して完全な応答を得るには、モバイル広告 ID と合わせて Experience Cloud ID（`MID`）を送信する必要があります。

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

**ユーザー ID**：`d_cid_ic`

**定義**：データソースの統合コード。これは、[!DNL API] での [!DNL Adobe Experience Cloud Privacy Core Service]に対するリクエストで、データソース ID や名前空間 ID の代わりに使用できま す。

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
