---
description: 'このページには、Audience Manager とユーザーベースのプラットフォーム間の統合を設定および管理する方法に関するガイダンスが含まれています。 '
seo-description: 'このページには、Audience Manager とユーザーベースのプラットフォーム間の統合を設定および管理する方法に関するガイダンスが含まれています。 '
seo-title: ユーザーベースのプラットフォームを使用した認証
solution: Audience Manager
title: ユーザーベースのプラットフォームを使用した認証
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# ユーザーベースのプラットフォームを使用した認証{#authentication-with-people-based-platforms}

このページには、Audience Manager とユーザーベースのプラットフォーム間の統合を設定および管理する方法に関するガイダンスが含まれています。

>[!NOTE]
>この手順は、導入シナリオに関係なく、People-Based Destinations では必須です。

## ユーザーベースのプラットフォーム認証の設定 {#configure-authentication}

1. Audience Manager アカウントにログインして、**[!UICONTROL Administration]**／**[!UICONTROL Integrated Accounts]** に移動します。ソーシャルプラットフォームとの統合を設定したことがある場合は、このページに表示されます。それ以外の場合、ページは空になります。
   ![ユーザーベースの統合](assets/pbd-config.png)
1. 「**[!UICONTROL Add Account]**」をクリックします。
1. **[!UICONTROL People-Based Platform]** ドロップダウンメニューを使用して、統合を設定するプラットフォームを選択します。
   ![ユーザーベースのプラットフォーム](assets/pbd-add.png)
1. 「**[!UICONTROL Confirm]**」をクリックすると、選択したプラットフォームの認証ページにリダイレクトされます。
1. ソーシャルプラットフォームアカウントを認証すると、Audience Manager にリダイレクトされ、関連する広告主アカウントが表示されます。使用する広告主アカウントを選択し、「**[!UICONTROL Confirm]**」をクリックします。
1. Audience Manager のページ上部に通知が表示され、アカウントが正常に追加されたかどうかがわかります。また、連絡先電子メールアドレスを追加して、ソーシャルプラットフォーム認証の有効期限が近づいたら通知を受け取ることもできます。

## 認証トークンの有効期限と通知管理 {#token-expiration-notification}

Audience Manager は、一定期間後に期限切れになる認証トークンを介して、ソーシャルプラットフォームとの統合を処理します。トークン有効期間には、各ソーシャルプラットフォームの統合ルールが適用されます。認証トークンの期限が切れると、Audience Manager はオーディエンスセグメントを宛先に送信できなくなります。このシナリオを避けるには、1 つ以上の連絡先電子メールアドレスを統合に追加することをお勧めします。これにより、認証トークンが期限切れになるとすぐに通知が届きます。通知が届いたら、引き続きオーディエンスセグメントが宛先に届くよう、再認証できます。

ここでは、既存の統合に電子メールアドレスを追加する方法について説明します。

1. Audience Manager アカウントにログインして、**[!UICONTROL Administration]**／**[!UICONTROL Integrated Accounts]** に移動します。
1. トークンの有効期限通知を受信する統合を特定し、**[!UICONTROL Edit]** アイコンをクリックします。
1. トークンの有効期限通知を受信する電子メールアドレスを、コンマ区切りで入力します。
1. 「**[!UICONTROL Save]**」をクリックします。

## 認証トークンの更新 {#token-renewal}

認証トークンが有効期限切れになると、Audience Manager と対応するソーシャルプラットフォームの統合が中断されるので、Audience Manager はオーディエンスセグメントを宛先に送信できなくなります。[!UICONTROL Integrated Accounts] ページには、[!UICONTROL Expiration] 列の各統合の有効期限が表示され、いつでも認証を更新できます。

期限切れまたは期限切れの認証を更新する方法は、次のとおりです。
1. Audience Manager アカウントにログインして、**[!UICONTROL Administration]**／**[!UICONTROL Integrated Accounts]** に移動します。
1. 認証の更新に必要な統合を特定します。有効期限切れの認証は、[!UICONTROL Expired] とマークされ、有効期限が近づいている認証には、残りの日数が表示されます。
1. [!UICONTROL Expiration] 列で、対応する **[!UICONTROL Renew]** アイコンをクリックします。これにより、ソーシャルプラットフォームの認証ページから戻る **[!UICONTROL Renew Account]** ワークフローがトリガーされます。認証が完了すると、新しい有効期限でトークンが更新されます。
   ![pbd-renew](assets/pbd-renew.png)
