---
description: 広告主向けオーディエンスの最適化により、自社の有料メディアキャンペーン全体で Audience Manager セグメントによってどの程度パフォーマンス向上を図れるかを確認できます。これらのレポートは、ログレベルのキャンペーンパフォーマンスデータと Audience Manager のセグメント指標を組み合わせることで、セグメントを中心とした最適化および効果的なチャネルミックスを導き出します。
seo-description: 広告主向けオーディエンスの最適化により、自社の有料メディアキャンペーン全体で Audience Manager セグメントによってどの程度パフォーマンス向上を図れるかを確認できます。これらのレポートは、ログレベルのキャンペーンパフォーマンスデータと Audience Manager のセグメント指標を組み合わせることで、セグメントを中心とした最適化および効果的なチャネルミックスを導き出します。
seo-title: 広告主向けオーディエンスの最適化
solution: Audience Manager
title: 広告主向けオーディエンスの最適化
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 広告主向けオーディエンスの最適化{#audience-optimization-for-advertisers}

広告主向けオーディエンスの最適化により、自社の有料メディアキャンペーン全体で Audience Manager セグメントによってどの程度パフォーマンス向上を図れるかを確認できます。これらのレポートは、ログレベルのキャンペーンパフォーマンスデータと Audience Manager のセグメント指標を組み合わせることで、セグメントを中心とした最適化および効果的なチャネルミックスを導き出します。

## データの収集方法 {#data-ingestion-methods}

次のいずれかの方法でこれらのレポートで使用するデータを [!DNL Audience Manager] に送信できます。両方の方法でデータを送信する場合もあります。そうすることで、訪問者に関するより包括的で正確な情報をレポートに取り込むことができます。To use the [!UICONTROL Audience Optimization] reports, your event calls must include *all* of the parameters listed in the [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) documentation. 以下に列挙された方法でデータを送信できます。

* ピクセル呼び出し：必要なメタデータパラメーターを [!DNL Audience Manager] に渡すには、[ピクセル呼び出しを使用したキャンペーンのクリックデータのキャプチャ](../../../integration/media-data-integration/click-data-pixels.md)と[ピクセル呼び出しを使用したキャンペーンのインプレッションデータのキャプチャ ](../../../integration/media-data-integration/impression-data-pixels.md)を参照してください。

* データファイル：これらのレポートを使用して独自のデータ、または [!DNL Audience Manager] と統合されていないソースからのデータを分析する場合、そのデータのデータファイルとメタデータファイルを作成およびアップロードする必要があります。詳しくは、[オーディエンスの最適化レポートのデータファイル](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)と [Audience Optimization レポートのデータおよびメタデータファイル](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)を参照してください。

## ロールベースのアクセス制御（RBAC）{#rbac}

表示できるレポートのタイプは、どの [!UICONTROL RBAC] グループに割り当てられているかに応じて異なります。詳しくは、[管理](../../../features/administration/administration-overview.md)と[グループの作成](../../../features/administration/administration-overview.md#create-group)を参照してください。

[!UICONTROL RBAC] グループには、レポートを [!UICONTROL Audience Optimization] 表示するためにいくつかのデータソースが設定されている必要があります。担当の [!DNL Audience Manager] コンサルタントがお客様に代わってこれらのデータソースを設定します。[!UICONTROL RBAC] ユーザーグループに設定されたデータソースが多いほど、それらのグループメンバーがアクセスできるデータが多くなります。担当のコンサルタントは、これらのデータソースのうち少なくとも 1 つを設定します。

* 広告主データソース
* ブランドデータソース
* プラットフォームデータソース

複数の [!UICONTROL RBAC] ユーザーグループに属しているユーザーの場合、各グループの表示を切り替えることができます。選択されたグループに合わせて表示されたデータが更新されます。[!UICONTROL RBAC] を使用していない場合、すべてのユーザーは管理者権限を持ち、すべてのデータソース（コンバージョングループ）にアクセスできます。

## コンバージョングループ {#conversion-groups}

[!UICONTROL Audience Optimization] レポートでは、 **[!UICONTROL Conversion Groups]** 少なくとも1つのコンバージョン特性を含むデータソースと同義語です。Data sources which do not contain at least one conversion trait do not appear in the [!UICONTROL Audience Optimization] reports. You can view the conversion traits for conversion groups in the [Reported Conversion Traits](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) report.
