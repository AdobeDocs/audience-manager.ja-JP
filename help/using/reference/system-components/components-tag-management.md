---
description: Audience Manager のタグ管理コンポーネントには、クライアントポータル、Adobe Tag Manager（廃止予定。Adobe Experience Platform Launch を代替として推奨）、DIL、Akamai、制御データベースなどがあります。
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Tag Management コンポーネント
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 81%

---

# Tag Management コンポーネント{#tag-management-components}

Audience Managerタグ管理コンポーネントには、クライアントポータル、Adobe Tag Manager(Adobe Experience Platformタグに代わって廃止 )、DIL、Akamai、制御データベースなどがあります。

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

クライアントポータルは、タグおよびデータ管理の主要なユーザーインターフェイス（UI）です。ポータルを使用してタグの操作、特性およびセグメントの作成、宛先の設定、およびレポートによるキャンペーンパフォーマンスの監視をおこないます。

## DIL／TIM コンテナ {#dil-tim}

[!UICONTROL DIL] コンテナは、[!DNL Audience Manager] のデータ収集コードを Web サイトに配置する際に使用されます。[!UICONTROL TIM] は非推奨（廃止予定）となった Tag Insertion Manager です。[!DNL Audience Manager] では使用されなくなりました。代わりに、 [!DNL Audience Manager] 拡張 [Adobe Experience Platformタグ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) を使用して、在庫のページに配置するコンテナコードを設定および生成します。

## データ統合ライブラリ（DIL） {#dil}

[Data Information Library](../../dil/dil-overview.md)（DIL）は、Web サイトからデータを収集するための自己完結型の API モジュールです。[!UICONTROL DIL] を使用することで、データ収集、統合、Cookie 値の読み込み、およびページデータのリカバリのための専用コードを記述する手間を省くことができます。[!UICONTROL DIL] はこれらのアクションを自動で実行します。これに加えて、[!UICONTROL DIL] はコンパクトです。自己完結型のコードライブラリであるので、情報収集に必要なコーディング量を削減できます。さらには、[!UICONTROL DIL] は、[!DNL Audience Manager] と [!DNL Adobe] Experience Cloud の他の製品を統合する際に使用できます。

## Akamai {#akamai}

[!DNL Audience Manager] は [Akamai](https://www.akamai.com/jp/ja/about/) を使用して [!UICONTROL TIM (Tag Insertion Manager)] と呼ばれるアドビのタグ管理プラットフォームからコンテナコードをホストおよび配信します。ただし、[!UICONTROL TIM] によるコードデプロイメントは廃止され、[!DNL Adobe Experience Platform Tags] で置き換えられました。

## 制御データベース {#control-database}

制御データベースは、以下をおこないます。

* ポータルからのクライアント入力を処理します（特性および宛先の作成など）。
* コンテナテンプレートやターゲットパブリッシング iFrame の作成に使用されるデータなどを Akamai に送信します。
* UI のレポーティングシステムにデータを返します。
