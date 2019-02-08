---
layout: page
title: Estrutura de diretórios
---

[Directory structure](https://jekyllrb.com/docs/structure/)

Jekyll é, em essência, um mecanismo de transformação de texto. O conceito por trás do sistema é o seguinte: você dá a ele um texto escrito em sua linguagem de marcação favorita, seja Markdown, [Textile](https://github.com/jekyll/jekyll-textile-converter), ou simplesmente HTML, e produz um layout ou uma série de arquivos de layout. Ao longo desse processo, você pode ajustar a aparência das URLs do site, quais dados são exibidos no layout e muito mais. Tudo isso é feito através da edição de arquivos de texto; o site estático é o produto final.

Um site Jekyll básico geralmente se parece com isso:

```bash
.
├── _config.yml
├── _data
|   └── members.yml
├── _drafts
|   ├── begin-with-the-crazy-ideas.md
|   └── on-simplicity-in-technology.md
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   └── post.html
├── _posts
|   ├── 2007-10-29-why-every-programmer-should-play-nethack.md
|   └── 2009-04-26-barcamp-boston-4-roundup.md
├── _sass
|   ├── _base.scss
|   └── _layout.scss
├── _site
├── .jekyll-metadata
└── index.html # can also be an 'index.md' with valid YAML Frontmatter
```

* Estrutura de diretórios dos sites do Jekyll usando temas baseados em gems
  Começando Jekyll 3.2, um novo projeto Jekyll bootstrapped com `jekyll new` usa temas baseados em gem para definir a aparência do site. Isso resulta em uma estrutura de diretório padrão mais clara: `_layouts`, `_includes` e `_sass` são armazenados no tema-gem, por padrão. Minima é o tema padrão atual, e `bundle show minima` mostrará onde os arquivos do tema minima são armazenados no seu computador.

Uma visão geral do que cada um deles faz:

`_config.yml`

*Armazena dados de configuração. Muitas dessas opções podem ser especificadas a partir do executável da linha de comando, mas é mais fácil especificá-las aqui para que você não precise se lembrar delas.*


`_drafts`

*Drafts(rascunhos) são posts não publicados. O formato desses arquivos é sem data: `title.MARKUP`. Aprenda a trabalhar com [drafts](https://jekyllrb.com/docs/drafts/).*


`_includes`

*Estas são as parciais que podem ser misturadas e combinadas por seus layouts e posts para facilitar a reutilização. A tag de liquid `{% include file.ext%}` pode ser usada para incluir a parcial em `_includes / file.ext`.*


`_layouts`

*Esses são os modelos que envolvem postagens. Layouts são escolhidos post-by-post no [YAML Front Matter](https://jekyllrb.com/docs/frontmatter/), que é descrito na próxima seção. A tag de liquid `{{content}}` é usada para injetar conteúdo na página da web.*


`_posts`

*Seu conteúdo dinâmico, por assim dizer. A convenção de nomenclatura desses arquivos é importante e deve seguir o formato: `YEAR-MONTH-DAY-title.MARKUP`. Os [permalinks](https://jekyllrb.com/docs/permalinks/) podem ser personalizados para cada postagem, mas a data e a linguagem de marcação são determinadas exclusivamente pelo nome do arquivo.*


`_data`

Dados do site bem formatados devem ser colocados aqui. O mecanismo do Jekyll carregará automaticamente todos os arquivos de dados (usando os formatos e extensões `.yml`, `.yaml`, `.json`, `.csv` ou `.tsv`) nesse diretório, e eles estarão acessíveis via 'site.data'. Se houver um arquivo `members.yml` no diretório, você poderá acessar o conteúdo do arquivo por meio de `site.data.members`.


`_sass`

Estes são sass parciais que podem ser importados para o seu `main.scss`, que então serão processados em uma única folha de estilos `main.css` que define os estilos a serem usados pelo seu site.


`_site`

É aqui que o site gerado será colocado (por padrão) assim que o Jekyll terminar de transformá-lo. Provavelmente, é uma boa ideia adicionar isso ao seu arquivo `.gitignore`.


`.jekyll-metadata`

Isso ajuda o Jekyll a controlar quais arquivos não foram modificados desde a última criação do site e quais arquivos precisarão ser regenerados na próxima construção. Este arquivo não será incluído no site gerado. Provavelmente, é uma boa ideia adicionar isso ao seu arquivo `.gitignore`.


`index.html` or `index.md` and other HTML, Markdown files

Contanto que o arquivo tenha uma seção [YAML Front Matter](https://jekyllrb.com/docs/frontmatter/), ele será transformado pelo Jekyll. O mesmo acontecerá com qualquer arquivo `.html`, `.markdown`, `.md` ou `.textile` no diretório raiz ou nos diretórios do seu site não listados acima.


Other Files/Folders

Todos os outros diretórios e arquivos, exceto os listados acima - como pastas de `CSS` e `images`, arquivos `favicon.ico` e assim por diante - serão copiados integralmente para o site gerado. Existem muitos [sites que já usam o Jekyll](https://jekyllrb.com/docs/sites/), se você está curioso para ver como eles são exibidos.

***
[back](./)