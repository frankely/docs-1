---
title: 关于 GitHub 上的合并方法
intro: '您可以允许能够推送到仓库的贡献者使用不同的合并选项在 {% data variables.product.product_location %} 上合并其推送请求，或者对所有仓库的拉取请求实施特定的合并方法。'
redirect_from:
  - /articles/about-merge-methods-on-github
  - /github/administering-a-repository/about-merge-methods-on-github
  - /github/administering-a-repository/configuring-pull-request-merges/about-merge-methods-on-github
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Repositories
shortTitle: About merge methods
ms.openlocfilehash: 97e8b7159ebadf1fe02ae56f707728c2bc8c439d
ms.sourcegitcommit: 1309b46201604c190c63bfee47dce559003899bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: '145863780'
---
{% data reusables.pull_requests.configure_pull_request_merges_intro %} 您可以只对仓库启用所需的方法，以实施一种合并方法，如提交压缩或变基。

{% ifversion fpt or ghec %} {% note %}

注意：使用合并队列时，你将无法再选择合并方法，因为这由队列控制。 {% data reusables.pull_requests.merge-queue-references %}

{% endnote %} {% endif %}

{% data reusables.pull_requests.default_merge_option %}

默认合并方法创建合并提交。 通过强制实施线性提交历史记录，可以防止任何人将合并提交推送到受保护分支。 有关详细信息，请参阅“[关于受保护的分支](/github/administering-a-repository/about-protected-branches#require-linear-history)”。

## 压缩合并提交

{% data reusables.pull_requests.squash_and_merge_summary %}

在启用压缩提交之前，请考虑以下缺点：
- 您会丢失关于最初何时执行了特定更改以及是谁进行了压缩提交的信息。
- 如果在压缩与合并后继续操作拉取请求的头部分支，然后在相同分支之间创建新的拉取请求，您先前被压缩与合并的提交将列于新的拉取请求中。 可能还有必须在每个连续的拉取请求中反复解决的冲突。 有关详细信息，请参阅“[关于拉取请求合并](/github/collaborating-with-issues-and-pull-requests/about-pull-request-merges#squashing-and-merging-a-long-running-branch)”。
- 有些使用 "SHA" 或“哈希”ID 的 Git 命令可能更难使用，因为原始提交的 SHA ID 已经丢失。 例如，使用 [`git rerere`](https://git-scm.com/docs/git-rerere) 可能不那么有效。

有关详细信息，请参阅“[为拉取请求配置提交压缩](/articles/configuring-commit-squashing-for-pull-requests)”。

## 变基和合并提交

{% data reusables.pull_requests.rebase_and_merge_summary %}

在启用提交变基之前，请考虑以下缺点：
- 存储库参与者可能必须在命令行上变基、解决所有冲突，并将其更改推送到拉取请求的主题分支（或删除头分支），然后才可在 {% data variables.product.product_location %} 上使用“变基和合并”选项。 强制推送必须谨慎执行，以免贡献者覆盖别人在其工作基础上所做的工作。 若要详细了解何时在 {% data variables.product.product_location %} 上禁用“变基和合并”选项，并了解用于重新启用它的工作流，请参阅“[关于拉取请求合并](/articles/about-pull-request-merges/#rebase-and-merge-your-pull-request-commits)”。
- {% indented_data_reference reusables.pull_requests.rebase_and_merge_verification spaces=3 %}

有关详细信息，请参阅“[为拉取请求配置提交变基](/articles/configuring-commit-rebasing-for-pull-requests)”。
