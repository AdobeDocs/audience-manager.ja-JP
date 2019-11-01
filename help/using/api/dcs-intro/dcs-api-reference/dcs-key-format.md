---
description: 呼び出しをおこなう場合、DCS では標準形式またはシリアル化された形式のキー値ペアデータを受信します。この節では、標準のキー値ペアデータとシリアル化されたキー値ペアデータの形式について説明します。
seo-description: 呼び出しをおこなう場合、DCS では標準形式またはシリアル化された形式のキー値ペアデータを受信します。この節では、標準のキー値ペアデータとシリアル化されたキー値ペアデータの形式について説明します。
seo-title: DCS 呼び出しでのキー値ペアの形式
solution: Audience Manager
title: DCS 呼び出しでのキー値ペアの形式
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# DCS 呼び出しでのキー値ペアの形式 {#formatting-key-value-pairs-in-dcs-calls}

呼び出しをおこなう場合、[!UICONTROL DCS] では標準形式またはシリアル化された形式のキー値ペアデータを受信します。この節では、標準のキー値ペアデータとシリアル化されたキー値ペアデータの形式について説明します。

## 標準およびシリアル化されたキー値ペア {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> キー値タイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> 例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>標準</b> </td> 
   <td colname="col2"> <p>標準のキー値ペアは単一のキーと値で構成されます。この構造ではデータを別々のキー値ペアに編成します。各キーは明示的に指定されます。別の値を定義ために再度使用される場合でも、同様です。これは、DCS にデータを送信する最も一般的な方法です。 </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>シリアル型</b> </td> 
   <td colname="col2"> <p>シリアル化されたキー値ペアは単一のキーと複数の値で構成されます。これはデータを編成する効率的な方法になりますが、シリアル化されたキー値ペアには、各キーと各キー値セットを区切るための特定のシンボルが必要です。 </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## シリアル化されたキー値ペアの区切り文字 {#delimiters-separators}

シリアル化されたキー値ペアでは、変数内の値および変数間を区切るマーカーを指定する必要があります。Audience Manager には次の区切り文字が必要です。

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 区切り文字のタイプ </th> 
   <th colname="col2" class="entry"> シンボル </th> 
   <th colname="col3" class="entry"> 区切る対象 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>ペア区切り</b> </td> 
   <td colname="col2"> アンパサンド &amp; </td> 
   <td colname="col3"> <p>キー値ペア: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>値区切り</b> </td> 
   <td colname="col2"> コンマ , </td> 
   <td colname="col3"> <p>キー値ペア内の個々の値： </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [DCS へのデータ送信](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [DCS でサポートされるキー値のプレフィックスと変数](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [キー値ペアの解説](../../../reference/key-value-pairs-explained.md)

