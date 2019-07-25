---
description: このレポートでは、在庫で収集し Audience Manager に送信したすべての未使用情報の頻度カウントを返します。
seo-description: このレポートでは、在庫で収集し Audience Manager に送信したすべての未使用情報の頻度カウントを返します。
seo-title: 未使用シグナルレポート
solution: Audience Manager
title: 未使用シグナルレポート
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 未使用シグナルレポート{#unused-signals-report}

このレポートでは、在庫で収集し Audience Manager に送信したすべての未使用情報の頻度カウントを返します。

<!-- 

c_unused_signals.xml

 -->

## 未使用シグナルレポート

シグナルは、Web サイトからの情報で、[キーと値のペア](../../reference/key-value-pairs-explained.md)の形式（`color=blue, price>100, gender=female` など）で [!DNL Audience Manager] に渡されます。

未使用シグナルは、収集したものの、特性にマッピングされていないデータで構成されます。[!UICONTROL Unused Signals] レポートには、日付、キー、値および頻度のカウント別に表のデータが表示されます。Any unmapped signal passed in to [!DNL Audience Manager] at least 100 times in a day qualifies for the [!UICONTROL Unused Signals] report.

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
   <td colname="col2"> <p>レポートをレビューして、特定シグナルの値の様々なバリエーションを把握します。 </p> <p>例えば、<code>c_state = North Carolina</code> としてキー値ペアで定義されている「North Carolina」州の特性があるとします。名前のバリエーションを見つけて特性に追加する（例えば、<code>c_state = North Carolina, NC, N.C., NCarolina</code>）のに、レポートが役に立ちます。さらに、レポートで名前のバリエーションを見つけて、すべてのサイトで統一された値に置き換えることもできます｡ </p> <p> </p> </td> 
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

Run and check the [!UICONTROL Unused Signals] report:

* 特性を作成または特性ルールを更新した後。これにより、特性とルールが適切にセットアップされていることを確認できます。結果に数値 1 が含まれている場合は、新しい特性が正しく設定されていない可能性があります。
* 隔週または毎月。スケジュール設定されたレビューは、特性マッピングが最新かどうかを確認するのに役に立ちます。

>[!NOTE]
>
>レポートで未使用値を検索する際は、以下の点を考慮してください。例えば、以下の 2 つの式には違いがあります。

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Both examples show a trait which contains two key-value pairs v and a. The first expression translates into: the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23. The second expression contains key v with the value 1 [!UICONTROL AND] the key a with the value [!UICONTROL NOT EQUAL] 23.
* Considering the two different expressions above, let's say you search in the [!UICONTROL Unused Signals Report] for the values that get passed on key a with any value different than 23, you'll only obtain results in the first case because values for key were not sent AT ALL. 2 番目の場合は、23 以外の値が送信されたので、キー a は未使用ではありません。

## 特性の一括作成

Contact your Partner Solutions representative if you need to bulk create a lot of traits based on data obtained from the [!UICONTROL Unused Signals] report.
