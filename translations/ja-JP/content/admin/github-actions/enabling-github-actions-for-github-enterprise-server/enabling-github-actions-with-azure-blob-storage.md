---
title: Azure Blob ストレージで GitHub Actions を有効化する
intro: '{% data variables.product.prodname_ghe_server %} で {% data variables.product.prodname_actions %} を有効化し、Azure Blob ストレージを使用して、ワークフローの実行によって生成されたデータを保存できます。'
permissions: 'Site administrators can enable {% data variables.product.prodname_actions %} and configure enterprise settings.'
versions:
  ghes: '*'
type: how_to
topics:
  - Actions
  - Enterprise
  - Infrastructure
  - Storage
redirect_from:
  - /admin/github-actions/enabling-github-actions-with-azure-blob-storage
shortTitle: Azure Blob storage
ms.openlocfilehash: bcd92b12ec8ecd807906a3b2f7c09971d6641b93
ms.sourcegitcommit: fcf3546b7cc208155fb8acdf68b81be28afc3d2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2022
ms.locfileid: '145120453'
---
## 前提条件

{% data variables.product.prodname_actions %} を有効化する前に、次のステップを完了していることを確認してください。

* ワークフローデータを保存するための Azure ストレージアカウントを作成します。 {% data variables.product.prodname_actions %} はデータをブロック Blob として保存し、次の 2 つのストレージアカウントタイプがサポートされています。
  * **標準** パフォーマンスレベルを使用した **汎用** ストレージアカウント (`general-purpose v1` または `general-purpose v2` とも呼ばれている)。

    {% warning %}

    **警告:** 汎用ストレージアカウントでは **Premium** パフォーマンスレベルを使用できません。 ストレージアカウントを作成するときに **標準** のパフォーマンスレベルを選択する必要があり、後で変更することはできません。

    {% endwarning %}
  * **Premium** パフォーマンスレベルを使用する **BlockBlobStorage** ストレージアカウント。

  Azure ストレージアカウントの種類とパフォーマンスレベルについて詳しくは、[Azure のドキュメント](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-overview?toc=/azure/storage/blobs/toc.json#types-of-storage-accounts)を参照してください。
{% data reusables.actions.enterprise-common-prereqs %}

## Azure Blob ストレージで {% data variables.product.prodname_actions %} を有効化する

{% data reusables.enterprise_installation.ssh-into-instance %} {% data reusables.actions.perform-blob-storage-precheck %} {% data reusables.enterprise_site_admin_settings.access-settings %} {% data reusables.enterprise_site_admin_settings.management-console %} {% data reusables.enterprise_management_console.actions %} {% data reusables.actions.enterprise-enable-checkbox %}
1. [成果物とログストレージ] で、 **[Azure Blob Storage]** を選択し、Azure ストレージアカウントの接続文字列型を入力します。 ストレージアカウントの接続文字列の取得について詳しくは、[Azure ドキュメント](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal#view-account-access-keys)を参照してください。
  ![Azure Blob Storage と接続文字列フィールドを選ぶためのラジオボタン](/assets/images/enterprise/management-console/actions-azure-storage.png) {% data reusables.enterprise_management_console.save-settings %}

{% data reusables.actions.enterprise-postinstall-nextsteps %}
