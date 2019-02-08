---
layout: page
title: Uso básico
---

[Basic Usage](https://jekyllrb.com/docs/usage/)

A gem Jekyll disponibiliza um executável `jekyll` para você na janela do Terminal. Você pode usar este comando de várias maneiras:

```bash
jekyll build
# => The current folder will be generated into ./_site

jekyll build --destination <destination>
# => The current folder will be generated into <destination>

jekyll build --source <source> --destination <destination>
# => The <source> folder will be generated into <destination>

jekyll build --watch
# => The current folder will be generated into ./_site,
#    watched for changes, and regenerated automatically.
```

### Substituir configurações de desenvolvimento padrão

O URL padrão é definido como `http://localhost:4000` no ambiente de desenvolvimento. 3.3.0

Se você deseja criar para o seu ambiente de produção:

Defina seu URL de produção em `_config.yml`, por exemplo `URL: https://example.com`.
Executar `JEKYLL_ENV = pacote de produção exec jekyll build`.

  * Alterações no `_config.yml` não são incluídas durante a regeneração automática.
    O arquivo de configuração principal `_config.yml` contém configurações globais e definições de variáveis que são lidas uma vez no tempo de execução. As alterações feitas no `_config.yml` durante a regeneração automática não são carregadas até a próxima execução.
    Note que [Data Files](https://jekyllrb.com/docs/datafiles) são incluídos e recarregados durante a regeneração automática.

        * Pastas de destino são limpas nas compilações do site
    O conteúdo de <destination> é automaticamente limpo, por padrão, quando o site é criado. Arquivos ou pastas que não são criados pelo seu site serão removidos. Os arquivos e pastas que você deseja reter em <destination> podem ser especificados na diretiva de configuração <keep_files>.
    Não use um local importante para <destination>; em vez disso, use-o como uma área de teste e copie os arquivos desse local para o servidor da web.


O Jekyll também vem com um servidor de desenvolvimento embutido que permitirá que você visualize como o site gerado ficará no seu navegador localmente.

```bash
jekyll serve
# => Um servidor de desenvolvimento será executado em http: // localhost: 4000 /
# Auto-regeneração: ativada. Use `--no-watch` para desativar.

jekyll serve --livereload
# LiveReload atualiza seu navegador após uma alteração.

jekyll serve --incremental
# Incremental realizará uma compilação parcial para reduzir o tempo de regeneração.

jekyll serve --detach
# => O mesmo que "jekyll serve", mas será desconectado do terminal atual.
# Se você precisar matar o servidor, você pode `kill -9 1234` onde" 1234 "é o PID.
# Se você não consegue encontrar o PID, então, `ps aux | grep jekyll` e mata a instância.
```

```bash
jekyll serve --no-watch
# => O mesmo que "jekyll serve", mas não assistirá a alterações.
```

Estas são apenas algumas das [opções de configuração](https://jekyllrb.com/docs/configuration/) disponíveis. Muitas opções de configuração podem ser especificadas como sinalizadores (flags) na linha de comando ou, como alternativa (e mais comum), podem ser especificadas em um arquivo `_config.yml` na raiz do diretório de origem. O Jekyll usará automaticamente as opções deste arquivo quando for executado. Por exemplo, se você colocar as seguintes linhas no arquivo `_config.yml`:

```bash
source:      _source
destination: _deploy
```

Então os dois comandos seguintes serão equivalentes:

```bash
jekyll build
jekyll build --source _source --destination _deploy
```

Para mais sobre possíveis opções de configuração veja as opções de configuração citadas acima.

  * Pedir ajuda
O comando de `help` está sempre aqui para lembrá-lo de todas as opções disponíveis e uso, e também trabalha com `build`, `serve` e `new` subcomandos, por exemplo, `jekyll help new` ou `jekyll help build`.

Se você estiver interessado em navegar por esses documentos on-the-go, instale o `jekyll-docs` gem e execute `jekyll docs` no seu terminal.

***
[back](./)