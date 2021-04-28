---
description: Audience Manager が Audience Optimization for Publishers を有効にする前に、この記事に記載されたすべての前提条件が満たされていることを確認してください。すべての前提条件を確認後、カスタマーケアにご連絡ください。
seo-description: Audience Manager が Audience Optimization for Publishers を有効にする前に、この記事に記載されたすべての前提条件が満たされていることを確認してください。すべての前提条件を確認後、カスタマーケアにご連絡ください。
seo-title: Google Ad Manager データファイルを Audience Manager に読み込む
solution: Audience Manager
title: Google Ad Manager データファイルを Audience Manager に読み込む
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization レポート
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
translation-type: ht
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: ht
source-wordcount: '570'
ht-degree: 100%

---

# Google Ad Manager（旧称 DFP）データファイルを Audience Manager に読み込む {#import-dfp-data-files-into-audience-manager}

Audience Manager が Audience Optimization for Publishers を有効にする前に、この記事に記載されたすべての前提条件が満たされていることを確認してください。すべての前提条件を確認後、カスタマーケアにご連絡ください。

## Google Ad Manager ログ取り込みの前提条件 {#prereqs-dfp-ingestion}

この節で説明している処理は、ログの取り込みを許可するための前提条件に進む&#x200B;*前*&#x200B;におこなってください。

[!DNL Audience Manager] で[!DNL Google Ad Manager]（以前の Google DFP）ログファイルを使用するには、まず広告タグ呼び出しで [Audience Manager の一意のユーザー ID（UUID）](../../../reference/ids-in-aam.md)を設定する必要があります。これにより、ID が [!DNL Google Ad Manager] ログに含まれ、[!DNL Google Ad Manager] と [!DNL Audience Manager] との間で ID を照合できるようになります。[!DNL Audience Manager] の [!UICONTROL DIL] コードまたは [!UICONTROL Audience Management Module] を使用して、[!DNL Audience Manager] UUID をファーストパーティの Cookie で設定します。

広告タグ呼び出しでの [!DNL Audience Manager] ID の設定方法は以下のとおりです（ドキュメントにも説明があります）。

* [Google Publisher Tag（GPT）を使用する](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Cookie 宛先を使用する](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

[!DNL Audience Manager] ID はご自身で設定する必要があります。また、[!DNL Audience Manager] コンサルタントを使用して、すべて正常であることを確認できます。次のようになっていれば、[!DNL Audience Manager] ID は正しく設定されています。

* 識別子として使用されているキーが `'aamid'` である。
* ユーザー ID 値が [Audience Manager で使用される ID の一覧](../../../reference/ids-in-aam.md)で説明されているように、正しく [!DNL Audience Manager] UUID の形式になっている。
* [!DNL Audience Manager] UUID が ログの定義済みフィールド（CustomTargeting など）に入力されている。[!DNL Google Ad Manager]

## ログの取り込みを許可するための前提条件 {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 手順 </th> 
   <th colname="col2" class="entry"> 詳細 </th> 
   <th colname="col3" class="entry"> 所有者 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>手順 1 </p> </td> 
   <td colname="col2"> <p>手順 2 に進む前に、<span class="keyword"> Audience Manager</span> UUID を設定するために必要な手順（上記で説明）が完了していることを確認してください。 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager カスタマーケアまたはコンサルタント</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>手順 2 </p> </td> 
   <td colname="col2"> <p>Google Ad Manager 管理者が作成します。 </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Google Ad Manager ログを <span class="keyword"> Audience Manager</span> に取り込むためのサービスアカウント。 </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">新しい資格情報。 <p>注意：このプロジェクト専用の電子メールアドレスが必要となる場合があります。この電子メールアドレスは、Google Storage Bucket へのアクセスのプロビジョニングに使用されます。 </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">秘密鍵（JSON ベースの資格情報）。 </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Google Ad Manager 管理者 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>手順 3 </p> </td> 
   <td colname="col2"> <p>Gogle Ad Manager がサービスアカウントへの API アクセスを許可します。この手順により、寸法を説明するメタデータ（行項目、オーダー、クリエイティブ）へのアクセスが可能になります。 <p>注意：API にアクセスする権限を許可するには、手順 2 で設定したサービスアカウント電子メールアクセスを使用します。 </p> </p> </td> 
   <td colname="col3"> <p>Google Ad Manager 管理者 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>手順 4 </p> </td> 
   <td colname="col2"> <p>Google Ad Manager が、Google Storage Bucket へのアクセスを確立します。以下の点に注意してください。 </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">この処理は Google グループからおこなうことができます。 </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">サービスアカウントに関連付けられた一意の電子メールアドレスを、ストレージバケットに関連付けます。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Google Ad Manager 管理者 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>手順 5 </p> </td> 
   <td colname="col2"> <p>Google Ad Manager のネットワーク ID は、Google Ad Manager 管理者が入力します。これにより、API を呼び出す際にネットワーク ID を渡すことができます。 </p> </td> 
   <td colname="col3"> <p>Google Ad Manager 管理者 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>手順 6 </p> </td> 
   <td colname="col2"> <p>前提条件をまとめて AAM カスタマーケア（aamsupport@adobe.com）宛てに電子メールで送信し、ログの取り込み処理を開始します。次のセクションのテンプレートを使用して、電子メールの下書きを作成します。 </p> </td> 
   <td colname="col3"> <p>自分または <span class="keyword"> Audience Manager</span> コンサルタントが代理で実行 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 電子メールのテンプレート {#email-template}

ログの取り込みの有効化を最終決定するには、aamsupport@adobe.com に電子メールを送信します。[添付の電子メールテンプレート](assets/enable_dfp_ingestion.txt)を使用してください。
