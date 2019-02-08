--
layout: page
---

## [Adicionando uma nova chave SSH para a conta do Github](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account)

Para configurar a sua conta Github com sua nova (ou existente) chave SSH, também é necessário adicioná-la a conta do Github.

Depois de adicionar uma nova chave SSH à sua conta do GitHub, você pode reconfigurar quaisquer repositórios locais para usar o SSH. Para obter mais informações, consulte ["Alternando URLs remotos de HTTPS para SSH"](https://help.github.com/articles/changing-a-remote-s-url/#switching-remote-urls-from-https-to-ssh).

  * Nota: as chaves DSA foram descontinuadas no OpenSSH 7.0. Se o seu sistema operacional usar o OpenSSH, você precisará usar um tipo alternativo de chave ao configurar o SSH, como uma chave RSA. Por exemplo, se o seu sistema operacional for o MacOS Sierra, você poderá configurar o SSH usando uma chave RSA.

1 - Copie a chave SSH para o clipboard via terminal. Substitua o nome da chave no exemplo se necessário.
```bash
sudo apt-get install xclip
# Downloads and installs xclip. If you don't have `apt-get`, you might need to use another installer (like `yum`)
xclip -sel clip < ~/.ssh/id_rsa.pub
# Copies the contents of the id_rsa.pub file to your clipboard
```

    * Dica: Se o xclip não estiver funcionando, você pode localizar a pasta oculta do .ssh, abrir o arquivo no seu editor de texto favorito e copiá-lo para a área de transferência.


2 - Na sua página do Github, encontre __Settings__.
https://help.github.com/assets/images/help/settings/userbar-account-settings.png

3 - Em __SSH and GPG keys__.
https://help.github.com/assets/images/help/settings/settings-sidebar-ssh-keys.png

4 - Em __New SSH key or Add SSH key__.
https://help.github.com/assets/images/help/settings/ssh-add-ssh-key.png

5 - No camp "Title" adicione um rótulo descritivo para a sua chave, como "Aspire One".

6 - Cole a chave no campo "Key".
https://help.github.com/assets/images/help/settings/ssh-key-paste.png

7 - Então clique em __Add SSH key__.
https://help.github.com/assets/images/help/settings/ssh-add-key.png

8 - Se perguntado digite sua senha.
https://help.github.com/assets/images/help/settings/sudo_mode_popup.png

***
[back](./)
