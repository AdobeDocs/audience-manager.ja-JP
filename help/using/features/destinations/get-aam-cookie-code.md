---
description: Audience Manager の一意のユーザー ID（UUID）値を取得するために、DART Enterprise（および他の宛先タイプ）で必要となるコードです。
seo-description: Audience Manager の一意のユーザー ID（UUID）値を取得するために、DART Enterprise（および他の宛先タイプ）で必要となるコードです。
seo-title: get_aamCookie コード
solution: Audience Manager
title: get_aamCookie コード
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 7d0735fa9620b7765db7be8d3a7c8731536ffd32
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 100%

---


# get_aamCookie コード {#get-aamcookie-code}

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
