---
title: Adicionar conteúdo ao site do GitHub Pages usando o Jekyll
intro: 'É possível adicionar uma nova página ou postagem ao site do Jekyll no {% data variables.product.prodname_pages %}.'
product: '{% data reusables.gated-features.pages %}'
redirect_from:
  - /articles/adding-content-to-your-github-pages-site-using-jekyll
  - /github/working-with-github-pages/adding-content-to-your-github-pages-site-using-jekyll
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Pages
shortTitle: Add content to Pages site
ms.openlocfilehash: 90bd0d067837364eb2767739da286da7906399c0
ms.sourcegitcommit: fb047f9450b41b24afc43d9512a5db2a2b750a2a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/11/2022
ms.locfileid: '145128197'
---
Pessoas com permissões de gravação para um repositório podem adicionar conteúdo a um site do {% data variables.product.prodname_pages %} usando o Jekyll.

## Sobre conteúdo em sites do Jekyll

Para poder adicionar conteúdo a um site do Jekyll no {% data variables.product.prodname_pages %}, você precisa criar o site do Jekyll. Para obter mais informações, confira "[Como criar um site do {% data variables.product.prodname_pages %} com o Jekyll](/articles/creating-a-github-pages-site-with-jekyll)".

Os principais tipos de conteúdo para sites do Jekyll são páginas e postagens. As páginas se destinam a conteúdo autônomo que não está associado a uma data específica, como uma página "Sobre". O site padrão do Jekyll contém um arquivo chamado `about.md`, que é renderizado como uma página no seu site em `YOUR-SITE-URL/about`. Você pode editar o conteúdo desse arquivo para personalizar a página "Sobre" e usá-la como um modelo para criar novas páginas. Para obter mais informações, confira "[Páginas](https://jekyllrb.com/docs/pages/)" na documentação do Jekyll.

As postagens são uma postagem de blog. O site padrão do Jekyll contém um diretório chamado `_posts` que contém um arquivo de postagem padrão. Você pode editar o conteúdo dessa postagem e usá-la como modelo para criar novas postagens. Para obter mais informações, confira "[Postagens](https://jekyllrb.com/docs/posts/)" na documentação do Jekyll.

O tema engloba layouts, inclusões e folhas de estilo padrão que serão aplicados automaticamente a novas páginas e postagens no site, mas é possível substituir qualquer um desses padrões. Para obter mais informações, confira "[Sobre o {% data variables.product.prodname_pages %} e o Jekyll](/articles/about-github-pages-and-jekyll#themes)".

{% data reusables.pages.about-front-matter %}

{% data reusables.pages.test-locally %}

## Adicionar uma nova página ao site

{% data reusables.pages.navigate-site-repo %} {% data reusables.pages.navigate-publishing-source %}
3. Na raiz da fonte de publicação, crie um arquivo para sua página chamado _PAGE-NAME.md_, substituindo _PAGE-NAME_ por um nome de arquivo significativo para a página.
4. Adicione o frontmatter YAML a seguir ao início do arquivo, substituindo _PAGE TITLE_ pelo título da página e _URL-PATH_ por um caminho desejado para a URL da página. Por exemplo, se a URL base do site for `https://octocat.github.io` e a _URL-PATH_ for `/about/contact/`, a página estará localizada em `https://octocat.github.io/about/contact`.
  ```shell
  layout: page
  title: "<em>PAGE TITLE</em>"
  permalink: /<em>URL-PATH</em>/
  ```
5. Abaixo da página inicial, adicione conteúdo para a página.
{% data reusables.files.write_commit_message %} {% data reusables.files.choose-commit-email %} {% data reusables.files.choose_commit_branch %} {% data reusables.files.propose_file_change %} {% data reusables.files.choose_pull_request %} {% data reusables.files.merge_pull_request %} {% data reusables.files.write_commit_message_pull_request %} {% data reusables.files.confirm_merge %} {% data reusables.files.delete_branch %}

## Adicionar uma nova postagem ao site

{% data reusables.pages.navigate-site-repo %} {% data reusables.pages.navigate-publishing-source %}
3. Navegue até o diretório `_posts`.
4. Crie um arquivo chamado _YYYY-MM-DD-NAME-OF-POST.md_, substituindo _YYYY-MM-DD_ pela data da postagem e _NAME-OF-POST_ pelo nome da postagem.
4. Adicione o frontmatter YAML a seguir ao início do arquivo, substituindo _POST TITLE_ pelo título da postagem, _YYYY-MM-DD hh:mm:ss -0000_ pela data e pela hora da postagem e _CATEGORY-1_ e _CATEGORY-2_ pela quantidade de categorias que deseja fornecer para a postagem.
  ```shell
  layout: post
  title: "<em>POST TITLE</em>"
  date: </em>YYYY-MM-DD hh:mm:ss -0000</em>
  categories: <em>CATEGORY-1</em> <em>CATEGORY-2</em>
  ```
5. Abaixo da página inicial, adicione conteúdo para a postagem.
{% data reusables.files.write_commit_message %} {% data reusables.files.choose-commit-email %} {% data reusables.files.choose_commit_branch %} {% data reusables.files.propose_file_change %} {% data reusables.files.choose_pull_request %} {% data reusables.files.merge_pull_request %} {% data reusables.files.write_commit_message_pull_request %} {% data reusables.files.confirm_merge %} {% data reusables.files.delete_branch %}

Seu post já deve estar no seu site! Se a URL base do site for `https://octocat.github.io`, a nova postagem estará localizada em `https://octocat.github.io/YYYY/MM/DD/TITLE.html`.

## Próximas etapas

{% data reusables.pages.add-jekyll-theme %} Para obter mais informações, confira "[Como adicionar um tema ao seu site do {% data variables.product.prodname_pages %} usando o Jekyll](/articles/adding-a-theme-to-your-github-pages-site-using-jekyll)".
