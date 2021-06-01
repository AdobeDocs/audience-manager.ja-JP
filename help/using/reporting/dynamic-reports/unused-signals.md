---
description: このレポートでは、インベントリで収集し Audience Manager に送信したすべての未使用情報の頻度カウントを返します。
seo-description: このレポートでは、インベントリで収集し Audience Manager に送信したすべての未使用情報の頻度カウントを返します。
seo-title: 未使用シグナルレポート
solution: Audience Manager
title: 未使用シグナルレポート
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 100%

---

# 未使用シグナルレポート {#unused-signals-report}

このレポートでは、インベントリで収集し Audience Manager に送信したすべての未使用情報の頻度カウントを返します。このレポートにアクセスするには、**Analytics／Audience Reports／Other Report／Unused Signals**&#x200B;に移動します。

>[!NOTE]
>
>「オーディエンスレポートへのアクセス権がありません」というメッセージが表示された場合は、Audience Manager コンサルタントまたはカスタマーケアに連絡して、レポートをプロビジョニングしてもらってください。

![未使用シグナルレポートのスクリーンショット](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## 概要

シグナルは、Web サイトからの情報で、[キーと値のペア](../../reference/key-value-pairs-explained.md)の形式（`color=blue, price>100, gender=female` など）で [!DNL Audience Manager] に渡されます。

未使用シグナルは、収集したものの、特性にマッピングされていないデータで構成されます。[!UICONTROL Unused Signals] レポートには、データが日付、キー、値、頻度カウント別に表形式で表示されます。1 日に 100 回以上 [!DNL Audience Manager] に渡されたマッピングされていないシグナルが、[!UICONTROL Unused Signals] レポートの対象になります。

このレポートをレビューすると、新規または既存の特性にマッピングできる孤立したシグナルの特定に役に立ちます。

>[!NOTE]
>
>キーまたは値の名前を検索フィールドに指定すると、結果を特定のレコードに限定できます。

## ユースケース

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 例 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>特性の統一性の確保または単一キーへの関連する値の追加</b> </p> </td> 
   <td colname="col2"> <p>レポートをレビューして、特定シグナルの値の様々なバリエーションを把握します。 </p> <p>例えば、<code> c_state = North Carolina</code> としてキー値ペアで定義されている「North Carolina」州の特性があるとします。名前のバリエーションを見つけて特性（例：<code> c_state = North Carolina, NC, N.C., NCarolina</code>）に追加するのに、レポートが役に立ちます。さらに、レポートで名前のバリエーションを見つけて、すべてのサイトで統一された値に置き換えることもできます｡ </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>新規特性の作成</b> </p> </td> 
   <td colname="col2"> <p>レポートをレビューして、特定のキーで渡された新しい値を確認します。これらの新しい値に基づいて新規のキー値ペアを作成できます。 </p> <p> <p>注意：レポートを隔週に確認して、頻繁に変化する値（例えば、ショー、キャンペーン、著名人など）がないかどうかを調べます。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>マッピングされていない値の検出</b> </p> </td> 
   <td colname="col2"> <p>レポートをレビューして、数値 1 がないか確認します。<span class="wintitle">未使用シグナル</span>レポートの数値 1 は null 値を表します。これは必ずしも悪くはありません。単に、特定のキーに値マッピングが関連付けられていないだけです。重要な変数に値 1 が多数ある場合は、サイトチームに相談して、すべてのページが正しくタグ付けされているかどうかを確認します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## ベストプラクティス

[!UICONTROL Unused Signals] レポートを実行してチェックします。

* 特性を作成または特性ルールを更新した後。これにより、特性とルールが適切にセットアップされていることを確認できます。結果に数値 1 が含まれている場合は、新しい特性が正しく設定されていない可能性があります。
* 隔週または毎月。スケジュール設定されたレビューは、特性マッピングが最新かどうかを確認するのに役に立ちます。

>[!NOTE]
>
>レポートで未使用値を検索する際は、以下の点を考慮してください。例えば、以下の 2 つの式には違いがあります。

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a! =23))
* どちらの例も、キー値ペアを 2 つ（v および a）を含む特性を示しています。最初の式は、「特性には、値が 1 のキー v を含み、値が 23 のキー a は含まない（the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23）」となり、2 番目の式は、「値が 1 のキー v、および値が 23 以外のキー a を含む（contains key v with the value 1 [!UICONTROL AND] the key a with the value [!UICONTROL NOT EQUAL] 23）」となります。
* 上記 2 つの異なる式の場合、例えば値が 23 以外のキー a に渡された値を [!UICONTROL Unused Signals Report] レポートで検索すると、最初の式でのみ結果が得られます。キーの値がまったく送信されなかったからです。2 番目の場合は、23 以外の値が送信されたので、キー a は未使用ではありません。

## 特性の一括作成

[!UICONTROL Unused Signals] レポートから得られたデータに基づいて多数の特性を一括作成する必要がある場合は、パートナーソリューション担当者に問い合わせてください。
