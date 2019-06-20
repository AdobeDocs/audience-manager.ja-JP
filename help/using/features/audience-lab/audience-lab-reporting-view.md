---
description: テストグループのレポートセクションには、テストグループのコンバージョンに関する情報が返されます。これにより、テストセグメントの効果を簡単に比較できます。いくつものフィルターやディメンションを使用してデータを視覚化できます。
seo-description: テストグループのレポートセクションには、テストグループのコンバージョンに関する情報が返されます。これにより、テストセグメントの効果を簡単に比較できます。いくつものフィルターやディメンションを使用してデータを視覚化できます。
seo-title: テストグループのレポート
solution: Audience Manager
title: テストグループのレポート
topic: DIL API
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# テストグループのレポート {#test-group-reporting}

テストグループのレポートセクションには、テストグループのコンバージョンに関する情報が返されます。これにより、テストセグメントの効果を簡単に比較できます。いくつものフィルターやディメンションを使用してデータを視覚化できます。

[!UICONTROL Audience Lab] では、作成したテストセグメントの詳細なレポート情報を返し、レポートデータをファイルとし [!DNL CSV] て保存できます。**[!UICONTROL Aggregate Reporting]** 次 **[!UICONTROL Trend Reporting]** のいずれかを選択できます。

**[!UICONTROL Aggregate Reporting]** は、テストセグメントの絶対数を返します。**[!UICONTROL Trend Reporting]** は、特定の期間におけるトレンド *のグラフを返し*ます。4 つのタブを使用してレポートをカスタマイズできます。

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Population Conversion Rate</span></b> </p> </td> 
   <td colname="col2"> <p>コンバージョンにつながった特定のテストセグメントに属するデバイスの割合を返します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Converters</span></b> </p> </td> 
   <td colname="col2"> <p>テストグループにおいて選択したコンバージョン特性を示したデバイス数を返します。コンバージョン特性の作成方法については、<a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external">こちらのビデオをご覧ください</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">Total Conversions</span></b> </p> </td> 
   <td colname="col2"> <p>テストセグメントにおいてコンバージョンに至った数を返します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Test Segment Populations</span></b> </p> </td> 
   <td colname="col2"> <p>テストセグメントに属するデバイス数を返します。Toggle between <b><span class="uicontrol"> Total Population</span></b> or <b><span class="uicontrol"> Real-time Population</span></b>. 違いについては、<a href="../../faq/faq-reporting.md">レポートの FAQ</a> で説明しています。 </p> </td>
  </tr>
 </tbody>
</table>

レポートを生成するために特定のコンバージョン特性を選択することも、すべての特性をまとめて選択することもできます。You can define a date range for which the information should be returned and export the report as a [!DNL CSV] file.

>[!NOTE]
>
>* テストグループに関するレポートは、開始日以降に実施されます。
>* テストの開始日後で、かつデバイスがテストセグメントに追加された後のコンバージョンのみがカウントされます。そのデバイスがテストグループに割り当てられる前に発生したコンバージョンについてはカウントされません。


A returned **[!UICONTROL Aggregate Reporting]** chart could look like this:

![](assets/aggregate-reporting.PNG)

A returned **[!UICONTROL Trend Reporting]** chart could look like the one below. 絶対数を無視し、テストセグメントのトレンドにのみ注目したい場合は、「**[!UICONTROL Normalized]**」チェックボックスをオンにしてください。

![](assets/trend-reporting.PNG)