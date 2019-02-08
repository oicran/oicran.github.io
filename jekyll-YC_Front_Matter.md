---
layout: page
title: Front Matter
---

[Front Matter](https://jekyllrb.com/docs/frontmatter/)

O assunto principal é onde o Jekyll começa a ficar bem legal. Qualquer arquivo que contenha um bloco de assuntos frontais do [YAML](http://yaml.org/) será processado pelo Jekyll como um arquivo especial. O assunto da frente deve ser a primeira coisa no arquivo e deve assumir a forma de YAML válido definido entre linhas tracejadas triplas. Aqui está um exemplo básico:

```bash
---
layout: post
title: Blogging Like a Hacker
---
```

Entre essas linhas tracejadas triplas, você pode definir variáveis predefinidas (veja abaixo uma referência) ou até mesmo criar as suas próprias. Essas variáveis estarão disponíveis para você acessar usando tags Liquid mais abaixo no arquivo e também em qualquer layouts ou includes que a página ou postagem em questão depender.

    * Se você usar a codificação UTF-8, certifique-se de que não existam caracteres de cabeçalho `BOM` da lista de materiais em seus arquivos ou coisas muito ruins acontecerão com o Jekyll. Isso é especialmente relevante se você estiver executando o Jekyll no Windows.

*ProTip ™: Variáveis de Matéria da Frente São Opcionais*
*Se você quiser usar tags e variáveis liquid, mas não precisa de nada em seu assunto, apenas deixe em branco! O conjunto de linhas tracejadas triplo com nada entre elas fará com que Jekyll processe seu arquivo. (Isso é útil para coisas como CSS e feeds RSS!)*

### Variáveis Globais Predefinidas

Há um número de variáveis globais predefinidas que você pode definir na primeira página de uma página ou postagem.


Variável: `layout`

Descrição: Se definido, isso especifica o arquivo de layout a ser usado. Use o nome do arquivo de layout sem a extensão do arquivo. Arquivos de layout devem ser colocados na pasta `_layouts`.

    * Usando `null` produzirá um arquivo sem usar um arquivo de layout. No entanto, isso é substituído se o arquivo for um post/document e tiver um layout definido nos [padrões de frontmatter](https://jekyllrb.com/docs/configuration/#front-matter-defaults).
    
    * A partir da versão 3.5.0, usar `none` em um post/document produzirá um arquivo sem usar um arquivo de layout, independentemente dos padrões de frontmatter. Usar `none` em uma página, no entanto, fará com que o Jekyll tente usar um layout chamado "none".


Variável: `permalink`

Descrição: Se você precisar que seus URLs de postagens de blog processados sejam algo diferente do estilo de todo o site (padrão `/year/month/day/title.html`), você poderá definir essa variável e ela será usada como o URL final.


Variável: `published`

Descrição: Defina como `false` se você não quiser que uma postagem específica seja exibida quando o site for gerado.

  * ProTip ™: Renderizar Posts Marcados como Não-publicados
    Para pré-visualizar as páginas não publicadas, simplesmente execute `jekyll serve` ou`jekyll build` com o parâmetro `--unpublished`. O Jekyll também tem um recurso de [drafts](https://jekyllrb.com/docs/drafts/) à mão especialmente desenvolvido para postagens de blog.

### [Variáveis Personalizadas](https://jekyllrb.com/docs/frontmatter/#custom-variables)

Quaisquer variáveis no front matter que não são predefinidas são misturadas nos dados que são enviados para o Liquid template durante a conversão. Por exemplo, se você definir um título, poderá usá-lo no layout para definir o título da página:

```
<!DOCTYPE HTML>
<html>
  <head>
    <title>{{ page.title }}</title>
  </head>
  <body>
    …
```

### [Variáveis Predefinidas para Postagens](https://jekyllrb.com/docs/frontmatter/#predefined-variables-for-posts)

Estes estão disponíveis para uso imediato (out-of-the-box) no front matter de um post.


Variável: `date`

Descrição: Uma data aqui substitui a data do nome da postagem. Isso pode ser usado para garantir a classificação correta das postagens. Uma data é especificada no formato `YYYY-MM-DD HH:MM:SS +/-TTTT`; horas, minutos, segundos e deslocamento de fuso horário são opcionais.


Variável: `category`  `categories`

Descrição: Em vez de colocar posts dentro de pastas, você pode especificar uma ou mais categorias às quais a postagem pertence. Quando o site é gerado, o post agirá como se tivesse sido definido com essas categorias normalmente. Categories (no plural) podem ser especificadas como uma [lista YAML](https://en.wikipedia.org/wiki/YAML#Basic_components) ou uma string separada por espaços.


Variável: `tags`

Descrição: Semelhante a categorias, uma ou várias tags podem ser adicionadas a uma postagem. Também como categorias, as tags podem ser especificadas como uma lista YAML ou uma string separada por espaço.


  * ProTip ™: não se repita
    Se você não quiser repetir as variáveis frequentemente usadas no assunto, basta definir [defaults](https://jekyllrb.com/docs/configuration/#front-matter-defaults) para elas e substituí-las apenas quando necessário (ou não). Isso funciona tanto para variáveis predefinidas quanto personalizadas.

***
[back](./)