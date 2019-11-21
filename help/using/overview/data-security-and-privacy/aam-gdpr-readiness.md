---
description: Audience Managerのお客様向けGDPR対応ガイダンス
seo-description: Audience Managerのお客様向けGDPR対応ガイダンス
seo-title: Audience Managerのお客様向けGDPR対応ガイダンス
solution: Audience Manager
title: Audience Managerのお客様向けGDPR対応ガイダンス
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# Audience Manager をご利用のお客様（データ管理者）向けの GDPR 対応ガイダンス{#gdpr-readiness-guidance}

Audience Managerは、データ管理と組織の準備に関する事前対応型の作業を推奨します。 これにより、顧客データをアクセスまたは削除の要求に関連するプロセスに対して整理し、チームを有効にして、これらの要求を管理し、顧客(Data Subjects)がブランドに対して積極的で差別化されたエクスペリエンスを得ることができます。

お客様のデータプロセッサとして、アドビは、GDPR要件とお客様のデータサブジェクトから同意を得るためのプロセスに関する法的なアドバイスを提供できません。 貴社のGDPRコンプライアンスに関するガイダンスについては、弁護士にお問い合わせください。

## データガバナンス：Audience Manager インスタンスにおける消費者データの管理方法について検討を始めてください

* Audience Manager でユーザーを特定するためにマーケティングチームが使用している様々な顧客 ID、およびそれらが保存されているデータソースを確認してください。データの種類によっては Audience Manager に取り込まれる前に御社内でハッシュ化されるので、これにより要求プロセス（削除やアクセスなど）を効率化することができます。
* IDFA／GAID モバイルデバイス ID は、Audience Manager において複数の用途で使用されます。Adobe Mobile SDK を使用している場合、GDPR に関して完全な応答を得るために、必ず Experience Cloud ID （MID）および IDFA／GAID を送信してください。
* 個人データの定義の適用範囲が拡大する中で、地域によっては IP アドレスも個人データと見なされる可能性があります。アドビのコンサルタントチームと積極的にご相談のうえ、最終オクテットの不明化をおこなってください。
* GDPR 要求の際にデータ主体の本人確認をおこなうための検証／認証のポリシーおよびプロセスを決定してください。
* 個人データを扱う技術システムにおいてオーディエンスアクティベーションを防ぐためには、[データエクスポートのコントロール](../../features/data-export-controls.md)を使用することを検討してください。例えば、サードパーティのデータが含まれるセグメントは、電子メールサービスプロバイダーに配信すべきではありません。[!UICONTROL Data Export Control] を設定することで、社内の誰かが誤ってこのデータをアクティブ化してしまうことを防ぐことができます。
* [ロールベースのアクセス制御](../../features/administration/administration-overview.md)を導入して、適切なチームが意図したデータにのみアクセスできるようにしてください。
* 適切なデータの[保持期間](../../faq/faq-privacy.md#data-retention-faq)を検討してください。
* 一連の ID をいつどこでまとめるべきかを検討するために、また、Audience Manager の[プロファイル結合ルール](../../features/profile-merge-rules/merge-rules-overview.md)。

## 組織的準備：ビジネスプロセスの構築

* データ主体からの要求を受信し応答するためのプロセスを確認してください。Audience Manager に対して要求を送信するための自動ツールを構築することを検討してください。
* DMP の中核的チーム内でプライバシー担当者を任命してください。入力 ID の要件に関する理解を共有するために、プライバシー担当者と Audience Manager 製品を使用する部署を連携させてください。
* データ主体と共有する前に、データのレビューをおこなってください。責任の所在を明確にするために、手順をドキュメント化してください。
