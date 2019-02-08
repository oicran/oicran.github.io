---
layout: page
title: Quick-Start Guide
---

[Quick-start guide](https://jekyllrb.com/docs/quickstart/)

Se você já tem um ambiente de desenvolvimento [Ruby](https://www.ruby-lang.org/en/downloads/) completo com todos os cabeçalhos e [RubyGems](https://rubygems.org/pages/download) instalados (veja os [requisitos](https://jekyllrb.com/docs/installation/#requirements) do Jekyll), você pode criar um novo site Jekyll fazendo o seguinte:

```shell
# Instale Jekyll e Bundler gems através do RubyGems
gem install jekyll bundler

# Criando um novo Jekyll site em ./myblog
jekyll new myblog

# Mude para o seu novo diretório
cd myblog

# Construa o site no servidor de visualização
bundle exec jekyll serve

# Agora navegue para http://localhost:4000
```

Se você encontrar algum erro inesperado durante o procedimento acima, consulte a página de [solução de problemas](https://jekyllrb.com/docs/troubleshooting/#configuration-problems) ou a página de requisitos já mencionada, pois pode estar faltando cabeçalhos de desenvolvimento ou outros pré-requisitos.

### Sobre Bundler

`gem install bundler` instala a gem do bundler através do RubyGems. Você só precisa instalá-lo uma vez - não toda vez que cria um novo projeto Jekyll. Aqui estão alguns detalhes adicionais:

`bundler` é uma gem que gerencia outras gems de Ruby. Ele garante que suas gems e versões gem sejam compatíveis e que você tenha todas as dependências necessárias que cada gem requer.

Os arquivos `Gemfile` e `Gemfile.lock` informam ao Bundler sobre os requisitos de gem em seu site. Se o seu site não tiver esses Gemfiles, você pode omitir o `bundle exec` e apenas executar o `jekyll serve`.

Quando você executa o `bundle exec jekyll serve`, o Bundler usa as gemas e as versões especificadas em `Gemfile.lock` para garantir que seu site Jekyll seja compilado sem conflitos de compatibilidade ou dependência.

Para obter mais informações sobre como usar o Bundler em seu projeto Jekyll, este [tutorial](https://jekyllrb.com/tutorials/using-jekyll-with-bundler/) deve fornecer respostas para as perguntas mais comuns e explicar como se preparar rapidamente.

### Opções para criar um novo site com o Jekyll

`jekyll new <PATH>` instala um novo site Jekyll no caminho especificado (relativo ao diretório atual). Neste caso, o Jekyll será instalado em um diretório chamado `myblog`. Aqui estão alguns detalhes adicionais:

  * Para instalar o site do Jekyll no diretório em que você está, execute `jekyll new .` Se o diretório existente não estiver vazio, você pode passar a opção `--force` com `jekyll new . --force`

  * O `jekyll new` inicia automaticamente `bundle install` para instalar as dependências necessárias. (Se você não quiser que o Bundler instale as gems, use `jekyll new myblog --skip-bundle`.)

  * Por padrão, o site Jekyll instalado pelo `jekyll new` usa um tema baseado em gem chamado [Minima](https://github.com/jekyll/minima). [Com temas baseados em gem](https://jekyllrb.com/docs/themes), alguns dos diretórios e arquivos são armazenados na gem do tema, escondidos de sua visão imediata.

  * Recomendamos configurar Jekyll com um tema baseado em gem, mas se você quiser começar com uma "lousa" em branco, use `jekyll new myblog --blank`

  * Para aprender sobre outros parâmetros que você pode incluir com `jekyll new`, digite `jekyll new --help`.

> Em caso de dúvida, use o comando `help` para lembrá-lo de todas as opções e uso disponíveis, ele também funciona com subcomandos `new`, `build` e `serve` por exemplo: `jekyll help new` ou `jekyll help build`.

### Próximos passos

_Construir um site Jekyll com o tema padrão é apenas o primeiro passo. A mágica real acontece quando você começa a criar postagens de blog, usando o assunto principal para controlar modelos e layouts, e aproveitando todas as opções impressionantes de configuração que o Jekyll disponibiliza._

***
[back](./)