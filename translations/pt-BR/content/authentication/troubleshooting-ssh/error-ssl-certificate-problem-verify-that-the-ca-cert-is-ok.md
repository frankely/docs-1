---
title: 'Erro: problema na certificação SSL, verifique se a cert CA está OK'
intro: 'O erro indica que o certificado CA root está desatualizado. Não será possível fazer push ou pull nos repositórios {% data variables.product.product_name %} se houver necessidade de atualizar o certificado CA root.'
redirect_from:
  - /articles/error-ssl-certificate-problem-verify-that-the-ca-cert-is-ok
  - /github/authenticating-to-github/error-ssl-certificate-problem-verify-that-the-ca-cert-is-ok
  - /github/authenticating-to-github/troubleshooting-ssh/error-ssl-certificate-problem-verify-that-the-ca-cert-is-ok
versions:
  fpt: '*'
  ghec: '*'
topics:
  - SSH
shortTitle: SSL certificate problem
ms.openlocfilehash: 26777edf5b312c8f45c5b1fb211b87648778cf13
ms.sourcegitcommit: fcf3546b7cc208155fb8acdf68b81be28afc3d2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2022
ms.locfileid: '145083547'
---
Você receberá a seguinte mensagem de erro:

```shell
$ git push -u github.main
> fatal: 'github.main' does not appear to be a git repository
> fatal: The remote end hung up unexpectedly

$ git pull -u github
> error: SSL certificate problem, verify that the CA cert is OK. Details:
> error:14090086:SSL routines:SSL3_GET_SERVER_CERTIFICATE:certificate verify failed while accessing https://github.com/tqisjim/google-oauth.git/info/refs
> fatal: HTTP request failed
```

"CA" é a abreviatura de "certificate authority" (autoridade certificada), um grupo terceiro responsável por gerenciar conexões seguras na Web. Esse grupo estabelece "certificados" digitais, que são uma forma de garantir que existem conexões válidas entre duas máquinas (por exemplo, seu computador e o GitHub.com). Sem um certificado, o risco de segurança entre duas máquinas é maior.

Ao receber essa mensagem de erro, provavelmente seu CA está desatualizado e precisa ser atualizado. Atualizar seu sistema operacional normalmente também atualiza seu CA e o problema é resolvido.
