---
layout: page
title: Gerando uma nova chave GPG
---

[Generating a new GPG key](https://help.github.com/articles/generating-a-new-gpg-key/)

  * Note: Antes de gerar uma nova chave GPG certifique-se de ter verificado seu endereço de email para poder assinar commits e tags.

`gpg --full-generate-key`

ou `gpg --gen-key`

e forneça os dados completos como tipo (rsa e rsa),tamanho (4096), nome, email, tempo de expiração e passphrase.

Para listar depois de concluído o processo de criação:

`gpg --list-secret-keys --keyid-format LONG`

A partir da lista escolha e copie o ID da chave GPG que quer usar. No exemplo o GPG key ID is `3AA5C34371567BD2`:

```ash
gpg --list-secret-keys --keyid-format LONG
/Users/hubot/.gnupg/secring.gpg
------------------------------------
sec   4096R/3AA5C34371567BD2 2016-03-10 [expires: 2017-03-10]
uid                          Hubot 
ssb   4096R/42B317FD4BA89E7A 2016-03-10
```

Cole o comando substituindo o ID key GPG.

```bash
gpg --armor --export 3AA5C34371567BD2
# Prints the GPG key ID, in ASCII armor format
```

Copie sua chave GPG, começando por `-----BEGIN PGP PUBLIC KEY BLOCK-----` è terminando com `-----END PGP PUBLIC KEY BLOCK-----`.

Adicione a GPG key no Github.

***
[back](./gpg_github.html)