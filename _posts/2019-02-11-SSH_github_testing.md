---
layout: post
title: "Testando sua conexão SSH"
date:   2019-02-11 12:49:30 -0200
categories: ssh_github
---

[Testing](https://help.github.com/articles/testing-your-ssh-connection)

Depois de ativada sua chave SSH e adicionada a sua conta do Github, pode agora testar sua conexão.
Antes de testar sua conexão você deve ter:

> [Conferido a exixtência de chaves SSH](https://help.github.com/articles/checking-for-existing-ssh-keys)
> [Gerado uma nova chave SSH](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
> [Adicionado uma nova chave para conta do Github](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account)

Quando testar a conexão será necessário autenticar com a senha criada da chave SSH criada anteriormente. Mais informações como [trabalhar com senhas de chaves SSH](https://help.github.com/articles/working-with-ssh-key-passphrases).

Entre com o seguinte comando no terminal:

```bash
ssh -T git@github.com
# Attempts to ssh to GitHub
```

Receberá um aviso como esse:

```bash
The authenticity of host 'github.com (IP ADDRESS)' can't be established.
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)?
```
ou esse:
```
The authenticity of host 'github.com (IP ADDRESS)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)?
```

Verifique se a impressão digital na mensagem que você vê corresponde a uma das mensagens na etapa 2 e, em seguida, digite sim:
```bash
Hi username! You've successfully authenticated, but GitHub does not
provide shell access.
```
Pode ocorrer essa mensagem de erro:
```
...
Agent admitted failure to sign using the key.
debug1: No more authentication methods to try.
Permission denied (publickey).
```
Esse é um conhecido problema com algumas distribuições Linux, [veja aqui](https://help.github.com/articles/error-agent-admitted-failure-to-sign).

Verifique se a mensagem contém o seu nome de usuário, se receber uma mensagem "permission denied", [veja aqui](https://help.github.com/articles/error-permission-denied-publickey).

***
[back](./ssh_github.html)