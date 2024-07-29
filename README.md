# Repositório APT Não-Oficial FreeTube

Repositório APT Não-Oficial do [FreeTube](https://github.com/FreeTubeApp/FreeTube).

Use este repositório para instalar e atualizar o pacote FreeTube com facilidade usando o APT.

Antes de confiar neste repositório, verifique a integridade dos arquivos e considere sua segurança primeiro. Crie seu próprio repositório APT usando este como base ou utilize o meu que buscará atualizações diariamente.

## Requisitos

* Debian/Ubunto ou qualquer distro derivado destes.

## Como instalar o repositório APT

Para que o APT identifique este repositório e seja capaz de instalar e atualizar o FreeTube você deve executar os códigos abaixo.

```shell
sudo apt remove freetube # Apenas se você instalou o FreeTube usando o arquivo deb. Neste caso, desinstale primeiro.
wget -qO- https://maeglithier.github.io/freetube-apt/pubkey.asc | sudo gpg --dearmor -o /usr/share/keyrings/freetube-archive-keyring.gpg
echo "deb [arch=amd64,arm64,armhf signed-by=/usr/share/keyrings/freetube-archive-keyring.gpg] https://maeglithier.github.io/freetube-apt stable main" | sudo tee /etc/apt/sources.list.d/freetube.list >/dev/null
sudo apt update
sudo apt install freetube -y # Agora você está pronto para instalar e atualizar sempre que uma nova versão lançar.
```

## Como faço para desinstalar este repositório?

Para remover este repositório e sua chave pública você deve executar os códigos abaixo.

```shell
sudo apt remove freetube # Apenas se você ainda não desinstalou o freetube. Neste caso, desinstale primeiro.
sudo rm /usr/share/keyrings/freetube-archive-keyring.gpg
sudo rm /etc/apt/sources.list.d/freetube.list
```

## Checksum

9bee4f73cebbd5c095ae9099981c1cab39378df7f2c471d6f5dc02f106b8ab91  pool/main/f/freetube/freetube_0.21.2_amd64.deb

177a3333206cbf2b03208176d733876f81c51f0b5cde3b86a519f9d5f9d0d600  pool/main/f/freetube/freetube_0.21.2_arm64.deb

47e23d500c5bc3371f1ef2a1dd57b216bca130040e62a9f40d2237251469dfc6  pool/main/f/freetube/freetube_0.21.2_armhf.deb

## Copyright

O instalador do FreeTube (arquivos deb) são distribuidos sob a licença AGPLv3.
