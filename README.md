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

c010e55a608bcee817f969a02ab3d9cf4368696f4a2b954c6adebc4e0b70868a  pool/main/f/freetube/freetube_0.21.0_amd64.deb

eafbf46bf0b1768030d8fd83ac99a0c3b907e84bb3b60a9aae5a40f722895ebc  pool/main/f/freetube/freetube_0.21.0_arm64.deb

63bf303f5987716ee3a4c920466361acc5b8c28ec9648df99ae30fd544d65a09  pool/main/f/freetube/freetube_0.21.0_armhf.deb

# Copyright
O instalador do FreeTube (arquivos deb) são distribuidos sob a licença AGPLv3.