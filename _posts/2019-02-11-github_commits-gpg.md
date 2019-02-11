---
layout: post
title: "Commits usando GPG"
date:   2019-02-11 12:42:30 -0200
categories: gpg_github
---

[Commits using gpg](https://help.github.com/articles/signing-commits-using-gpg/)

Depois de configurar sua chave GPG e associá-la à sua conta do GitHub e ao Git, você pode assinar commits localmente. Seus commits serão mostrados como verificados em uma solicitação pull no GitHub.

  * Note: Github Desktop não suporta assinatura GPG.

  * Tips:
  Para configurar seu cliente Git para assinar commits por padrão para um repositório local, nas versões Git 2.0.0 e acima, execute `git config commit.gpgsign true`. Para assinar todos os commits por padrão em qualquer repositório local em seu computador, execute `git config --global commit.gpgsign true`.

  Para armazenar sua senha de chave GPG para que você não precise inseri-la toda vez que assinar um commit, recomendamos o uso das seguintes ferramentas:

  For Mac users, the GPG Suite allows you to store your GPG key passphrase in the Mac OS Keychain.
For Windows users, the Gpg4win integrates with other Windows tools.
You can also manually configure [gpg-agent](http://linux.die.net/man/1/gpg-agent) to save your GPG key passphrase, but this doesn't integrate with Mac OS Keychain like ssh-agent and requires more setup.

Se você tem várias chaves GPG ou está tentando assinar confirmações ou tags com uma chave GPG que não corresponde à sua identidade de committer, você deve informar ao Git sobre sua chave GPG.

1 - Ao cometer(committing) mudanças em sua ramificação local(local branch), adicione o sinalizador(flag) -S ao comando git commit:

```bash
git commit -S -m your commit message
# Creates a signed commit
```

2 - Depois de criar o commit insira a passphrase criada quando gerou a chave GPG.

3 - Quando terminar de criar os commits localmente, envie-os(push them) para o seu repositório remoto no GitHub:

```bash
git push
# Pushes your local commits to the remote repository
```

4 - No Github navegue até o seu pull request.

5 - Em pull request clique em [Commits](https://help.github.com/assets/images/help/pull_requests/pull-request-tabs-commits.png)

6 - Para ver informações mais detalhadas sobre a verificação das assinaturas clique em [Verified](https://help.github.com/assets/images/help/commits/gpg-signed-commit-verified-without-details.png).

***
[back](./)