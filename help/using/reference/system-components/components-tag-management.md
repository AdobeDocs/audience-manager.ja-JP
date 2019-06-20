---
description: Audience Manager のタグ管理コンポーネントには、クライアントポータル、Adobe Tag Manager（廃止され Adobe Dynamic Tag Manager および Adobe Launch に置き換わりました）、DIL、Akamai、制御データベースなどがあります。
seo-description: Audience Manager のタグ管理コンポーネントには、クライアントポータル、Adobe Tag Manager（廃止され Adobe Dynamic Tag Manager および Adobe Launch に置き換わりました）、DIL、Akamai、制御データベースなどがあります。
seo-title: タグ管理コンポーネント
solution: Audience Manager
title: タグ管理コンポーネント
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# タグ管理コンポーネント{#tag-management-components}

Audience Manager のタグ管理コンポーネントには、クライアントポータル、Adobe Tag Manager（廃止され Adobe Dynamic Tag Manager および Adobe Launch に置き換わりました）、DIL、Akamai、制御データベースなどがあります。

<!-- 

c_comptag.xml

 -->

Audience Manager には次のコンポーネントがあります。

* [クライアントポータル](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL／TIM コンテナ](../../reference/system-components/components-tag-management.md#dil-tim)
* [データ情報ライブラリ（DIL）](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [制御データベース](../../reference/system-components/components-tag-management.md#control-database)

## クライアントポータル {#client-portal}

クライアントポータルは、タグおよびデータ管理の主要なユーザーインターフェイス（UI）です。ポータルを使用してタグの操作、特性およびセグメントの作成、送信先の設定、およびレポートによるキャンペーンパフォーマンスの監視をおこないます。

## DIL／TIM コンテナ {#dil-tim}

[!UICONTROL DIL] コンテナは、[!DNL Audience Manager] のデータ収集コードを Web サイトに配置する際に使用されます。[!UICONTROL TIM] は廃止された Tag Insertion Manager です。[!DNL Audience Manager] では使用されなくなりました。Instead, you use [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) or the [!DNL Audience Manager] extension in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) to configure and generate container code that you place on pages in your inventory. [!UICONTROL DTM] コンテナは、サイトからデータ [!UICONTROL Data Information Library (DIL)] を収集して送信 [!DNL Audience Manager]するために、と連携します。

## データ統合ライブラリ（DIL）{#dil}

[Data Information Library](../../dil/dil-overview.md)（DIL）は、Web サイトからデータを収集するための自己完結型の API モジュールです。[!UICONTROL DIL] を使用することで、データ収集、統合、Cookie 値の読み込み、およびページデータのリカバリのための専用コードを記述する手間を省くことができます。[!UICONTROL DIL] は、これらのアクションを自動的に実行します。Additionally, [!UICONTROL DIL] is compact. 自己完結型のコードライブラリであるので、情報収集に必要なコーディング量を削減できます。さらには、[!UICONTROL DIL] は、[!DNL Audience Manager] と [!DNL Adobe] Experience Cloud の他の製品を統合する際に使用できます。

## Akamai {#akamai}

[!DNL Audience Manager] では、 [Akamai](https://www.akamai.com/html/about/index.html) を使用して、独自のtag managementプラットフォームからコンテナコードをホストおよび配信 [!UICONTROL TIM (Tag Insertion Manager)]します。However, code deployment with [!UICONTROL TIM] has been phased out in favor of [!UICONTROL Adobe Dynamic Tag Management] and [!UICONTROL Adobe Launch].

## 制御データベース {#control-database}

制御データベースは、以下をおこないます。

* ポータルからのクライアント入力を処理します（特性および送信先の作成など）。
* コンテナテンプレートやターゲットパブリッシング iFrame の作成に使用されるデータなどを Akamai に送信します。
* UI のレポーティングシステムにデータを返します。

