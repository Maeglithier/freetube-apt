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

bf8649c7b384cd50178d6c887371472916bfdacb9971e939c35ddbe4ab3adc08  pool/main/f/freetube/freetube_0.21.3_amd64.deb

255eae1ad5603e718a50e6b08be1e33dfef63b6d2efc9dfe1141d56a87c3effc  pool/main/f/freetube/freetube_0.21.3_arm64.deb

1da3f8bc38098b541d36d394e5c5f189c7b5e7f9e32ee4a45c4715eeb2c25bad  pool/main/f/freetube/freetube_0.21.3_armhf.deb

## Copyright

O instalador do FreeTube (arquivos deb) são distribuidos sob a licença AGPLv3.
