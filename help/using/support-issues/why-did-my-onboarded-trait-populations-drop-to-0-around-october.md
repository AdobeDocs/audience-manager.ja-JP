---
description: 2019年10月14日頃、デバイスIDグラフのオンボードの特性の母集団が0に減少し、以前はずっと高くなっていました。
seo-description: 2019年10月14日頃、デバイスIDグラフのオンボードの特性の母集団が0に減少し、以前はずっと高くなっていました。
seo-title: なぜ私のオンボードの特徴は10月15日頃に0人に減ったのでしょう？
solution: Audience Manager
title: なぜ私のオンボードの特徴は10月15日頃に0人に減ったのでしょう？
translation-type: tm+mt
source-git-commit: eb129bbf642cb666ce3ea05ff606c051e02f4d1e

---


# なぜ私のオンボードの特徴は10月15日頃に0人に減ったのでしょう？ {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

2019年10月14日頃、デバイスIDグラフのオンボードの特性の母集団が0に減少し、以前はずっと高くなっていました。

![デバイスIDドロップの画像](/help/using/support-issues/assets/device_id_populationdrop.png)

**回答**

10月15日に、Audience Managerのプロファイル結合ルール機能の更新が、クロスデバイスデータソースにアップロードされたCRM IDからキーオフされたオンボードデータが、デバイスIDに対して認識されなくなりました。  以前は、Audience Managerは、クロスデバイスID（またはCRM ID）と、関連するAudience Manager UUID（デバイスID）にそれらの関連付けられた関連付けられた関連付けられた関連付けをコピーしていました。  この変更は、特性データと実現されるプロファイルの性質をより正確に反映するために行われました。

特性の関連付けを表示するには、特性ビューの右上隅にあるドロップダウンから「デバイス間ID」オプションを選択してください。

![デバイス間ID別の割り当てを表示](/help/using/support-issues/assets/deviceid-crossdevice.png)

