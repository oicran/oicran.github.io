---
layout: post
title: "Gerando uma nova chave SSH e adicionando ao ssh-agent"
date:   2019-02-11 12:48:00 -0200
categories: ssh_github
---

[Generating](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

Depois de verificar as chaves SSH existentes, você pode gerar uma nova chave SSH para usar na autenticação e adicioná-la ao ssh-agent.

Se você ainda não tiver uma chave SSH, deverá gerar uma nova chave SSH. Se você não tiver certeza se já possui uma chave SSH, verifique as chaves existentes.

Se você não quiser redigitar sua senha todas as vezes que usar sua chave SSH, poderá [adicionar sua chave ao agente SSH](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#adding-your-ssh-key-to-the-ssh-agent), que gerencia suas chaves SSH e lembra sua frase secreta.

### Gerando uma nova chave SSH

No terminal substitua o email pelo do seu usuário no Github.
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
Será criada uma nova chave SSH usando o email como rótulo

Quando perguntado sobre qual arquivo deseja salvar a chave, digite "enter". É aceito o destino padrão do arquivo.
`Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]
`
E digite uma senha segura para a chave SSH
```
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]
```

### Adicionando a chave SSH ao ssh-agent

Inicie o ssh-agent em background
```
eval "$(ssh-agent -s)"
Agent pid 59566
```
Adicione a sua chave privada ao ssh-agent. Se sua chave foi criada ou tem um nome diferente, substitua por `id_rsa` no comando abaixo.
`ssh-add ~/.ssh/id_rsa`

[Adicione a chave SSH a conta do Github](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account).

***
[back](./ssh_github.html)