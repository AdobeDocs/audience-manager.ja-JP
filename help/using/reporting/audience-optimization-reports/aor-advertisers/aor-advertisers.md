---
description: Audience Optimization for Advertisers では、自社の有料メディアキャンペーン全体で Audience Manager セグメントによってどの程度パフォーマンス向上を図れるかを確認できます。これらのレポートは、ログレベルのキャンペーンパフォーマンスデータと Audience Manager のセグメント指標を組み合わせることで、セグメントを中心とした最適化および効果的なチャネルミックスを導き出します。
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization for Advertisers
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
TQID: https://experienceleague.adobe.com/U9Rg-4rwjGdqYsjGDlctn0PBuxAlDjwIBtorAnGtqHU
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 406
ht-degree: 99%

---

# 広告主向け[!UICONTROL Audience Optimization]{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] for Advertisers では、自社の有料メディアキャンペーン全体で Audience Manager セグメントによってどの程度パフォーマンス向上を図れるかを確認できます。これらのレポートは、ログレベルのキャンペーンパフォーマンスデータと Audience Manager の[!UICONTROL segment]指標を組み合わせることで、セグメントを中心とした最適化および効果的なチャネルミックスを導き出します。

## データの収集方法 {#data-ingestion-methods}

次のいずれかの方法でこれらのレポートで使用するデータを [!DNL Audience Manager] に送信できます。両方の方法でデータを送信する場合もあります。そうすることで、訪問者に関するより包括的で正確な情報をレポートに取り込むことができます。[!UICONTROL Audience Optimization]レポートを使用するには、イベント呼び出しに[メタデータファイルの概要とマッピング](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)ドキュメントに一覧表示されている&#x200B;*すべて*&#x200B;のパラメーターを含める必要があります。以下に列挙された方法でデータを送信できます。

* ピクセル呼び出し：必要なメタデータパラメーターを [!DNL Audience Manager] に渡すには、[ピクセル呼び出しを使用したキャンペーンのクリックデータのキャプチャ](../../../integration/media-data-integration/click-data-pixels.md)と[ピクセル呼び出しを使用したキャンペーンのインプレッションデータのキャプチャ &#x200B;](../../../integration/media-data-integration/impression-data-pixels.md)を参照してください。

* データファイル：これらのレポートを使用して独自のデータ、または [!DNL Audience Manager] と統合されていないソースからのデータを分析する場合、そのデータのデータファイルとメタデータファイルを作成およびアップロードする必要があります。詳しくは、[オーディエンスの最適化レポートのデータファイル](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)と [オーディエンスの最適化レポートのデータおよびメタデータファイル](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)を参照してください。

## [!UICONTROL Role-Based Access Controls] （RBAC） {#rbac}

表示できるレポートのタイプは、どの [!UICONTROL RBAC] グループに割り当てられているかに応じて異なります。詳しくは、[管理](../../../features/administration/administration-overview.md)と[グループの作成](../../../features/administration/administration-overview.md#create-group)を参照してください。

[!UICONTROL Audience Optimization]で表示するには、[!UICONTROL RBAC] グループに対して特定のデータソースが設定されている必要があります。担当の [!DNL Audience Manager] コンサルタントがお客様に代わってこれらの[!UICONTROL data sources]を設定します。[!UICONTROL RBAC] ユーザーグループに設定された[!UICONTROL data sources]が多いほど、それらのグループメンバーがアクセスできるデータが多くなります。担当のコンサルタントは、これらの[!UICONTROL data sources]のうち少なくとも 1 つを設定します。

* 広告主 [!UICONTROL data source]
* ブランド [!UICONTROL data source]
* プラットフォーム [!UICONTROL data source]

複数の [!UICONTROL RBAC] ユーザーグループに属しているユーザーの場合、各グループの表示を切り替えることができます。選択されたグループに合わせて表示されたデータが更新されます。[!UICONTROL RBAC] を使用していない場合、すべてのユーザーは管理者権限を持ち、すべての[!UICONTROL data sources]（コンバージョングループ）にアクセスできます。

## コンバージョングループ {#conversion-groups}

[!UICONTROL Audience Optimization]レポートにおいて、**[!UICONTROL Conversion Groups]**&#x200B;は 1 つ以上のコンバージョン特性が含まれる[!UICONTROL data sources]と同義語になります。コンバージョン特性が 1 つも含まれない[!UICONTROL Data sources]は[!UICONTROL Audience Optimization]レポートに表示されません。[報告されたコンバージョン特性](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md)レポートでコンバージョングループのコンバージョン特性を確認できます。
