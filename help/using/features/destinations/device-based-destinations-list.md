---
description: このページには、現在のサーバー間統合のみが含まれています。統合について詳しくは、Adobe Exchange のリスト（利用可能な場合）を参照するか、アドビコンサルタント、またはカスタマーケアにお問い合わせください。
seo-description: このページには、現在のサーバー間統合のみが含まれています。統合について詳しくは、Adobe Exchange のリスト（利用可能な場合）を参照するか、アドビコンサルタント、またはカスタマーケアにお問い合わせください。
seo-title: Adobe Audience Manager のサーバー間の宛先
keywords: アクティブ化、アクティベートパートナー、宛先、宛先
solution: Audience Manager
title: Adobe Audience Manager のサーバー間の宛先
feature: 宛先の基本
exl-id: 7db3bc02-ece4-4524-a401-d2c8c6de510a
translation-type: ht
source-git-commit: 78d3bbc03936130f9c9da8ee5eed33e6ef9a07b9
workflow-type: ht
source-wordcount: '1148'
ht-degree: 100%

---

# [!DNL Audience Manager] [!UICONTROL Device-based Destinations]

このページには、現在の の[!DNL Audience Manager][デバイスベースの宛先](/help/using/features/destinations/add-device-based-destinations.md)のみが含まれます。[!DNL Audience Manager] では、[!UICONTROL device-based destinations] は [!UICONTROL server-to-server destinations] とも呼ばれます。統合について詳しくは、[Adobe Exchange](https://exchange.adobe.com/experiencecloud.html) のリスト（利用可能な場合）を参照するか、[!DNL Adobe] コンサルタントまたはカスタマーケアにお問い合わせください。


* **前回の更新日** = この [!UICONTROL device-based destination] で最後に更新がおこなわれた日付が表示されます。
* **アップデート** = [!DNL Audience Manager]この [!UICONTROL destination] にデータをリアルタイムで送信するか、バッチ（1 回/日）で送信するかを指定します。
* **セグメント解除** = セグメント化解除とは、デバイスプロファイルを不適格として[!UICONTROL segments]から削除するプロセスのことです。デバイスプロファイルを[!UICONTROL segment]から削除できるかどうかは、[!UICONTROL Profile Merge Rule] の作成時に使用したデバイスオプションによって異なります。セグメント化解除は、[!DNL GDPR] 削除リクエストのコンテキストでも使用されます。[プロファイルの結合ルールとデバイスのセグメント化解除プロセス](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)および [セグメント解除に対応している Audience Manager パートナー](/help/using/overview/data-security-and-privacy/data-privacy-requests.md#aam-partners-with-unsegmentation)をお読みください。[!DNL Audience Manager] は、以下の「**はい**」とマークされている[!UICONTROL destinations]にセグメント情報を送信します。
* **[!DNL IAB TCF] 同意の字列の受信** = [!DNL Audience Manager Plug-in for IAB TCF] は、ユーザーのプライバシー設定に従い、[!DNL IAB TC] 文字列をアクティベーションパートナーに転送できるようにします。[IAB TCF 用 Audience Manager プラグイン](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md)をお読みください。
* **[!DNL ICDS]** = この列には、[!UICONTROL Instant Cross-Device Suppression] をサポートするパートナーが一覧表示されます。[Instant Cross-Device Suppression](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) をお読みください。
* **モバイルデバイス ID** = この列には、[!DNL Audience Manager] からモバイルデバイス ID を受け取ることができるパートナーが一覧表示されます。


| 統合 | 最終更新日 | 更新 | セグメント解除 | [!DNL IAB TCF] 同意シグナルの受信 | [!DNL ICDS] | モバイルデバイス ID |
|----------------------------------------------------------|------------|-----------|-----------|-----------------------------------|------|-------------------|
| [!DNL 4C Insights] | 2018/09/26 | 1 回/日 | ○ | × | × | ○ |
| [!DNL 4info] | 2017/02/09 | 1 回/日 | × | × | × | ○ |
| [!DNL AcuityAds] | 2017/02/09 | リアルタイム | ○ | × | ○ | × |
| [!DNL Adara] | 2017/02/17 | リアルタイム | ○ | × | × | × |
| [!DNL Addictive Mobility] | 2017/02/22 | 1 回/日 | ○ | × | ○ | ○ |
| [!DNL Adelphic] | 2017/02/22 | 1 回/日 | × | × | × | ○ |
| [!DNL AdForm] | 2017/02/22 | リアルタイム | ○ | × | ○ | ○ |
| [!DNL AdGear] | 2017/02/22 | リアルタイム | ○ | × | ○ | × |
| [!DNL Adikteev] | 2018/01/26 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Adroll]／[!DNL NextRoll] | 2019/12/10 | 1 回/日 | × | × | × | × |
| [!DNL Adswizz] | 2017/10/09 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Adtheorent] | 2017/02/22 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Affinio] | 2018/04/03 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Aki] | 2018/06/21 | 1 回/日 | × | × | × | ○ |
| [!DNL Amazon Advertising] | 2017/06/15 | 1 回/日 | ○ | × | × | × |
| [!DNL AOL AdLearn] | 2017/03/02 | リアルタイム | × | × | × | ○ |
| [!DNL AOL ONE] | 2017/03/02 | リアルタイム | ○ | × | × | ○ |
| [!DNL AppNexus] | 2017/03/02 | リアルタイム | ○ | × | ○ | × |
| [!DNL AppNexus Yieldex] | 2017/08/10 | 1 回/日 | ○ | × | × | × |
| [!DNL Artsai] (formerly [!DNL Adxcel]) | 27/01/2020 | 1 回/日 | × | × | × | ○ |
| [!DNL Atedra]／[!DNL AdStanding] | 2017/03/02 | リアルタイム | ○ | × | ○ | × |
| [!DNL Avocet] | 2017/12/06 | 1 回/日 | × | × | × | × |
| [!DNL Bidtellect] | 2017/03/03 | リアルタイム | ○ | × | × | × |
| [!DNL Beeswax] | 2018/05/25 | 1 回/日 | × | × | × | ○ |
| [!DNL Brandscreen] | 2017/03/03 | リアルタイム | × | × | × | × |
| [!DNL Brightroll] | 2017/03/03 | 1 回/日 | × | ○ | × | × |
| [!DNL Button] | 2017/12/18 | 1 回/日 | ○ | × | × | ○ |
| [!DNL C1 Exchange] | 2017/02/27 | 1 回/日 | ○ | × | × | × |
| [!DNL Celtra] | 2017/02/27 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Centro] | 2017/02/27 | 1 回/日 | × | × | × | ○ |
| [!DNL ChoiceStream] | 2017/02/27 | 1 回/日 | × | × | × | × |
| [!DNL Clearstream.tv] | 2017/02/27 | リアルタイム | ○ | × | × | × |
| [!DNL Collective AMP Platform] | 2017/02/27 | 1 回/日 | × | × | × | × |
| [!DNL Criteo] | 2017/02/27 | リアルタイム | × | ○ | × | ○ |
| [!DNL Crosswise] | 2017/02/27 | 1 回/日 | ○ | × | × | × |
| [!DNL D.A.C. AudienceOne] | 2017/02/27 | 1 回/日 | ○ | × | × | × |
| [!DNL DataXu] | 2017/11/20 | リアルタイム | × | × | × | ○ |
| [!DNL Digilant] | 2017/03/02 | リアルタイム |  | × | × | × |
| [!DNL DistrictM] | 2017/03/02 | 1 回/日 | ○ | × | × | × |
| [!DNL DoubleVerify] | 2017/09/06 | 1 回/日 | ○ | × | × | × |
| [!DNL Drawbridge] | 2017/03/02 | リアルタイム | × | × | × | ○ |
| [!DNL Dstillery]（[!DNL FKA Media6]） | 2017/03/02 | リアルタイム | ○ | × | × | ○ |
| [!DNL Dunnhumby] | 2019/11/21 | 1 回/日 | × | × | × | × |
| [!DNL easyfundraising] | 2019/06/27 | 1 回/日 | × | × | × | ○ |
| [!DNL Epsilon Conversant] | 2017/03/03 | リアルタイム | × | × | × | × |
| [!DNL Exponential] | 2017/02/27 | リアルタイム | ○ | × | ○ | × |
| [!DNL Eyereturn Marketing] | 2017/04/11 | 1 回/日 | ○ | × | × | × |
| [!DNL EyeView Digital] | 2018/06/14 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Fiksu] | 2017/03/03 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Flashtalking] | 2017/03/02 | 1 回/日 | × | × | × | × |
| [!DNL Flybits] | 31/07/2020 | リアルタイム | ○ | × | ○ | ○ |
| [!DNL FreakOut] | 2017/03/03 | 1 回/日 | ○ | × | × | × |
| [!DNL Freewheel] | 2017/02/27 | 1 回/日 | ○ | ○ | × | ○ |
| [!DNL Gamut Media] | 2017/03/03 | リアルタイム |  | × | × |  |
| [!DNL Google AdsWords Display] | 2018/08/02 | リアルタイム | ○ | ○ | × | ○ |
| [!DNL Google DoubleClick Bid Manager (DBM)] | 2017/04/24 | リアルタイム | ○ | ○ | ○ | ○ |
| [!DNL Google DoubleClick Campaign Manager (DCM fka DFA)] | 2017/04/24 | リアルタイム | ○ | ○ | ○ | ○ |
| [!DNL Google DoubleClick for Publishers (DFP, DFPP)] | 2017/04/24 | リアルタイム | ○ | ○ | ○ | ○ |
| [!DNL GumGum] | 2017/06/02 | 1 回/日 | ○ | × | × | × |
| [!DNL Index Exchange (formerly Casale Media)] | 2017/03/03 | 1 回/日 | ○ | × | × | × |
| [!DNL Infectious Media] | 2017/03/03 | リアルタイム | ○ | × | ○ | × |
| [!DNL inMobi] | 2017/03/30 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Innovid] | 2017/03/02 | 1 回/日 | ○ | × | × | × |
| [!DNL iPinYou] | 2017/07/11 | 1 回/日 | × | × | × | × |
| [!DNL Jampp] | 2017/05/11 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Jivox] | 2017/08/30 | リアルタイム | × | × | × | × |
| [!DNL Juice Mobile] | 2017/03/03 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Krux] | 2017/06/30 | 1 回/日 | × | × | × | ○ |
| [!DNL Liftoff.io] | 2017/11/09 | 1 回/日 | ○ | × | × | ○ |
| [!DNL LiveIntent] | 2017/07/17 | 1 回/日 | ○ | × | × | × |
| [!DNL LiveRail] | 2017/01/20 | 1 回/日 |  | × | × |  |
| [!DNL Logicad] | 2017/06/22 | 1 回/日 | × | × | × | × |
| [!DNL Lotame] | 2017/06/30 | 1 回/日 | ○ | × | × | ○ |
| [!DNL MaxPoint Interactive] | 2017/02/27 | 1 回/日 | × | × | × | × |
| [!DNL MediaMath] | 2017/02/27 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Microsoft Bing Ads] | 2019/10/10 | リアルタイム | ○ | ○ | ○ | × |
| [!DNL Millennial Media] | 2017/02/27 | 1 回/日 | × | × | × | ○ |
| [!DNL mPlatform China] | 2018/08/06 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Narrative I/O] | 2018/01/12 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Native Touch] | 2017/03/02 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Nativo] | 2017/02/27 | 2 回/日 | ○ | × | × | × |
| [!DNL Mail.ru] | 2019/04/29 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Mobile Professionals] | 2018/05/25 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Netmining] | 2017/03/02 | リアルタイム | × | × | × | × |
| [!DNL Neustar] | 2017/03/28 | 1 回/日 | ○ | × | × | × |
| [!DNL OnAd] | 2017/02/13 | リアルタイム | ○ | × | ○ | × |
| [!DNL OneSpot] | 2017/06/19 | リアルタイム | ○ | × | × | ○ |
| [!DNL OpenX] | 2018/07/26 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Opera Mediaworks] | 2017/02/13 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Outbrain] | 2017/04/03 | 1 回/日 | ○ | × | × | × |
| [!DNL OwnerIQ] | 2017/02/13 | リアルタイム | ○ | × | ○ | × |
| [!DNL Platform 161] | 2018/11/28 | 1 回/日 | ○ | × | × | ○ |
| [!DNL PocketMath] | 2017/02/22 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Powerlinks] | 2017/05/17 | 1 回/日 | ○ | × | × | × |
| [!DNL Pubmatic] | 2017/02/13 | リアルタイム | × | × | × | × |
| [!DNL Pulsepoint] | 2017/02/13 | 1 回/日 | ○ | × | × | × |
| [!DNL PushSpring] | 2017/08/28 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Quantcast] | 2017/02/13 | リアルタイム | ○ | × | × | × |
| [!DNL RhythmOne / RadiumOne] | 2017/02/13 | リアルタイム | ○ | × | × | ○ |
| [!DNL Remerge] | 2017/05/31 | リアルタイム | ○ | × | ○ | ○ |
| [!DNL Resonate] | 2017/02/17 | 1 回/日 | ○ | × | × | × |
| [!DNL RevJet] | 2017/02/17 | 1 回/日 | × | × | × | × |
| [!DNL RocketFuel] | 2017/02/17 | リアルタイム | ○ | × | ○ | ○ |
| [!DNL Rubicon] |  | リアルタイム | ○ | ○ | × |  |
| [!DNL RUN] | 2017/02/17 | 1 回/日 | ○ | × | × | × |
| [!DNL RTB House] | 04/02/2021 | リアルタイム | ○ | × | ○ | ○ |
| [!DNL Sabio Mobile] | 2017/02/17 | 1 回/日 | × | × | × | ○ |
| [!DNL Simpli.fi] | 2017/02/17 | 1 回/日 | × | × | × | ○ |
| [!DNL Sizmek ad server (Amazon)] | 2017/02/17 | リアルタイム | ○ | × | × |  |
| [!DNL Slickdeals] | 2018/09/04 | リアルタイム | ○ | × | × | ○ |
| [!DNL Smart Adserver] | 2017/07/31 | リアルタイム | ○ | × | ○ | ○ |
| [!DNL So-net Media Networks Logicad] |  | 1 回/日 | ○ | × | × |  |
| [!DNL Sonobi] | 2017/03/28 | リアルタイム | ○ | × | ○ | × |
| [!DNL SpecificMedia] | 2017/03/03 | リアルタイム | × | × | × | × |
| [!DNL SpongeCell] | 2017/03/03 | リアルタイム | ○ | × | ○ | ○ |
| [!DNL SpotX] | 2018/03/16 | 1 回/日 | × | ○ | × | ○ |
| [!DNL Stroer] | 2017/03/03 | 1 回/日 | ○ | × | × | × |
| [!DNL SundaySky] | 2017/03/03 | リアルタイム | ○ | × | ○ | × |
| [!DNL StartApp] | 2018/05/25 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Supership]／[!DNL ScaleOut] | 2017/03/03 | 1 回/日 | ○ | × | × | × |
| [!DNL Survata] | 2017/08/09 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Taboola] | 2017/08/03 | 1 回/日 | × | ○ | × | × |
| [!DNL Tapad] | 17/07/2020 | リアルタイム | × | × | × | ○ |
| [!DNL Telaria] | 2019/04/25 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Telogical Systems] | 2017/03/03 | リアルタイム | ○ | × | × | × |
| [!DNL The Trade Desk] | 2017/03/03 | リアルタイム | ○ | ○ | ○ | ○ |
| [!DNL Thnk Realtime] | 2016/02/05 | リアルタイム |  | × | × |  |
| [!DNL Tremor Video] | 2017/03/03 | 1 回/日 | ○ | × | × | × |
| [!DNL Triple Lift] | 2017/03/03 | リアルタイム | × | ○ | × | × |
| [!DNL TrueX] | 2018/01/11 | リアルタイム | ○ | × | × | ○ |
| [!DNL TubeMogul] | 2017/03/03 | リアルタイム | ○ | × | ○ | × |
| [!DNL Turn]／[!DNL Amobee] | 2027/03/03 | リアルタイム | × | × | × | ○ |
| [!DNL Twenga] | 2018/10/29 | リアルタイム | ○ | × | × | × |
| [!DNL Twitter Tailored Audiences] | 2017/03/27 | リアルタイム | ○ | × | ○ | × |
| [!DNL Undertone] | 2017/07/11 | 1 回/日 | × | × | × | × |
| [!DNL Verve] | 2017/06/15 | 1 回/日 | ○ | × | × | ○ |
| [!DNL VideoAmp] | 2017/03/03 | リアルタイム | × | × | × | × |
| [!DNL Videology] | 2017/03/03 | 1 回/日 | × | × | × | × |
| [!DNL VisualIQ] | 2017/03/24 | 1 回/日 | ○ | × | × | × |
| [!DNL Wikibuy] | 2018/08/04 | リアルタイム | ○ | × | × | ○ |
| [!DNL X+1] | 2016/02/05 | 1 回/日 |  | × | × |  |
| [!DNL Xaxis] | 2017/03/03 | 1 回/日 | ○ | × | × | × |
| [!DNL Yahoo DataX] | 2017/03/03 | リアルタイム | ○ | ○ | ○ | ○ |
| [!DNL Yahoo! Japan] | 2017/03/03 | リアルタイム | × | × | × | × |
| [!DNL Yandex] | 2018/11/28 | 1 回/日 | ○ | × | × | ○ |
| [!DNL Yieldex] | 2017/08/21 | 様々 | ○ | × | × | × |
| [!DNL YieldMo] | 2017/03/03 | 1 回/日 | × | × | × | × |
| [!DNL Yume] | 2017/05/31 | 1 回/日 | × | × | × | × |
| [!DNL Zeta]／[!DNL Sizmek DSP]／[!DNL RocketFuel] | 2017/02/17 | リアルタイム | ○ | × | ○ | ○ |