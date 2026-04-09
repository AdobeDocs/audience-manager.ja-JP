---
description: 2019 年 10 月 14 日（PT）頃、デバイス ID グラフのオンボーディングされた特性の母集団が 0 に減っているのに気づきました。これは、以前はもっと多かったものです。
seo-description: Around October 14th, 2019 I noticed that my onboarded trait populations for the Device ID graph have dropped to 0, where previously they were much higher.
seo-title: Why did my Onboarded trait populations drop to 0 around October 15th?
solution: Audience Manager
title: 10 月 15 日頃にオンボーディングされた特性の母集団が 0 に減ったのはなぜですか？
feature: Support
exl-id: e93cee15-7d05-4f81-8f14-a3e03f214542
TQID: https://experienceleague.adobe.com/AMglvoNdxz7SDKZN3B52mBnFiJVRQvzsAvykIv2foCo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 100%

---

# 10 月 15 日頃にオンボーディングされた特性の母集団が 0 に減ったのはなぜですか？ {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## 質問

2019 年 10 月 14 日（PT）頃、デバイス ID グラフのオンボーディングされた特性の母集団が 0 に減っているのに気づきました。これは、以前はもっと多かったものです。なぜこのようなことが起こったのでしょうか？

![デバイス ID 減少の画像](assets/device_id_populationdrop.png)

## 回答

10 月 15 日に、Audience Manager のプロファイル結合ルール機能に対するアップデートが変更され、クロスデバイスデータソースにアップロードされた CRM ID をキーにしたオンボーディングされたデータが、デバイス ID と対照して認識されなくなりました。以前は、Audience Manager は、両方のクロスデバイス ID（または CRM ID）と対照して認識し、関連する Audience Manager UUID（デバイス ID）に対してこれらの認識をコピーしていました。この変更は、特性データの特性と認識されたプロファイルをより正確に反映するためにおこなわれました。

特性認識を表示するには、特性表示の右上隅にあるドロップダウンから「クロスデバイス ID」オプションを選択してください。

![クロスデバイス ID による認識の表示](assets/deviceid-crossdevice.png)
