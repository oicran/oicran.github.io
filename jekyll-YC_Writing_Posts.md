---
layout: page
title: Escrevendo Posts
---

[Writing posts](https://jekyllrb.com/docs/posts/)

Um dos melhores aspectos de Jekyll é que ele é "conhecimento do blog". O que isso significa, exatamente? Bem, simplesmente, isso significa que o blog é incorporado à funcionalidade do Jekyll. Se você escrever artigos e publicá-los on-line, poderá publicar e manter um blog simplesmente gerenciando uma pasta de arquivos de texto em seu computador. Em comparação com o incômodo de configurar e manter bancos de dados e sistemas CMS baseados na web, essa será uma mudança bem-vinda!

### A Pasta de Postagens

Conforme explicado na página de estrutura de diretórios, a pasta `_posts` é onde seus posts de blog vão residir. Esses arquivos geralmente são Markdown ou HTML, mas podem ser outros formatos com o conversor adequado instalado. Todas as postagens devem ter o [YAML Front Matter](https://jekyllrb.com/docs/frontmatter/), e elas serão convertidas do formato de origem para uma página HTML que faça parte do site estático.

#### Criando Arquivos de Postagens

Para criar uma nova postagem, tudo o que você precisa fazer é criar um arquivo no diretório `_posts`. Como você nomeia arquivos nesta pasta é importante. O Jekyll requer que os arquivos de postagem do blog sejam nomeados de acordo com o seguinte formato:

`YEAR-MONTH-DAY-title.MARKUP`

Onde `YEAR` é um número de quatro dígitos, `MONTH` e `DAY` são ambos números de dois dígitos e `MARKUP` é a extensão de arquivo que representa o formato usado no arquivo. Por exemplo, os seguintes são exemplos de nomes de arquivos de postagem válidos:

`2011-12-31-new-years-eve-is-awesome.md`
`2012-09-12-how-to-write-a-blog.md`

* *ProTip ™: Link para outros posts*
*Use a tag [`post_url`](https://jekyllrb.com/docs/templates/#linking-to-posts) para vincular a outras postagens sem ter que se preocupar com a quebra de URLs quando o estilo permalink do site for alterado.*

#### Formatos de Conteúdo

Todos os arquivos de postagem do blog devem começar com o [YAML Front Matter](https://jekyllrb.com/docs/frontmatter/). Depois disso, é simplesmente uma questão de decidir qual formato você prefere. Jekyll suporta [Markdown](https://daringfireball.net/projects/markdown/) fora da caixa, e tem [inúmeras extensões para outros formatos](https://jekyllrb.com/docs/plugins/#converters-1) também, incluindo o popular formato Textile. Cada um desses formatos tem sua própria maneira de marcar diferentes tipos de conteúdo em uma postagem, portanto, você deve se familiarizar com esses formatos e decidir qual deles melhor atende às suas necessidades.

* *Esteja ciente dos conjuntos de caracteres*
*Os processadores de conteúdo podem modificar certos caracteres para torná-los mais bonitos. Por exemplo, o `smart` A extensão em Redcarpet converte caracteres de cotação ASCII padrão em encaracolados, Unicode. Para que o navegador exiba esses caracteres adequadamente, defina o valor meta do conjunto de caracteres incluindo `<meta charset="utf-8">` no  `<head>` do seu layout.*

### Incluindo Imagens e Recursos

É provável que, em algum momento, você deseje incluir imagens, downloads ou outros ativos digitais junto com seu conteúdo de texto. Embora a sintaxe de vinculação a esses recursos seja diferente entre Markdown e Textile, o problema de descobrir onde armazenar esses arquivos em seu site é algo que todos enfrentarão.

Há várias maneiras de incluir recursos digitais no Jekyll. Uma solução comum é criar uma pasta na raiz do diretório do projeto chamada algo como `assets`, na qual quaisquer imagens, arquivos ou outros recursos são colocados. Em seguida, a partir de qualquer postagem, eles podem ser vinculados ao uso da raiz do site como o caminho para o recurso incluir. Novamente, isso dependerá da configuração do (sub) domínio e do caminho do seu site, mas aqui estão alguns exemplos no Markdown de como você pode fazer isso usando o filtro `absolute_url` em uma postagem.

Incluindo um recurso de imagem em uma postagem:

```markdown
... which is shown in the screenshot below:
![My helpful screenshot]({{ "/assets/screenshot.jpg" | absolute_url }})
```

Vinculando a um PDF para os leitores baixarem:

```markdown
... you can [get the PDF]({{ "/assets/mydoc.pdf" | absolute_url }}) directly.
```

### Uma Postagem Típica

O Jekyll pode lidar com muitas iterações diferentes da ideia que você pode associar a uma “postagem”, no entanto, uma postagem padrão no estilo do blog, incluindo Título, Layout, Data de Publicação e Categorias, pode ter esta aparência:

```markdown
---
layout: post
title:  "Welcome to Jekyll!"
date:   2015-11-17 16:16:01 -0600
categories: jekyll update
---

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `bundle exec jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

```

Tudo entre o primeiro e o segundo `---` são parte do YAML Front Matter, e tudo após o segundo `---` será processado com Markdown e exibido como "Conteúdo".

### Exibindo um Índice de Postagens

É muito bom ter postagens em uma pasta, mas um blog não é útil, a menos que você tenha uma lista de postagens em algum lugar. Criar um índice de postagens em outra página (ou em um [template](https://jekyllrb.com/docs/templates/) "modelo") é fácil, graças à [linguagem de modelo Liquid](https://docs.shopify.com/themes/liquid/basics) e suas tags. Veja um exemplo básico de como criar uma lista de links para suas postagens no blog:

```html
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
```

Naturalmente, você tem controle total sobre como (e onde) exibe suas postagens e como estrutura seu site. Você deve ler mais sobre [como os modelos funcionam](https://jekyllrb.com/docs/templates/) com o Jekyll se você quiser saber mais.

Note que a variável `post` existe apenas dentro do loop `for` acima. Se você deseja acessar as variáveis da page/post's atualmente renderizadas (as variáveis da post/page que contém o loop `for`), use a variável de `page`.

### Exibindo Categorias ou Tags de Postagem

Ei, isso é muito legal, mas e mostrar algumas das suas postagens relacionadas entre si? Para isso você pode usar qualquer uma das variáveis definidas no Front Matter. Na seção "postagem típica", você pode ver como definir categorias. Basta adicionar as categorias ao seu Front Matter como uma [lista yaml](https://en.wikipedia.org/wiki/YAML#Basic_components).

Agora que suas postagens têm uma categoria ou várias categorias, você pode criar uma página ou um modelo exibindo apenas as postagens dessas categorias que você especificar. Veja um exemplo básico de como criar uma lista de postagens de uma categoria específica.

Primeiro, no diretório `_layouts`, crie um novo arquivo chamado `category.html` - nesse arquivo, coloque (pelo menos) o seguinte:

```html
---
layout: page
---

{% for post in site.categories[page.category] %}
    <a href="{{ post.url | absolute_url }}">
      {{ post.title }}
    </a>
{% endfor %}
```

Em seguida, no diretório raiz de sua instalação do Jekyll, crie um novo diretório chamado `category` e, em seguida, crie um arquivo para cada categoria que você deseja listar. Por exemplo, se você tiver um `blog` de categoria, crie um arquivo no novo diretório chamado `blog.html` com pelo menos

```yaml
---
layout: category
title: Blog
category: blog
---
```

Nesse caso, as páginas de listagem estarão acessíveis em

`{baseurl} /category/blog.html`

Embora as categorias e as tags sejam muito semelhantes, elas são usadas para agrupar postagens, há algumas diferenças entre elas. As categorias e subcategorias criam hierarquias que, por padrão, são refletidas na estrutura de diretórios do seu site. Uma postagem com o seguinte cabeçalho

```yaml
---
layout: post
title: A Trip
category: [ blog, travel ]
---
```

estará acessível em 

`{baseurl} /blog/travel/year/month/day/A-Trip.html`.

Por outro lado, um post marcado

```html
---
layout: post
title: A Trip
tags: [ blog, travel ]
---
```

será salvo como `{baseurl}/year/month/day/A-Trip.html`. Cabe a você criar `{baseurl}/tag/blog.html` e`{baseurl}/tag/travel.html` da mesma maneira descrita acima para categorias.

Enquanto este exemplo é feito com tags e categorias, você pode facilmente estender suas listas para filtrar por qualquer outra variável criada com extensões.

### Postar Trechos

Cada postagem recebe automaticamente o primeiro bloco de texto, desde o início do conteúdo até a primeira ocorrência de `excerpt_separator`, e o define no hash de dados da postagem. Tome o exemplo acima de um índice de posts. Talvez você queira incluir uma pequena dica sobre o conteúdo da postagem, adicionando o primeiro parágrafo de cada uma de suas postagens:

```html
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
```

Como o Jekyll pega o primeiro parágrafo, você não precisará incluir o trecho nas tags `p`, o que já é feito para você. Essas tags podem ser removidas com as seguintes opções, se você preferir:

```html
{{ post.excerpt | remove: '<p>' | remove: '</p>' }}
```

Se você não gostar do trecho de postagem gerado automaticamente, ele poderá ser explicitamente substituído ao adicionar um valor de `excerpt`"trecho" à YAML Front Matter da sua postagem. Como alternativa, você pode optar por definir um `excerpt_separator` personalizado na matéria principal do YAML da postagem:

```yaml
---
excerpt_separator: <!--more-->
---

Excerpt
<!--more-->
Out-of-excerpt
```

Você também pode definir o `excerpt_separator` globalmente em seu arquivo de configuração `_config.yml`.

Desative completamente os trechos configurando seu `excerpt_separator` para `""`.

Além disso, como acontece com qualquer saída gerada pelas tags Liquid, você pode passar `| strip_html` filter para remover quaisquer tags html na saída. Isso é particularmente útil se você deseja enviar um trecho de postagem como uma tag `meta = "description"` no `head` do post, ou em qualquer outro lugar que tenha tags html junto com o conteúdo não é desejável.

### Destacar Trechos de Código

Jekyll também tem suporte embutido para realce de sintaxe de trechos de código usando Pygments ou Rouge, e é fácil incluir um trecho de código em qualquer post. Basta usar a tag Liquid dedicada da seguinte forma:

```yaml
{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}
```

E a saída ficará assim:

```yaml
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
```

* ProTip ™: Mostrar números de linha
Você pode fazer trechos de código com números de linha adicionando a palavra `linenos` ao final da tag de abertura como esta: `{% highlight ruby linenos%}`.

Esses princípios básicos devem ser suficientes para você começar a escrever seus primeiros posts. Quando você estiver pronto para descobrir o que mais é possível, talvez esteja interessado em fazer coisas como [personalizar permalinks de postagens](https://jekyllrb.com/docs/permalinks/) ou usar [variáveis personalizadas](https://jekyllrb.com/docs/variables/) em suas postagens e em outros lugares em seu site.

***
[back](./)