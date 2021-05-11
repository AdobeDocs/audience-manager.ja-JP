---
description: Audience Managerタグ管理コンポーネントには、クライアントポータル、Adobe Tag Manager(Adobe Experience Platform Launchに代わって廃止)、DIL、Akamai、および制御データベースが含まれます。
seo-description: Audience Managerタグ管理コンポーネントには、クライアントポータル、Adobe Tag Manager(Adobe Experience Platform Launchに代わって廃止)、DIL、Akamai、および制御データベースが含まれます。
seo-title: Tag Management コンポーネント
solution: Audience Manager
title: Tag Management コンポーネント
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: 'システムコンポーネント '
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 67%

---

# Tag Management コンポーネント {#tag-management-components}

Audience Managerタグ管理コンポーネントには、クライアントポータル、Adobe Tag Manager(Adobe Experience Platform Launchに代わって廃止)、DIL、Akamai、および制御データベースが含まれます。

<!-- 

c_comptag.xml

 -->

Audience Manager には次のコンポーネントがあります。

* [クライアントポータル](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL／TIM コンテナ](../../reference/system-components/components-tag-management.md#dil-tim)
* [データ情報ライブラリ（DIL）](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [制御データベース](../../reference/system-components/components-tag-management.md#control-database)

## クライアントポータル  {#client-portal}

クライアントポータルは、タグおよびデータ管理の主要なユーザーインターフェイス（UI）です。ポータルを使用してタグの操作、特性およびセグメントの作成、送信先の設定、およびレポートによるキャンペーンパフォーマンスの監視をおこないます。

## DIL／TIM コンテナ  {#dil-tim}

[!UICONTROL DIL] コンテナは、[!DNL Audience Manager] のデータ収集コードを Web サイトに配置する際に使用されます。[!UICONTROL TIM] は非推奨（廃止予定）となった Tag Insertion Manager です。[!DNL Audience Manager] では使用されなくなりました。代わりに、[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html)の[!DNL Audience Manager]拡張子を使用して、在庫のページに配置するコンテナコードを設定し生成します。

## データ統合ライブラリ（DIL）{#dil}

[Data Information Library](../../dil/dil-overview.md)（DIL）は、Web サイトからデータを収集するための自己完結型の API モジュールです。[!UICONTROL DIL] を使用することで、データ収集、統合、Cookie 値の読み込み、およびページデータのリカバリのための専用コードを記述する手間を省くことができます。[!UICONTROL DIL] はこれらのアクションを自動で実行します。これに加えて、[!UICONTROL DIL] はコンパクトです。自己完結型のコードライブラリであるので、情報収集に必要なコーディング量を削減できます。さらには、[!UICONTROL DIL] は、[!DNL Audience Manager] と [!DNL Adobe] Experience Cloud の他の製品を統合する際に使用できます。

## Akamai {#akamai}

[!DNL Audience Manager] は [Akamai](https://www.akamai.com/jp/ja/about/) を使用して [!UICONTROL TIM (Tag Insertion Manager)] と呼ばれるアドビのタグ管理プラットフォームからコンテナコードをホストおよび配信します。ただし、[!UICONTROL TIM]を使用したコードの導入は、[!DNL Adobe Experience Platform Launch]を優先して段階的に廃止されました。

## 制御データベース {#control-database}

制御データベースは、以下をおこないます。

* ポータルからのクライアント入力を処理します（特性および宛先の作成など）。
* コンテナテンプレートやターゲットパブリッシング iFrame の作成に使用されるデータなどを Akamai に送信します。
* UI のレポーティングシステムにデータを返します。
