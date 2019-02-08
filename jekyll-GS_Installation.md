---
layout: page
title: Instalação
---

[Installation](https://jekyllrb.com/docs/installation/)

Jekyll é um [Ruby Gem](http://guides.rubygems.org/rubygems-basics/), e pode ser instalado na maioria dos sistemas.

### Requisitos

Antes de começar, verifique se seu sistema tem o seguinte:

Ruby versão 2.2.5 ou superior, incluindo todos os cabeçalhos de desenvolvimento (a instalação do ruby pode ser verificada executando `ruby -v`)
RubyGems (que você pode verificar executando `gem -v`)
GCC e Make (caso seu sistema não os tenha instalado, você pode verificar executando `gcc -v`, `g ++ -v` e `make -v` na interface de linha de comando do seu sistema)

### [Instalação Ubuntu Linux](https://jekyllrb.com/docs/installation/#ubuntu)

Antes de instalarmos o Jekyll, precisamos ter certeza de que temos todas as dependências necessárias.

`sudo apt-get install ruby ruby-dev build-essential`

__É melhor evitar instalar o Ruby Gems como usuário root__. Portanto, precisamos configurar um diretório de instalação gem para sua conta de usuário. Os comandos a seguir adicionarão variáveis de ambiente ao seu arquivo `~ / .bashrc` para configurar o caminho da instalação gem. Corra agora:

```
 echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
 echo 'export GEM_HOME=$HOME/gems' >> ~/.bashrc
 echo 'export PATH=$HOME/gems/bin:$PATH' >> ~/.bashrc
 source ~/.bashrc
```

Finalmente instalar o jekyll:

`gem install jekyll bundler`

É isso aí! Você está pronto para começar a usar o jekyll!

### Atualizar o jekyll

Antes de começar o desenvolvimento com jekyll talvez você queira confirmar se esta atualizado com a última versão. Para encontrar a instalada atualmente corra um desses comandos:

`jekyll --version`
`gem list jekyll`

Também pode usar RubyGems para encontar a [versão corrente do jekyll](https://rubygems.org/gems/jekyll). Outro caminho para se certificar se você tem a última versão é roda o comando `gem outdated`. Isso vai mostrar uma lista de todas gems no seu sistema que precisam ser atualizadas. Se não estiver rodando a última versão, corra esse comando:

`bundle update jekyll`

Se não tiver o Bundler instalado corra:

`gem update jekyll`

Para atualizar para a última Rubygems, corra:

`gem update --system`

Consulte nossa seção de atualização para atualizar do Jekyll 2.x ou 1.x.


### Pré-release

Para instalar um pré-release, verifique se você tem todos os requisitos instalados corretamente e execute:

`gem install jekyll --pre`

Isso vai instalar o ultimo pré-release. Se quiser um em particular, use `-v` indicar a versão que quer instalar:

`gem install jekyll -v '2.0.0.alpha.1'`

Se você deseja instalar uma versão de desenvolvimento do Jekyll, o processo é um pouco mais complicado. Isso lhe dá a vantagem de ter o mais recente e melhor, mas pode ser instável.

`git clone git://github.com/jekyll/jekyll.git
cd jekyll
script/bootstrap
bundle exec rake build
ls pkg/*.gem | head -n 1 | xargs gem install -l`

Agora com tudo atualizado e instalado, mãos à obra!

***
[back](./)