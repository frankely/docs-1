---
ms.openlocfilehash: de2ab71ca5c93229329c2887dc71685aa92e199d
ms.sourcegitcommit: fcf3546b7cc208155fb8acdf68b81be28afc3d2d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "145065925"
---
可以指定单个事件或多个事件。 例如，当推送到存储库中的任何分支或有人创建存储库的分支时，将运行具有以下 `on` 值的工作流：

```yaml
on: [push, fork]
```

如果指定多个事件，仅需发生其中一个事件就可触发工作流。 如果触发工作流的多个事件同时发生，将触发多个工作流运行。
