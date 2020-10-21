## Instalação do Docker no Ubuntu

Atualize seu Sistema Operacional;

#### sudo apt update

#### sudo apt upgrade

Instale pacotes de Pré-requisitos;

#### sudo apt-get install  curl apt-transport-https ca-certificates software-properties-common

Adicione os Repositórios do Docker;

Primeiro deve adicionar a chave GPG, inserindo o seguinte comando;

#### curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

Agora deve adicionar o repositório;

#### sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

Atualize as informações do repositório;

#### sudo apt update

Execute o seguinte comando para instalar o Docker;

#### sudo apt install docker-ce

Para verificar o status do docker execute o comando abaixo;

#### sudo systemctl status docker

Caso queira verificar a versão do docker que foi instalado, execute o comando;

#### docker –version


## Instalação do Zabbix em Docker

Para instalar o container zabbix em docker execute comando abaixo: 
Obs: nesse comando foi criado  a porta 80 para acesso do zabbix, a porta 10050 que é a porta do agent e criado um variavel para instalação do banco de dados mysql.

#### sudo docker container run --name zabbix-server -p 80:80 -p 10050:10050 -v /var/lib/mysql:/var/lib/mysql -d zabbix/zabbix-appliance

após instalação, informe o ip do servidor no navegador.
