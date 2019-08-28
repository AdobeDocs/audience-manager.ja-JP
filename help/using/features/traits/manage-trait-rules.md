---
description: 特性ビルダーの式ビルダーを使用すると、オーディエンス認定要件を確立するルールを作成およびテストできます。ルールは、「color == blue」または「price > 100」などのキー値ペアで構成されます。比較演算子は、キーと値の間の関係を確立します。ブール式は、ルールグループ間の関係を判別します。
seo-description: 特性ビルダーの式ビルダーを使用すると、オーディエンス認定要件を確立するルールを作成およびテストできます。ルールは、「color == blue」または「price > 100」などのキー値ペアで構成されます。比較演算子は、キーと値の間の関係を確立します。ブール式は、ルールグループ間の関係を判別します。
seo-title: 特性ルールの管理
solution: Audience Manager
title: 特性ルールの管理
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
translation-type: ht
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 特性ルールの管理 {#managing-trait-rules}

[!UICONTROL Trait Builder] では、[!UICONTROL Expression Builder] を使用すると、オーディエンス資格要件を確立するルールを作成およびテストできます。ルールは、`color == blue` や `price > 100` などのキー値ペアで構成されます。比較演算子は、キーと値の間の関係を確立します。[!DNL Boolean] 式は、ルールグループ間の関係を判別します。

<!-- c_tb_rules.xml -->

## メインシグナルルール機能の説明

![](assets/manage-trait-rules.png)

1. 「**[!UICONTROL Expression Builder]**」または「**[!UICONTROL Code View]**」タブには、特性のルールの概要が表示されます。「**[!UICONTROL Expression Builder]**」を使用すると、フィールドおよびドロップダウンメニューを使用して、ルールを作成できます。「**[!UICONTROL Code View]**」を使用すると、手動でこれらの式をコードとして記述することで、ルールを作成できます。上の図に示したのは、製品キーが特定の値に等しいという認定条件（この場合、`color == "blue"`）でデータを評価するシグナルで構成されるシンプルな特性です。

1. このセクションのフィールドおよびコントロールを使用すると、キー値ペアからシグナルを作成して、比較演算子でそれらの間の関係を設定できます。キー、演算子および値が必要です。
1. 「[!UICONTROL Data Explorer Options]」を使用すると、シグナルに対する特性適合をバックフィルできます。
   >[!NOTE]
   >
   >このオプションを利用できるのは、[!UICONTROL Data Explorer] のお客様のみです。詳しくは、アドビのコンサルタントにお問い合わせください。
1. このセクションには、バックフィルの対象の特性と対象外の特性について、[!UICONTROL Expression Builder]で定義されたシグナルの過去 7 日間にわたる特性適合の推定値が表示されます。
   >[!NOTE]
   >
   >このオプションを利用できるのは、[!UICONTROL Data Explorer] のお客様のみです。詳しくは、アドビのコンサルタントにお問い合わせください。
1. テストフィールドを使用すると、Audience Manager にデータを送信する際に使用するシグナルルールまたは [!DNL URL] の組み合わせを検証できます。

## 特性ルールの作成 {#create-trait-rule}

ルール（または式）は、個々のキー値ペアまたはキー値ペアのグループで構成されます。比較演算子は、キー値ペアの間の関係を設定します。ルールを作成するには、キーと値を指定し、演算子を選択して、「**[!UICONTROL Add Rule]**」をクリックします。

<!-- t_tb_create_rules.xml -->

「**[!UICONTROL Basic Information]**」セクションの必須フィールドは、特性ルールを作成する&#x200B;*前*&#x200B;に入力します。

1. 「**[!UICONTROL Trait Expression]**」セクションを展開して、キーと値の名前を入力します。これにより、*`signal`* が作成されます。
   >[!NOTE]
   >
   >イベント呼び出しでデータを [!DNL Audience Manager] に送信するために必要であれば、キー変数でプレフィックス `c_`（またはその他の命名規則）を使用します。
1. 「**[!UICONTROL Operator]**」ドロップダウンから[比較演算子](../../features/traits/trait-comparison-operators.md)を選択します。比較演算子はシグナルの要素間の関係を比較します。
   >[!NOTE]
   >
   >[!DNL Boolean] 演算子 [!UICONTROL OR] はグループ&#x200B;*内*&#x200B;の複数のシグナル間の関係を確立します。これを変更することはできません。
1. 「**[!UICONTROL Add Rule]**」をクリックします。保存されたルールは、データ入力フィールドの上にある特性ワークスペースに表示されます。

### 例 {#example-trait-rule}

以下の例では、ユーザーが製品 ID に基づいて新しい特性ルールを作成します。このルールを作成するために、ユーザーはキー `productkey` を「次と等しい」演算子（`==`）により値 `2093` にリンクしています。
![](assets/tb_sample_rule1.png)

「**[!UICONTROL Add Rule]**」をクリックすると特性が保存され、[!UICONTROL Expression Builder]ワークスペースに移動します。

![](assets/tb_sample_rule2.png)

>[!MORE_LIKE_THIS]
>
>* [新しいルールグループの作成](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [グループ間でルールを移動](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [特性ルールの削除](../../features/traits/manage-trait-rules.md#delete-trait)


## 新しいルールグループの作成 {#create-rule-group}

この手順では、新しいルールグループの作成方法を説明します。

<!-- t_tb_new_rule_group.xml -->

新しいルールグループを作成する前に、特性に 2 つ以上のルールが含まれている必要があります。

1. 移動するルールにカーソルを移動して、ハイライト表示します。
1. ハイライト表示されたルールの境界線にカーソルを移動します。ルールが自動的に現在のグループから分離され、新しいグループに移動します。
   >[!NOTE]
   >
   >誤ってルールを移動してしまった場合は、ルールをドラッグして元のグループに戻します。
1. ドロップダウンメニューから [!DNL Boolean] 演算子（[!UICONTROL AND NOT]、[!UICONTROL AND]、[!UICONTROL OR]）を選択し、ルールグループ間の関係を設定します。

>[!MORE_LIKE_THIS]
>
>* [特性ルールの作成](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [グループ間でルールを移動](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [特性ルールの削除](../../features/traits/manage-trait-rules.md#delete-trait)


## グループ間でルールを移動 {#move-rules-between-groups}

ルールを移動するには、ルールをクリックして、別のグループにドラッグします。

>[!MORE_LIKE_THIS]
>
>* [特性ルールの作成](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [新しいルールグループの作成](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [特性ルールの削除](../../features/traits/manage-trait-rules.md#delete-trait)


## 特性の編集 {#edit-trait}

この手順では、特性の編集方法について説明します。

<!-- t_tb_edit.xml -->

1. [!UICONTROL Traits] ダッシュボードで、編集する特性の **[!UICONTROL Actions]** 列にカーソルを移動します。特性管理アイコンが表示されます。
1. 鉛筆アイコンをクリックして、特性を編集します。

   ![](assets/tb_edit_trait.png)

## 特性ルールの削除 {#delete-trait}

この手順では、特性ルールの削除方法について説明します。

<!-- t_tb_delete_rule.xml -->

1. [!UICONTROL Traits] ダッシュボードで、編集する特性の [!UICONTROL Actions] 列にカーソルを移動し、鉛筆アイコンをクリックします。特性管理アイコンが表示されます。
1. 「[!UICONTROL Trait Expression]」セクションを展開します。
1. 削除するルールにカーソルを移動し、「X」アイコンをクリックします。ルールが直ちに削除されます。