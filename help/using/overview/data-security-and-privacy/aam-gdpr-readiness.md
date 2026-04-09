---
description: Audience Manager をご利用のお客様向けの GDPR 対応ガイダンス
seo-description: GDPR Readiness Guidance for Audience Manager Customers
seo-title: GDPR Readiness Guidance for Audience Manager Customers
solution: Audience Manager
title: Audience Manager をご利用のお客様向けの GDPR 対応ガイダンス
feature: Data Governance & Privacy
exl-id: 353b9035-20f3-41ff-819c-71f161e6b1e1
TQID: https://experienceleague.adobe.com/K72pQ8Q6yILWexkG38Hc5W1roYObFvhLE5A0GSCyhYE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 461
ht-degree: 90%

---

# Audience Manager をご利用のお客様（データ管理者）向けの GDPR 対応ガイダンス {#gdpr-readiness-guidance}

Audience Manager はデータガバナンスと組織的準備の分野に積極的に取り組むことをお勧めします。これにより、消費者データのアクセス要求または削除要求に関連するプロセスが体系化され、チームのメンバーはこれらの要求を容易に管理できるようになるので、自社ブランドに対して好意的な印象を消費者（データ主体）に与えることができ、エクスペリエンスの差別化を図ることができます。

アドビはデータ処理者であるので、GDPR 要求、およびデータ主体からの合意の取得のプロセスに関して、法的なアドバイスを提供することはできません。御社の GDPR への準拠に関しては、御社の顧問弁護士にアドバイスを求めてください。

## データガバナンス：Audience Manager インスタンスにおける消費者データの管理方法について検討を始めてください

* Audience Manager でユーザーを特定するためにマーケティングチームが使用している様々な顧客 ID、およびそれらが保存されているデータソースを確認してください。データの種類によっては Audience Manager に取り込まれる前に御社内でハッシュ化されるので、これにより要求プロセス（削除やアクセスなど）を効率化することができます。
* IDFA／GAID モバイルデバイス ID は、Audience Manager において複数の用途で使用されます。Adobe Mobile SDK を使用している場合、GDPR に関して完全な応答を得るために、必ず Experience Cloud ID （MID）および IDFA／GAID を送信してください。
* 個人データの定義の適用範囲が拡大する中で、地域によっては IP アドレスも個人データと見なされる可能性があります。アドビのコンサルタントチームと積極的にご相談のうえ、最終オクテットの不明化をおこなってください。
* GDPR 要求の際にデータ主体の本人確認をおこなうための検証／認証のポリシーおよびプロセスを決定してください。
* [&#x200B; データ書き出し制御](../../features/data-export-controls.md)を使用して、個人データを格納するテクノロジーへのオーディエンスのアクティブ化をブロックすることを検討してください。 例えば、サードパーティのデータが含まれるセグメントは、電子メールサービスプロバイダーに配信すべきではありません。[!UICONTROL Data Export Control] を設定することで、社内の誰かが誤ってこのデータをアクティブ化してしまうことを防ぐことができます。
* [ロールベースのアクセス制御](../../features/administration/administration-overview.md)を導入して、適切なチームが意図したデータにのみアクセスできるようにしてください。
* 適切なデータの[保持期間](../../faq/faq-privacy.md#data-retention-faq)を検討してください。
* IDのリンクとプライバシーポリシーおよび法的要件を確認して、ID セットを結び付けるタイミングと場所を確認します。Audience Managerの[Profile Merge Rules](../../features/profile-merge-rules/merge-rules-overview.md)を使用して適切に使用します。

## 組織的準備：ビジネスプロセスの構築

* データ主体からの要求を受信し応答するためのプロセスを確認してください。Audience Manager に対して要求を送信するための自動ツールを構築することを検討してください。
* DMP の中核的チーム内でプライバシー担当者を任命してください。入力 ID の要件に関する理解を共有するために、プライバシー担当者と Audience Manager 製品を使用する部署を連携させてください。
* データ主体と共有する前に、データのレビューをおこなってください。責任の所在を明確にするために、手順をドキュメント化してください。
