---
layout: page
title: Assets
---

[Assets](https://jekyllrb.com/docs/assets/)

O Jekyll fornece suporte integrado para o Sass e pode trabalhar com o CoffeeScript por meio de gem. Ruby. Para usá-los, você deve primeiro criar um arquivo com o nome de extensão adequado (algo como, `.sass`, `.scss` ou `.coffee`) e __iniciar o arquivo com duas linhas de traços triplos__, como este:

```yaml
---
---

// start content
.my-definition
  font-size: 1.2em
```

O Jekyll trata esses arquivos da mesma forma que uma página normal, em que o arquivo de saída será colocado no mesmo diretório de onde veio. Por exemplo, se você tiver um arquivo chamado `css/styles.scss` na pasta de origem do seu site, o Jekyll o processará e o colocará na pasta de destino do seu site, em `css/styles.css.`

  * __Jekyll processa todos os filtros e tags Liquid em arquivos de ativos__
    Se você estiver usando o [Mustache](https://mustache.github.io/) ou outra linguagem de templates JavaScript que entre em conflito com a [sintaxe do modelo Liquid](https://jekyllrb.com/docs/templates/), você precisará colocar as tags `{% raw%}` e `{% endraw%}` em torno do seu código.

### [Sass/SCSS](https://jekyllrb.com/docs/assets/#sassscss)

O Jekyll permite que você personalize sua conversão Sass de determinadas maneiras.

Coloque todos seus partials em seu diretório `sass_dir`, que por padrão é `<source>/css`. Para exemplo, dê uma olhada nesse [site usando suporte Sass no Jekyll](https://github.com/jekyll/jekyll-sass-converter/tree/master/docs)

Se você está usando um `@import` Sass, precisa garantir que seu `sass_dir` está definido para o diretório base que contém seus arquivos Sass. Você pode fazer isso assim:

```yaml
sass:
    sass_dir: _sass
```

O Sass converte  por padrão as opções em `sass_dir` para `_sass`.

  * __O `sass_dir` só é usado pelo Sass__
    Note que o `sass_dir`torna-se o caminho de carregamento para as importações Sass, nada mais. Isso significa que Jekyll não sabe sobre esses arquivos diretamente, portanto, quaisquer arquivos aqui não devem conter o YAML Front Matter como descrito acima, nem serão transformados como descrito acima. Esta pasta deve conter apenas importações.

Você tamm pode especificar o estilo de  saída com a opção `style` no seu arquivo `_config.yml`:

```yaml
sass:
    style: compressed
```

Estes são passados para o Sass, portanto, quaisquer opções de estilo de saída que o Sass suporta também são válidas aqui.


### [Coffeescript](https://jekyllrb.com/docs/assets/#coffeescript)

Para ativar o Coffeescript no Jekyll 3.0 ou acima você deve:

* Instalar o `jekyll-coffeescript` gem

* Certifique-se de que seu `_config.yml` esteja atualizado e inclua o seguinte:

```yaml
pluguins:
 - jekyll-coffeescript
```

***
[back](./)