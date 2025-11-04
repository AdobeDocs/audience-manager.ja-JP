---
description: Instant Cross-Device Suppression は、接続した複数のデバイスのいずれかで特定のエクスペリエンスが発生した場合に、複数のデバイスに接続したユーザーを抑制する機能です。Instant Cross-Device Suppression 機能を使用すると、ユーザーに複数のデバイスで一貫したエクスペリエンスを提供できます。このエクスペリエンスは、Audience Manager でのリアルタイムのセグメント化解除機能によって使用できるようになります。
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: Instant Cross-Device Suppression
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 85%

---

# Instant Cross-Device Suppression {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] は、接続した複数のデバイスのいずれかで特定のエクスペリエンスが発生した場合に、複数のデバイスに接続したユーザーを抑制する機能です。[!UICONTROL Instant Cross-Device Suppression] 機能を使用すると、ユーザーに複数のデバイスで一貫したエクスペリエンスを提供できます。このエクスペリエンスは、Audience Manager でのリアルタイムのセグメント化解除機能によって使用できるようになります。

## 概要 {#overview}

[!UICONTROL Instant Cross-Device Suppression] では、ユーザーエクスペリエンスの向上とメディア効率という 2 つの重要なユースケースを実現します。

* **ユーザーエクスペリエンスの向上**：製品やサービスを既に購入したユーザーには、購入前と同じクリエイティブは表示されません。代わりに、ユーザーがまだ購入していないことがわかっている製品やサービスのアップ販売メッセージまたはクロス販売メッセージを表示できます。
* **メディア効率**：すべての [!DNL DSP] にグローバルな頻度キャップを適用して、キャンペーン投資を最適化します。頻度キャップは、ユーザーに属する複数のデバイスに対してリアルタイムで実行できます。

リアルタイムのセグメント化解除の技術的な詳細については、[プロファイル結合ルールとデバイスセグメント化解除プロセス](merge-rule-unsegment.md)で説明しています。上記ユースケースの実用的な実装についても説明しています。

## コンバージョン後はターゲットにしない {#do-not-target-once}

既にコンバージョン済み（製品の購入、サブスクリプションの取得など）のユーザーには、コンバージョン前と同じメッセージが表示されないようにします。 次のように、[!UICONTROL AND NOT] ロジックを使用してこれを実現できます。

1. 次の図に示すように、2 つの特性を使用するセグメントを作成し、[!UICONTROL AND NOT] ロジックを使用します。ルールベースの特性を使用して、セグメント化解除がリアルタイムに起動されるようにコンバージョンイベントを定義する必要があります。詳しくは、[&#x200B; ルールベースの特性を作成 &#x200B;](../traits/create-onboarded-rule-based-traits.md) する方法を参照してください。
2. セグメントを任意の数のリアルタイムサーバー間宛先にマッピングします。[&#x200B; サーバー間宛先 &#x200B;](../destinations/add-edit-segments.md) にセグメントを追加する方法については、こちらを参照してください。

訪問者は、コンバージョンに達していない限り、セグメントの対象として認定されます。コンバージョン特性の対象として認定されしだい、訪問者はセグメントルールに従わなくなり、セグメントから即座に削除されます。

![](assets/and_not_use_case.png)

## インプレッション発生後はターゲットにしない {#do-not-target-after-x}

最新性と頻度のコントロールを設定することで、ユーザーに同じクリエイティブが大量に表示されるのを避けることができます。このシナリオでは、2 つの特性を使用するセグメントを作成します。その概要を次の手順で説明します。

1. 次の図に示すように、2 つの特性を使用するセグメントを作成し、[!UICONTROL AND] ロジックを使用します。ルールベースの特性を使用して、セグメント化解除がリアルタイムに起動されるようにインプレッションイベントを定義する必要があります。詳しくは、[&#x200B; ルールベースの特性を作成 &#x200B;](../traits/create-onboarded-rule-based-traits.md) する方法を参照してください。

   >[!NOTE]
   >
   >[!UICONTROL Actionable Log Files] または [!UICONTROL Pixel Calls] を使用して、ユーザーインプレッションに基づいて特性を作成できます。詳しくは、[実行可能なログファイル](../../integration/media-data-integration/actionable-log-files.md)および[ピクセル呼び出し](../../integration/media-data-integration/impression-data-pixels.md)を参照してください。

1. 2 番目の特性に頻度コントロールを適用します。必要に応じて、最新性コントロールも追加することができます。詳しくは、[&#x200B; 最新性と頻度の制御を適用する方法 &#x200B;](../segments/recency-and-frequency.md) を参照してください。
1. セグメントを任意の数のリアルタイムサーバー間宛先にマッピングします。[&#x200B; サーバー間宛先 &#x200B;](../destinations/add-edit-segments.md) にセグメントを追加する方法については、こちらを参照してください。

このシナリオでは、蓄積したユーザーのインプレッションが 3 個を超えたら、ユーザーはこのセグメントから削除され、この特定のクリエイティブはユーザーに表示されなくなります。

![](assets/impressions_use_case.png)

## 留意すべき重要な側面 - 処理 {#processing-notes}

処理に関しては、次の側面に留意してください。

* リアルタイムのセグメント化解除機能が働くためには、目的のセグメントをリアルタイムのサーバー間宛先にマッピングする必要があります。
* 複数のデバイスが[デバイスグラフ](profile-link-use-case.md#recommendations)で接続されている場合は、評価とセグメント化解除に関して、4 デバイスまでの制限が適用されます。この制限については、[デバイスグラフオプションとデバイスのセグメント化解除](merge-rule-unsegment.md#device-graph-options-unsegmentation)を参照してください。
* 複数のデバイスがデバイスグラフで接続されている場合、セグメント化解除コマンドは、24 時間ごとに宛先に送信されるバッチファイルに含まれています。
* リアルタイムでセグメント評価を促すには、デバイスが（[Edge](../../reference/system-components/components-edge.md) リアルタイムで表示される必要があります。 [!UICONTROL time-to-live (TTL)] を持つ特性では、特性 [!DNL TTL] を満たすと、バッチファイルを介して 24 時間以内に自動的にデバイスのセグメント化が解除されま&#x200B;す。詳しい方法については、[特性の有効期限間隔の設定](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)を参照してください。
* [!UICONTROL DCS API] を使用してルールベースの特性をリアルタイムにオンボードする場合は、[!UICONTROL AND NOT] ロジックを使用してセグメント化解除を起動することができます。詳しくは、[DCS API へのデータ送信](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)を参照してください。

## 留意すべき重要な側面 - 時間設定 {#timing-notes}

時間設定に関しては、次の側面に留意してください。

* セグメントは、デバイスプロファイルが [&#x200B; スト &#x200B;](../../reference/system-components/components-edge.md) ージに保存されるのと同じ期間（最後のリアルタイムインタラクションから 14 日間）で [!UICONTROL Edge]Edgeに保存されます。 データ保持について詳しくは、[データ保持に関する FAQ](../../faq/faq-privacy.md#data-retention-faq) を参照してください。
* セグメント化解除操作が [!DNL DCS] 地域全体に伝達されるまでに、およそ 24 時間かかります。[!DNL DCS] 地域の詳細については、[こちら](../../reference/system-components/components-data-collection.md)と[こちら](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)を参照してください。
