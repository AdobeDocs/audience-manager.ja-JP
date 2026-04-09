---
description: Audience Manager の一意のユーザー ID （UUID）値を取得するために、DART Enterprise（および他の送信先タイプ）で必要となるコードです。
seo-description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie コード
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
exl-id: 66e61a4b-908e-4950-8953-37a9920b67b5
TQID: https://experienceleague.adobe.com/x8w8GMRG9gnMWQAXyaWdguFk1SaD7P-199ccfyIQf-s
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2: id: c138d302-73f0-4186-93ea-10c4ba52f943id: e7029888-c8b0-46a7-849a-cf132a1559bf
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 52
ht-degree: 100%

---

# `get_aamCookie` コード {#get-aamcookie-code}

Audience Manager の一意のユーザー ID（[!DNL UUID]）値を取得するために [!DNL DART Enterprise]（および他の宛先タイプ）で必要になるコードです。

この関数はページの上部（理想的には `<head>` コードブロック内）で定義します。

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```
