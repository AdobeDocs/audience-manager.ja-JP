---
description: Google サイト運営者タグの .setTargeting メソッドを呼び出す前に、Audience Manager の Cookie を確認するための if 文を追加します。
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: GPT setTargeting API 呼び出しの変更
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
TQID: https://experienceleague.adobe.com/2K-1BhtAdC60YW3nxvT7cVgQVSsY3gaWy7NbG-FcDqM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 278
ht-degree: 98%

---

# GPT `setTargeting` API呼び出しの変更 {#modify-the-gpt-settargeting-api-call}

[!DNL Google Publisher Tag] `.setTargeting` メソッドを呼び出す前に、Audience Manager の Cookie を確認するための if 文を追加します。

## `IF` 文で Audience Manager の Cookie を確認

`.setTargeting` メソッドは、データを Audience Manager の宛先 Cookie と一意のユーザー ID Cookie（`aam_uuid`）から取得します。しかし、[!UICONTROL DIL] によりこれらの Cookie が書き込まれるより前に `.setTargeting` が呼び出された場合、またはこれらの Cookie が空の場合、ページを読み込むとエラーが発生することがあります。このような状況が発生しないようにするには、これらの Cookie を確認する `if` 文で `.setTargeting` メソッドを囲みます。これらの Cookie が設定されていない場合、この文は `.setTargeting` が `AamGpt` 関数を呼び出さないようにします。

### `IF` 文コードの例

この例では、Audience Manager の宛先 Cookie の名前は `Sample` です。この名前は、Audience Manager ユーザーインターフェイス で宛先 Cookie を作成する際に設定します。[!UICONTROL DIL] は `aam_uuid` Cookie を設定します。この名前は変更できません。

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>[!DNL Google Ad Manager] との統合の方法によっては、上記のコード例のうち一部の行だけが必要となることがあります。
>
>* クライアント側の統合：1～3 行目のみを使用します。
>* サーバー側の統合：どの行も必要ではありません。
>* [!DNL Audience Manager] でのレポートに使用する取り込み [!DNL Google Ad Manager] ログファイル：4～6 行目のみを使用します。このコードにより、`aam_uuid` Cookie の値がログに挿入され、レポート用に取り込めるようになります。

### `AamGpt` 関数とデータタイプ

`if` 文で使用するキー変数を定義します。

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 関数 </th> 
   <th colname="col2" class="entry"> のタイプ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>文字列 </p> </td> 
   <td colname="col3"> <p>キーと値のセグメントペアのキーを返します。例えば、キーと値のペアが <code> color=blue </code> である場合、<code> color </code> が返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>文字列の配列 </p> </td> 
   <td colname="col3"> <p>値を配列（<code> ["value1","value2"] </code> など）で返します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>Audience Manager ユーザー ID（<code> 12345 </code> など）を返します。 </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [GPT 宛先の作成](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Google サイト運営者タグ用の Audience Manager コード](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)
