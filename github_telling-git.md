---
layout: page
title: Adicionando a chave GPG a conta do Github
---

## [Telling git about your gpg key](https://help.github.com/articles/telling-git-about-your-gpg-key/)

Depois de configurar sua chave GPG e adicioná-la à sua conta do GitHub, você precisa informar ao Git que há uma chave GPG que você gostaria de usar.

Se você estiver usando uma chave GPG que corresponda à sua identidade de committer e ao seu endereço de e-mail confirmado associado à sua conta do GitHub, você poderá começar a assinar commits e assinar tags.

  * Se você não tiver uma chave GPG que corresponda à sua identidade de committer, será necessário associar um email a uma chave existente. Para mais informações, consulte ["Associando um email à sua chave GPG"](https://help.github.com/articles/associating-an-email-with-your-gpg-key).

Se você tem várias chaves GPG, você precisa dizer ao Git qual delas usar.

1 - Abra o Terminal.

2 - Use o comando `gpg --list-secret-keys --keyid-format LONG` para listar as chaves GPG para as quais você tem uma chave pública e privada. Uma chave privada é necessária para assinar commits ou tags.

```bash
gpg --list-secret-keys --keyid-format LONG

```

  * Note: Some GPG installations on Linux may require you to use `gpg2 --list-keys --keyid-format LONG` to view a list of your existing keys instead. In this case you will also need to configure Git to use gpg2 by running `git config --global gpg.program gpg2`.

3 -Na lista de chaves GPG, copie o ID da chave GPG que você gostaria de usar. Neste exemplo, o ID da chave GPG é `3AA5C34371567BD2`:

```bash
gpg --list-secret-keys --keyid-format LONG
/Users/hubot/.gnupg/secring.gpg
------------------------------------
sec   4096R/3AA5C34371567BD2 2016-03-10 [expires: 2017-03-10]
uid                          Hubot 
ssb   4096R/42B317FD4BA89E7A 2016-03-10
```

4 - Para definir sua chave de assinatura GPG no Git, cole o texto abaixo, substituindo o ID da chave GPG que você gostaria de usar. Neste exemplo, o ID da chave GPG é `3AA5C34371567BD2`:

`git config --global user.signingkey 3AA5C34371567BD2`

5 - Para adicionar sua chave GPG no seu bash profile, cole o texto abaixo:

```bash
test -r ~/.bash_profile && echo 'export GPG_TTY=$(tty)' >> ~/.bash_profile
echo 'export GPG_TTY=$(tty)' >> ~/.profile
```

  * Note: Se não tem o `.bash_profile`, esse comando adiciona a chave GPG ao `.profile`.

***
[back](./gpg_github.html)