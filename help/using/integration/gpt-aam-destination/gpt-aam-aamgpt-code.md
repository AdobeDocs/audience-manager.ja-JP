---
description: AamGpt は、Audience Manager の Cookie データを読み取り、Google サイト運営者タグに情報を送信する JavaScript 関数です。
seo-description: AamGpt は、Audience Manager の Cookie データを読み取り、Google サイト運営者タグに情報を送信する JavaScript 関数です。
seo-title: Google サイト運営者タグ用の Audience Manager コード
solution: Audience Manager
title: Google サイト運営者タグ用の Audience Manager コード
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
feature: Third-party Integration
exl-id: 04e74399-7b6a-400e-a1e6-94fe296e7209
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 98%

---

# Google サイト運営者タグ用の Audience Manager コード {#audience-manager-code-for-google-publisher-tags}

`AamGpt` は、Audience Manager の Cookie データを読み取り、[!DNL Google Publisher Tags] に情報を送信する [!DNL JavaScript] 関数です。

>[!NOTE]
>
>Audience Manager の Cookie データを [!UICONTROL UUID] および宛先の Cookie から読み取るための独自のコードがある場合、この関数は不要です。

## サンプルコード

`AamGpt` コードをページの先頭、可能であれば `<head>` コードブロック内に配置します。`AamGpt` コードは以下から利用できます。

```js
var AamGpt = {  
 strictEncode: function(str){ 
  return encodeURIComponent(str).replace(/[!'()]/g, escape).replace(/\*/g, "%2A"); 
 }, 
 getCookie: function(c_name) 
 { 
  var i,x,y,c=document.cookie.split(";"); 
  for (i=0;i<c.length;i++) 
  { 
   x=c[i].substr(0,c[i].indexOf("=")); 
   y=c[i].substr(c[i].indexOf("=")+1); 
   x=x.replace(/^\s+|\s+$/g,""); 
   if (x==c_name) 
   { 
    return unescape(y); 
   } 
  } 
 }, 
 getKey: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[0] != "undefined" && cList[0].match(/\w+/)) 
   { 
    return cList[0]; 
   } 
  }  
 }, 
 getValues: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D\w+/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[1] != "undefined" && cList[1].match(/\w+/)) 
   { 
    var vList=cList[1].split("%2C"); 
    if(typeof vList[0] != "undefined") 
    { 
     return vList; 
    } else { 
     return null; 
    }    
   } else { 
    return null; 
   } 
  } else { 
   return null; 
  } 
 } 
};
```
