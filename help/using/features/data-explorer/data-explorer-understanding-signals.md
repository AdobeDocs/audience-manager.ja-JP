---
description: シグナルは、Audience Manager における情報の最小単位です。シグナルは、オンラインプロパティにおけるユーザーインタラクションまたはユーザーアクティビティを表すものであり、Audience Manager に渡され特性ルールで使用されます。
seo-description: シグナルは、Audience Manager における情報の最小単位です。シグナルは、オンラインプロパティにおけるユーザーインタラクションまたはユーザーアクティビティを表すものであり、Audience Manager に渡され特性ルールで使用されます。
seo-title: シグナルについて
title: シグナルについて
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 100%

---


# シグナルについて

シグナルは、Audience Manager における情報の最小単位です。シグナルは、オンラインプロパティにおけるユーザーインタラクションまたはユーザーアクティビティを表すものであり、Audience Manager に渡され特性ルールで使用されます。

[!DNL Audience Manager] では、シグナルはキー値ペアで表されます。例えば、以下のシグナルは、電子機器が掲載されている Web ページに訪問者がアクセスしたことを示します。

* `page = electronics`

[シグナルダッシュボード](../../features/data-explorer/data-explorer-signals-dashboard.md)には、特性の新規作成に利用できる複数のシグナル属性が表示されます。以下に、利用可能なシグナルプロパティの詳細を示します。

* *Key-value pair* には、[!DNL Audience Manager] が受信したシグナルのキー値ペアが示されます。
* *Signal type* は各シグナルのカテゴリを示します。シグナルは、次のいずれかのカテゴリに分類されます。
   * [アクション可能なログファイル](/help/using/integration/media-data-integration/actionable-log-files.md)：メディアパフォーマンスログファイルから受信したリアルタイムシグナル。
   * [!DNL Adobe Analytics]：ご使用の [!DNL Adobe Analytics] アカウントから受信したリアルタイムのシグナル。
   * 一般的なオンラインデータ：オーディエンスのアクティビティによって生成され、アクションにつながるログファイルおよび [!DNL Adobe Analytics] には該当しないリアルタイムデータ。
   * オンボードレコード：バッチデータ転送で受信したデータ。
* *Signal Source* は、シグナルタイプによって異なります。
   * オンボードシグナルの場合、データソース名が表示されます。
   * [!DNL Adobe Analytics] から受信したシグナルの場合、データソースは常にレポートスイートになります。
   * アクションにつながるログファイルおよび一般的なオンラインデータの場合、この情報は表示されません。
* *Total Counts* は、過去 7 日間における [!DNL Audience Manager] でのリアルタイムシグナルの総受信回数を示します。
* *Included in Traits* には、シグナルが特性に含まれているかどうかが示されます。矢印をクリックすると、該当するシグナルを含む特性が表示されます。特性に含まれていないシグナルの場合、この列の値は、[!UICONTROL Create Onboarded Trait] または [!UICONTROL Create Rule-Based Trait] になります。

## シグナルデータの更新頻度

1 日に Audience Manager で処理されるデータ量は多いので、[!UICONTROL Data Explorer] による表示されるシグナルデータの更新は、シグナルタイプに応じた一定の間隔でおこなわれます。

* リアルタイムシグナルデータ（アクションにつながるログファイル、[!DNL Adobe Analytics] データ、一般的なオンラインデータ）は、4～6 時間ごとに更新されます。
* オンボードシグナルデータは、24 時間ごとに更新されます。

## 関連する概念

[シグナル、特性、セグメント](/help/using/reference/signal-trait-segment.md)