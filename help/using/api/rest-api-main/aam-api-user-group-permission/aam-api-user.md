---
description: ユーザーを管理する（ユーザーオブジェクトの作成、更新、リスト、削除および返却を含む）ための Rest API メソッド。
seo-description: ユーザーを管理する（ユーザーオブジェクトの作成、更新、リスト、削除および返却を含む）ための Rest API メソッド。
seo-title: ユーザー管理 API メソッド
solution: Audience Manager
title: ユーザー管理 API メソッド
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 100%

---


# ユーザー管理 API メソッド {#user-management-api-methods}

ユーザーを管理する（ユーザーオブジェクトの作成、更新、リスト、削除および返却を含む）ための Rest [!DNL API] メソッド。

<!-- c_rest_api_user_man_user.xml -->

## ユーザーの作成 {#create-user}

新しいユーザーを作成するための `POST` メソッド。

<!-- r_rest_api_user_create.xml -->

### リクエスト

`POST /api/v1/users/`

### リクエスト本文のサンプル

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### 応答

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

`isAdmin` が true に設定されている場合、ユーザーがパートナー管理者として作成されます。また、このプロパティでは、ユーザーがパターン管理者であるかどうかを確認することもできます。

ユーザー名が既に使用されている場合は、`409 Conflict` が返されます。

## ユーザーの更新 {#update-user}

ユーザーを更新するための `PUT` メソッド。

<!-- r_rest_api_user_update.xml -->

### リクエスト

`PUT /api/v1/users/`*`<userId>`*

### リクエスト本文のサンプル

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### 応答

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

ユーザー名が既に使用されている場合は、`409 Conflict` が返されます。

## ログインしているユーザーの更新 {#update-logged-in-user}

現在ログインしているユーザーを更新するための `PUT` メソッド。

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>大部分の [!DNL API] メソッドはパートナー管理者しか呼び出せませんが、このメソッドは管理者以外のユーザーでも呼び出すことができます。

### リクエスト

`PUT /self/update`

### リクエスト本文のサンプル

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### 応答

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

ユーザー名が既に使用されている場合は、`409 Conflict` が返されます。

## ログインしているユーザーのパスワードの更新 {#update-logged-in-user-pw}

現在ログインしているユーザーを更新するための `PUT` メソッド。

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>大部分の [!DNL API] メソッドはパートナー管理者しか呼び出せませんが、このメソッドは管理者以外のユーザーでも呼び出すことができます。

### リクエスト

`POST /users/self/update-password`

### リクエスト本文のサンプル

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

成功すると `200 OK` が返されます。いずれかのパスワードに問題がある場合は、`400 Bad Request` が返されます。

## ログインしているユーザーのパスワードのリセット {#reset-logged-in-user-pw}

現在ログインしているユーザーをリセットするための `PUT` メソッド。[!UICONTROL Audience Management] では、システムで生成したパスワードをユーザーに送信します。

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>大部分の [!DNL API] メソッドはパートナー管理者しか呼び出せませんが、このメソッドは管理者以外のユーザーでも呼び出すことができます。

### リクエスト

`POST /self/reset-password`

成功すると `200 OK` が返されます。

## ユーザー ID のユーザーオブジェクトを返す {#return-user-object-for-id}

ユーザー ID のユーザーオブジェクトを返すための `Get` メソッド。

<!-- r_rest_api_user_get_user_obj.xml -->

### リクエスト

`GET /api/v1/users/`*`<userId>`*

### 応答

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## ログインしているユーザーのユーザーオブジェクトを返す {#return-user-object-for-logged-in-user}

現在ログインしているユーザーのユーザーオブジェクトを返すための `Get` メソッド。

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>大部分の [!DNL API] メソッドはパートナー管理者しか呼び出せませんが、このメソッドは管理者以外のユーザーでも呼び出すことができます。

### リクエスト

`GET /api/v1/users/self`

### 応答

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## ユーザーのリスト {#list-users}

ユーザーをリストするための `GET` メソッド。

<!-- r_rest_api_user_list.xml -->

### リクエスト

`GET /api/v1/users/`

クエリパラメーターで複数のグループ ID を指定できます。

`GET /api/v1/users/?groupId=343&groupdId=12`

このクエリは、指定したグループのすべてのユーザーのリストを返します。

### 応答

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## ユーザーの削除 {#delete-users}

ユーザーを削除するための `DELETE` メソッド。

<!-- r_rest_api_user_delete.xml -->

### リクエスト

`DELETE /api/v1/users/`*`<user_id>`*

成功すると `204 No Content` が返されます。競合が発生する場合、`409 Conflict` が返されます。

## ユーザーの一括削除 {#delete-users-bulk}

複数のユーザーを一括削除するための `POST` メソッド。

<!-- r_rest_api_user_delete_bulk.xml -->

### リクエスト

`POST /api/v1/users/bulk-delete`

### リクエスト本文のサンプル

```
{[<user_id_1>, <user_id_2>, ...]}
```
