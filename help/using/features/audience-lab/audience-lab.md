---
description: セグメントテストグループに重複のないテストセグメントを作成すると、様々な宛先の有効性を測定し比較することができます。有効性をテストするために、対照グループを残しておき、セグメントを全体のうちの一部に割り振ることができます。
seo-description: セグメントテストグループに重複のないテストセグメントを作成すると、様々な宛先の有効性を測定し比較することができます。有効性をテストするために、対照グループを残しておき、セグメントを全体のうちの一部に割り振ることができます。
seo-title: Audience Lab
solution: Audience Manager
title: オーディエンスラボ
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: オーディエンスラボ
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 100%

---

# [!UICONTROL Audience Lab] {#audience-lab}

[!UICONTROL Segment Test Groups] で重複のないテストセグメントを作成すると、様々な宛先の有効性を測定し比較することができます。有効性をテストするために、対照グループを残しておき、セグメントを全体のうちの一部に割り振ることができます。

## 概要 {#audience-lab-overview}

[!UICONTROL Audience Lab] では、[プロファイルリンク](../../features/profile-merge-rules/merge-rules-overview.md)を使用することで、複数のデバイスにまたがってテストを実行できます。これにより、ユーザーはすべてのデバイスにわたって同じテストセグメントに適合し、同じ処理がおこなわれるようになります。テストグループ内のテストセグメントは、ベースセグメントに割り当てられた[プロファイル結合ルール](../../features/profile-merge-rules/merge-rules-dashboard.md)を継承します。

[!UICONTROL Audience Lab] のデフォルトビューには、各テストグループのカードが表示されます。カードをクリックして、**[!UICONTROL Test Group]** ビューにアクセスします。このビューには、以下の情報が含まれています。

* **[テストグループの情報](../../features/audience-lab/audience-lab-information-view.md)**
* **[テストグループのレポート](../../features/audience-lab/audience-lab-reporting-view.md)**

それぞれ&#x200B;**最大 15 個のテストセグメント**&#x200B;を持つ、**最大 10 個のテストグループ**&#x200B;を作成できます。

![](assets/test-groups-view.PNG)

## テストグループの検索とフィルタリング {#search-and-filter}

複数のテストセグメントを使用して複数のテストグループの作成をいったん開始したら、検索ボックスを使用して特定のテストグループを検索したほうが容易な場合があります。次のいずれかでテストグループを検索できます。

* テストグループの名前
* テストグループに含まれているいずれかのテストセグメントの名前
* テストグループの説明

![](assets/search_and_filter_audience_lab.png)

また、ステータスに基づいてテストグループをフィルタリングすることもできます。利用可能なすべてのステータスについては、下記の[ステータス](../../features/audience-lab/audience-lab.md#status)節を参照してください。

## [!UICONTROL Status] {#status}

テストグループのステータスには、Active、Scheduled、Paused、Draft、Completed があります。次の表は、各ステータスの詳細を示したものです。

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ステータス </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Active </span></b> </p> </td> 
   <td colname="col2"> <p><i>アクティブ</i>のテストグループは、現在送信先にデータを送信しています。<b><span class="uicontrol">テストグループ</span></b>カードの <b><span class="uicontrol">Pause Test</span></b> を押すと、送信先へのデータ送信が停止します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Scheduled </span></b> </p> </td> 
   <td colname="col2"> <p><i>scheduled</i> のテストグループは、まだアクティブではないものの、もう編集はできない状態です。<b>Create Test Groups</b> ウィザードで選択した開始日にアクティブになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">Paused </span></b> </p> </td> 
   <td colname="col2"> <p><i>paused</i> のテストグループは、現在宛先にデータを送信していません。<b><span class="uicontrol">テストグループ</span></b>カードの <b><span class="uicontrol">Make Active</span></b> を押すと、特性の送信が再開されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Draft </span></b> </p> </td> 
   <td colname="col2"> <p><i>draft</i> のテストグループは、まだアクティブではなく、編集できる状態です。マッピングされた宛先へのデータ送信はまだおこないません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Completed </span></b> </p> </td> 
   <td colname="col2"> <p><i>完了</i>のテストグループは、<b><span class="uicontrol">Create Test Groups</span></b> ウィザードで選択した終了日に達し、レポートデータの送信を終了しました。 </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> アクション </th> 
   <th colname="col2" class="entry"> 説明 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Edit </span></b> </p> </td>
   <td colname="col2"> <p>ドラフトのテストグループに対して<b>のみ</b>使用できます。<b><span class="uicontrol">Create New Test Group</span></b> ウィザードを再開できます。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pause </span></b> </p> </td>
   <td colname="col2"> <p>active テストグループに対して使用できます。テストセグメントの宛先への送信を一時停止できます。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">Make Active</span></b> </p> </td>
   <td colname="col2"> <p>paused テストグループに対して使用できます。テストセグメントの宛先への送信を再開できます。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">View</span></b> </p> </td>
   <td colname="col2"> <p>完了のテストグループに対して使用できます。テストで生成されたレポート情報を表示できます。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplicate </span></b> </p> </td>
   <td colname="col2"> <p>複製するテストグループと同じ設定で新しいテストグループを作成できます。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Delete </span></b> </p> </td>
   <td colname="col2"> <p>テストグループを削除できます。テストセグメントは宛先とのマッピングが解除され、テストグループに関連付けられていたベースラインセグメントおよびコンバージョン特性は完全に編集可能になります。テストグループを削除する際、必要に応じてレポートを保存するために、CSV ファイルのダウンロードを促すアラートがプロンプト表示されます。 </p> </td>
  </tr>
 </tbody>
</table>
