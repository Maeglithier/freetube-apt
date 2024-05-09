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
5a848ff7a9e77a1d285954bf9821fe16021a13180fac852913602936592a7fe2  pool/main/f/freetube/freetube_0.20.0_amd64.deb  
25efcea433e0e6d0e1995746e01e2d1af0763bb69a4d8640f33d8680ad659afa  pool/main/f/freetube/freetube_0.20.0_arm64.deb  
f3f4f03b725a33b7b4712d1d0e1119262587cd6cb2ac634d1d2619e323eacd3d  pool/main/f/freetube/freetube_0.20.0_armhf.deb  

# Copyright
O instalador do FreeTube (arquivos deb) são distribuidos sob a licença AGPLv3.