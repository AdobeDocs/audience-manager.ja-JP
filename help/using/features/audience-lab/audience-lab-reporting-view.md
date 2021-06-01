---
description: テストグループのレポートセクションには、テストグループのコンバージョンに関する情報が返されます。これにより、テストセグメントの効果を簡単に比較できます。いくつものフィルターやディメンションを使用してデータを視覚化できます。
seo-description: テストグループのレポートセクションには、テストグループのコンバージョンに関する情報が返されます。これにより、テストセグメントの効果を簡単に比較できます。いくつものフィルターやディメンションを使用してデータを視覚化できます。
seo-title: テストグループのレポート
solution: Audience Manager
title: テストグループのレポート
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 100%

---

# テストグループのレポート {#test-group-reporting}

テストグループのレポートセクションには、テストグループのコンバージョンに関する情報が返されます。これにより、テストセグメントの効果を簡単に比較できます。いくつものフィルターやディメンションを使用してデータを視覚化できます。

[!UICONTROL Audience Lab]は作成したテストセグメントに関する詳細なレポート情報を返します。また、レポートデータは [!DNL CSV] ファイルとして保存できます。**[!UICONTROL Aggregate Reporting]** と **[!UICONTROL Trend Reporting]** から選択できます。

**[!UICONTROL Aggregate Reporting]**&#x200B;は、テストセグメントの絶対数を返します。**[!UICONTROL Trend Reporting]**&#x200B;は、*特定の期間にわたる*&#x200B;トレンドのグラフを返します。4 つのタブを使用してレポートをカスタマイズできます。

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
   <td colname="col2"> <p>テストグループにおいて選択したコンバージョン特性を示したデバイス数を返します。コンバージョン特性の作成方法については、<a href="https://helpx.adobe.com/jp/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external">こちらのビデオをご覧ください</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">Total Conversions</span></b> </p> </td> 
   <td colname="col2"> <p>テストセグメントにおいてコンバージョンに至った数を返します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Test Segment Populations</span></b> </p> </td> 
   <td colname="col2"> <p>テストセグメントに属するデバイス数を返します。<b><span class="uicontrol">Total Population</span></b> と <b><span class="uicontrol">Real-time Population</span></b> 間を切り替えることができます。違いについては、<a href="../../faq/faq-reporting.md">レポートの FAQ</a> で説明しています。 </p> </td>
  </tr>
 </tbody>
</table>

レポートを生成するために特定のコンバージョン特性を選択することも、すべての特性をまとめて選択することもできます。また、返される情報の日付範囲を定義し、レポートを [!DNL CSV] ファイルとしてエクスポートすることができます。

>[!NOTE]
>
>* テストグループに関するレポートは、開始日以降に実施されます。
>* テストの開始日後で、かつデバイスがテストセグメントに追加された後のコンバージョンのみがカウントされます。そのデバイスがテストグループに割り当てられる前に発生したコンバージョンについてはカウントされません。


次のような&#x200B;**[!UICONTROL Aggregate Reporting]**&#x200B;チャートが返されます。

![](assets/aggregate-reporting.PNG)

次のような&#x200B;**[!UICONTROL Trend Reporting]**&#x200B;チャートが返されます。絶対数を無視し、テストセグメントのトレンドにのみ注目したい場合は、「**[!UICONTROL Normalized]**」チェックボックスをオンにしてください。

![](assets/trend-reporting.PNG)
