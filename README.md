# Repositório APT Não-Oficial FreeTube
Repositório APT Não-Oficial do [FreeTube](https://github.com/FreeTubeApp/FreeTube).

Use este repositório para instalar e atualizar o pacote FreeTube com facilidade usando o APT.

Antes de confiar neste repositório, verifique a integridade dos arquivos e considere sua segurança primeiro. Crie seu próprio repositório APT usando este como base ou utilize o meu que buscará atualizações diariamente.

# Requisitos

* Debian/Ubunto ou qualquer distro derivado destes.

# Como instalar o repositório APT
Para que o APT identifique este repositório e seja capaz de instalar e atualizar o FreeTube você deve executar os códigos abaixo.
```shell
sudo apt remove freetube # Apenas se você instalou o FreeTube usando o arquivo deb. Neste caso, desinstale primeiro.
wget -qO- https://maeglithier.github.io/freetube-apt/pubkey.asc | sudo gpg --dearmor -o /usr/share/keyrings/freetube-archive-keyring.gpg
echo "deb [arch=amd64,arm64,armhf signed-by=/usr/share/keyrings/freetube-archive-keyring.gpg] https://maeglithier.github.io/freetube-apt stable main" | sudo tee /etc/apt/sources.list.d/freetube.list >/dev/null
sudo apt update
sudo apt install freetube -y # Agora você está pronto para instalar e atualizar sempre que uma nova versão lançar.
```

# Como faço para desinstalar este repositório?
Para remover este repositório e sua chave pública você deve executar os códigos abaixo.
```shell
sudo apt remove freetube # Apenas se você ainda não desinstalou o freetube. Neste caso, desinstale primeiro.
sudo rm /usr/share/keyrings/freetube-archive-keyring.gpg
sudo rm /etc/apt/sources.list.d/freetube.list
```

# Checksum

ea2264b9458f9911e3a5000038a09a808b8e872e5df19a36201e319cf3ca3b53  pool/main/f/freetube/freetube_0.21.1_amd64.deb

e125219e9fa0d8da27de604bd666006640938792a102569ed0834d5b1bb5fc03  pool/main/f/freetube/freetube_0.21.1_arm64.deb

73c56020ad2634c39e0d0972bab54e6a6be76d5b9f8e0b483d7f156a2a6b3bb3  pool/main/f/freetube/freetube_0.21.1_armhf.deb

# Copyright
O instalador do FreeTube (arquivos deb) são distribuidos sob a licença AGPLv3.