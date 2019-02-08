---
layout: page
title: Buscando chaves existentes
---

## [Checking for exixting gpg keys](https://help.github.com/articles/checking-for-existing-gpg-keys/)

Antes de gerar podemos nos certificar da existência de de chaves GPG.


1- Abra o terminal

2- Use o comando `gpg --list-secret-keys --keyid-format LONG` para listar as chaves GPG para as quais você possua as chaves públicas e privadas. Uma chave privada é necessária para assinar commits e tags.

```bash
gpg --list-secret-keys --keyid-format LONG
```

  * Note: Some GPG installations on Linux may require you to use gpg2 --list-keys --keyid-format LONG to view a list of your existing keys instead. In this case you will also need to configure Git to use gpg2 by running git config --global gpg.program gpg2.

3- Check a saída do comando para ver se você tem alguma chave GPG.

***
[back](./)