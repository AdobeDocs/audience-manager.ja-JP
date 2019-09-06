---
description: 'このページには、Audience Managerとユーザーベースのプラットフォーム間の統合を設定および管理する方法に関するガイダンスが含まれています。 '
seo-description: 'このページには、Audience Managerとユーザーベースのプラットフォーム間の統合を設定および管理する方法に関するガイダンスが含まれています。 '
seo-title: 人ベースのプラットフォームとの認証
solution: Audience Manager
title: 人ベースのプラットフォームとの認証
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# 人ベースのプラットフォームとの認証 {#authentication-with-people-based-platforms}

このページには、Audience Managerとユーザーベースのプラットフォーム間の統合を設定および管理する方法に関するガイダンスが含まれています。

>[!NOTE]
>これは、導入シナリオに関係なく、人ベースの宛先の必須ステップです。

## 人ベースのプラットフォーム認証の設定 {#configure-authentication}

1. Audience Managerアカウントにログインして **[!UICONTROL Administration]** 、/ **[!UICONTROL Integrated Accounts]**に移動します。以前にソーシャルプラットフォームとの統合が設定されている場合は、このページに表示されています。それ以外の場合、ページは空です。
   ![ユーザーベースの統合](assets/pbd-config.png)
1. 「**[!UICONTROL Add Account]**」をクリックします。
1. **[!UICONTROL People-Based Platform]** ドロップダウンメニューを使用して、統合を設定するプラットフォームを選択します。
   ![ユーザーベースのプラットフォーム](assets/pbd-add.png)
1. クリック **[!UICONTROL Confirm]** して、選択したプラットフォームの認証ページにリダイレクトします。
1. ソーシャルプラットフォームアカウントを認証すると、関連する広告主アカウントを表示するAudience Managerにリダイレクトされます。使用する広告主アカウントを選択し、をクリック **[!UICONTROL Confirm]**&#x200B;します。
1. Audience Managerは、ページの上部に通知を表示して、アカウントが正常に追加されたかどうかを通知します。また、ソーシャルプラットフォーム認証の有効期限が近づいている場合に通知を受信する連絡先電子メールアドレスを追加することもできます。

## 認証トークンの有効期限と通知管理 {#token-expiration-notification}

Audience Managerは、一定期間後に期限切れになる認証トークンを介して、ソーシャルプラットフォームと統合します。トークン有効期間の期間には、各ソーシャルプラットフォームの統合ルールが適用されます。認証トークンが有効期限切れになると、Audience Managerはオーディエンスセグメントを宛先に送信できません。このシナリオを避けるには、少なくとも1つの連絡先電子メールアドレスを統合に追加することをお勧めします。これにより、認証トークンが期限切れになるとすぐに通知が届きます。その場合、宛先が引き続きオーディエンスセグメントを受け取るように再認証できます。

ここでは、既存の統合に電子メールアドレスを追加する方法について説明します。

1. Audience Managerアカウントにログインして **[!UICONTROL Administration]** 、/ **[!UICONTROL Integrated Accounts]**&#x200B;に移動します。
1. トークン有効期限通知を受信する統合を識別し、 **[!UICONTROL Edit]** アイコンをクリックします。
1. トークン有効期限通知を受信する電子メールアドレスをコンマで区切って入力します。
1. 「**[!UICONTROL Save]**」をクリックします。

## 認証トークンの更新 {#token-renewal}

認証トークンが有効期限切れになると、Audience Managerと対応するソーシャルプラットフォームの統合が中断されるので、Audience Managerはオーディエンスセグメントを宛先に送信できません。[!UICONTROL Integrated Accounts] ページに [!UICONTROL Expiration] は、列の各統合の有効期限が表示され、いつでも認証を更新できます。

期限切れまたは期限切れの認証を更新する方法について、以下に示します。
1. Audience Managerアカウントにログインして **[!UICONTROL Administration]** 、/ **[!UICONTROL Integrated Accounts]**&#x200B;に移動します。
1. 認証の更新に必要な統合を特定します。有効期限切れの認証は、有効 [!UICONTROL Expired]期限が切れているとマークされ、有効期限切れの認証は、残りの認証日が表示されます。
1. 列の対応 **[!UICONTROL Renew]** するアイコンをクリック [!UICONTROL Expiration] します。これにより **[!UICONTROL Renew Account]** 、ソーシャルプラットフォームの認証ページから戻るワークフローがトリガーされます。認証が完了すると、新しい有効期限のトークンが更新されます。
   ![pbd- refresh](assets/pbd-renew.png)
