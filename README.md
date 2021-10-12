# WSL2-Git-VsCode
Como configurar WSL2 + Git + VsCode
.
.
#
## Instalar Ubuntu no WSL2
#
# Abrir PoweShell como Administrador e mudar para o diretório onde está a imagem
# Os passos abaixo só servem para quem já fez download da imagem.

PS C:\Windows\system32> d:
PS D:\> cd .\ISOS\Others\
PS D:\ISOS\Others>
Add-AppxPackage .\Ubuntu_2004.2020.424.0_x64.appx

ou

Add-AppxPackage d:\ISOS\Others\Ubuntu_2004.2020.424.0_x64.appx

Após "instalar" na linha de comando, abrir a loja de APPs e finalizar a instalação.
Ou clicar em iniciar e procurar por Ubuntu e finalizar a instalação.

#
## Atualizar o Linux e instalar alguns pacotes
#
sudo apt update -y

sudo apt upgrade -y

sudo apt-get install git joe curl -y

sudo apt-get install gcc g++ -y

#
## Gerar chaves SSH >> no Linux <<
#
ssh-keygen -t rsa -b 4096 -C "usuario@dominio.com.br"

git config --global user.email "usuario@dominio.com.br"

git config --global user.name  "Nome Completo do Usuário"


#
## Instalar o Git for Windows e depois copiar a chave ssh gerada >> no Linux <<
#
cd ~
cd .ssh/
cp id_rsa* /mnt/c/Users/usuario/.ssh/.

#
## Dentro do bash >> do Git Bash <<
#
git config --global user.email "usuario@dominio.com.br"
git config --global user.name  "Nome Completo do Usuárioy"

#
## Cadastrar a chave ssh no site do GitHub
#

cat /home/usuario/.ssh/id_rsa.pub
e colocar o conteúdo acima em :
https://github.com/settings/keys


#
## Instalar o VsCode e fazer os ajustes finos
#

> Instalar pacote de idiomas e reiniciar o VsCode
> Fechar o Terminal do Linux e o VsCode antes do próximo passo
> Executar o VsCode de dentro do Linux com o comando # code .
> Aceitar "Você confia nos autores ...."
> Ajustar o Interpredador de comandos do Terminal e fechar o VsCode
> Instala a extensão WSL2 para o VsCode


> Para publicar o gitHub clicar no icone no canto inferior esquerdo

#
## Clonar os repositórios
#
git clone git@github.com:usuario/Reposutorio.git

-----------------------------------------
Sites que ajudaram a montar este projeto de tutorial :

#
## Como configurar as chaves SSH no Ubuntu 20.04
#
https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-20-04-pt

#
## Visual Studio Code, Remote-SSH, and SSH Keys (Windows/Mac/Linux)
#
https://youtu.be/py6Km38tJBc

#
## How To Use Git & Github with VS Code for Beginners - Create Repositories & SSH Key Setup
#
https://youtu.be/aMi4GXZVxSk

