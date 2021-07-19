---
description: インタラクティブレポートの技術的基盤となるソフトウェアとデータ更新スケジュールについて説明します。
seo-description: インタラクティブレポートの技術的基盤となるソフトウェアとデータ更新スケジュールについて説明します。
seo-title: レポート技術
solution: Audience Manager
title: レポート技術
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 100%

---

# レポート技術{#report-technology}

インタラクティブレポートの技術的基盤となるソフトウェアとデータ更新スケジュールについて説明します。

<!-- 

c_report_technology.xml

 -->

## Tableau 技術を使用するインタラクティブレポート

[!DNL Audience Manager] は、[Tableau](https://www.tableausoftware.com/) ソフトウェアを使用してインタラクティブレポートにデータを表示します。[!DNL Tableau] により、以下に役立つ視覚的なキューおよびシンボルを[!UICONTROL Delivery and Overlap]レポートで使用できます。

* パフォーマンスが高いまたは低い特性を見つける。
* ユニーク訪問者の重複が多いまたは少ない特性およびセグメントを見分ける。
* 重複データを使用して、ターゲット設定されたセグメントを作成する。
* 重複の少ない関連特性を特定することでリーチを拡大する。

## データ更新スケジュール

レポートデータは、毎週日曜日に更新されます。更新では、土曜日（前日）から先週の日曜日までのデータを処理します。

## インタラクティブレポートで使用される図形、色、サイズ {#shapes-colors-sizes}

ほとんどのインタラクティブレポートは、様々なサイズのシェイプや色を使用して結果を表示します。この表示形式は、数値の羅列を細かく調べなくてもデータを視覚的に理解するのに役立つように設計されています。

<!-- 

r_legend.xml

 -->

### レポートの凡例

次の表は、動的レポートで使用する形状、サイズ、色の定義です。

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> データ要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>形状</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">円はファーストパーティの特性を表します。 </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">正方形はサードパーティの特性を表します。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>色</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">赤色のシェードは<i>低い</i>重複を表します。 </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">緑色のシェードは<i>高い</i>重複を表します。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>サイズ</b> </td> 
   <td colname="col2"> サイズの増減はリーチに比例します（特性またはセグメントのクリックまたはユニークユーザーの数または割合）。 </td> 
  </tr> 
 </tbody> 
</table>

## Tableau ドキュメント {#tableau-documentation}

インタラクティブレポートに表示される Tableau コントロールの詳細については、[Linux 2018.2 での Tableau Server](https://help.tableau.com/v2018.2/server-linux/ja-jp/get_started_server.htm) に関する公式ドキュメントを参照してください。
