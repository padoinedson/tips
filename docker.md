# Dicas de Docker para Linux



## Atividade 1 ---- INSTALAÇÃO 


Opções:  


> 1--> Shell - arquivo baixado na pasta  

	$ sudo sh Install-Docker-on-Linux-Mint.sh  


> 2--> Oficial docker   

	https://docs.docker.com/install/linux/docker-ce/ubuntu/  


> 3--> Linux Mint 19:  

	https://gist.github.com/sirkkalap/e87cd580a47b180a7d32  


> 4--> Linux Mint 18:  

	https://gist.github.com/andrewelkins/1adc587feb610f586f8f40b50b7efc3a#file-install-docker-on-linux-mint-18-sh  


> 5--> Ubuntu de 64 Bits, versão 13.04:  

	https://www.digitalocean.com/community/tutorials/como-instalar-e-utilizar-o-docker-primeiros-passos-pt  


> 6--> Direto do shell  

	$ wget -qO- https://get.docker.com  






### Adicionar usuário ao grupo docker para evitar sudo

		$ sudo usermod -a -G docker <<seu-user-name>>




 
### Verificar se o docker está rodando

	ps -fax  
	top  
	$ ps -ef | grep docker  
	ou  
	$ pgrep docker  
	ou  
	$ sudo systemctl status docker  
			q (quit) para sair  


### Start o docker

		$ sudo systemctl start docker


### Info do docker

		$ docker info




### Testar o docker
 
	$ docker run hello-world


>				To try something more ambitious, you can run an Ubuntu container with:  
>				$ docker run -it ubuntu bash   

> 				Share images, automate workflows, and more with a free Docker ID:  
> 				https://hub.docker.com/  

>				For more examples and ideas, visit:  
>				https://docs.docker.com/get-started/  





## Atividade 2 ---- GERENCIAR IMAGENS PRONTAS  



###		Exibir imagens locais   

			$ sudo docker images  


###		Procurar por imagens prontas   

			sudo docker search `nome_da_imagem`

>			$ sudo docker search ubuntu  
>			$ sudo docker search mysql  
>			$ sudo docker search mongo  


>			https://hub.docker.com/search/?type=image  



###  Baixar/instalar uma imagem prontas

		 			$ sudo docker pull `nome_da_imagem`  
			
> 			$ sudo docker pull ubuntu



###		Excluir imagem

			$ docker rmi `IMAGE_ID` 






## Atividade 3 ---- GERENCIAR CONTAINERS
 


###		Exibir containers  

			$ sudo docker ps       <----- lista os ativos   

			$ sudo docker ps -a    <----- lista todos   


###		Criar um container inativo


			$ sudo docker run php  
			ou  
			$ sudo docker run --name padoin3 ubuntu    <---- com nome  

			$ sudo docker ps -a  


###		Criar e Executar um container 


			$ sudo docker run -i -t ubuntu /bin/bash  
			ou  
			$ sudo docker run -it ubuntu /bin/bash  
			ou  
			$sudo docker run -it --name padoin4 ubuntu   /bin/bash  

>							opções:  
>								-i permite interagir com o container    
>								-t associa o seu terminal ao terminal do container  
>								-it é apenas uma forma reduzida de escrever -i -t  
>								--name algum-nome permite atribuir um nome ao container em execução  
>								-p 8080:80 mapeia a porta 80 do container para a porta 8080 do host  
>								-d executa o container em background  
>								-v /pasta/host:/pasta/container cria um volume '/pasta/container' dentro do container com o conteúdo da pasta '/pasta/host' do host  

>								--detach , -d		Detached mode: run command in the background  
>								--detach-keys		Override the key sequence for detaching a container  
>								--env , -e			API 1.25+ Set environment variables  
>								--interactive , -i	Keep STDIN open even if not attached  
>								--privileged		Give extended privileges to the command  
>								--tty , -t			Allocate a pseudo-TTY  
>								--user , -u			Username or UID (format: <name|uid>[:<group|gid>])  


###		Sair de um container em execução

			$ exit



###		Ativar um container 

			$ sudo docker start CONTAINER ID




###		Stop um container ativo

			$ sudo docker stop CONTAINER ID




###		Excluir  containers

			$ sudo docker rm CONTAINER ID  

			$ sudo docker rm --force CONTAINER ID  
  



## Atividade 4 ---- GERENCIAR CONTAINERS




###		Criar um container ativo em backgroud

			$ sudo docker run -it -d --name padoin5 ubuntu   /bin/bash  
	
			$ sudo docker ps -a  



###		Ver status dos containers ativos

			$ sudo docker status 


###		Entrar em um container ativo e em backgroud  

			$ sudo docker attach CONTAINER_ID  


### 		Sair de um container em execução  

			$ exit  





## Atividade 5 ---- TRABALHAR COM CONTAINERS



  $  sudo docker run -it --name padoin44 ubuntu   /bin/bash  
  	 exit <----- dentro do container  

  $  sudo docker ps -a  
  $  sudo docker start padoin44  
  $  sudo docker ps -a  
  $  sudo docker attach padoin44   
  	 mkdir atividadeSD <----- dentro do container  
  	 exit <----- dentro do container  
 
  $  sudo docker start padoin44  
  $  sudo docker attach padoin44  
  	 exit <----- dentro do container  







## Atividade 6 ---- CRIAR SUAS IMAGENS 




###		Criar um arquivo Dockerfile

>			dica: 	somente um Dockerfile por diretorio  

conteúdo do arquivo:

>				FROM    # deve ser a primeira instrução - de qual imagem base vou criar a minha
>				RUN  	# comando que vai ser rodado na instalação
>				ENV     #
>				CMD     # deve ser a última instrução - qual comando vai ser executado qdo o container for levantado


Exemplo Dockerfile com serviço de rede:

>					FROM ubuntu
>					MAINTAINER padoin
>					RUN apt-get -y update
>					RUN apt-get -y install net-tools
>					RUN apt-get -y install iputils-ping



###		Criar a imagem com o arquivo Dockerfile 
	
>			$ sudo docker build -t <nome_da_minha_imagem:versao> <local a ser criado ponto "." é no local atual >

			$ sudo docker build -t ubuntu:2903 -f Dockerfile .



###		Exibir imagens locais  

			$ sudo docker images  




###		Executar um container a partir de uma imagem criada  

			$ sudo docker run -it ubuntu:2903 /bin/bash  



###		Sair de um container ativo  

			$ exit  





## Atividade 7 ----  USAR UM CONTAINER CRIADO




###		Executar um container a partir de uma imagem criada

			$ sudo docker run -it ubuntu:2903 /bin/bash


			$ ifconfig   <----------------- no container 


####		Sair de um container e deixá-lo ativo

			$ CTRL + P CTRL + Q   

		$ ping 172.17.0.3    <----------------- fora do  container   

		$ docker ps   

		$ docker stop CONTAINER_ID  





## Atividade 8 ---- USAR CONTAINER CRIADO
 

###		Executar um container a partir de uma imagem criada

			$ sudo docker run -it ubuntu:2903 /bin/bash



###		Sair do container e deixá-lo ativo
 
			$ CTRL + P CTRL + Q    



### 	Executar um comando em um container ativo


			$ sudo docker ps -a  

			$ sudo docker exec -i -t CONTAINER_ID ls  
		 	$ sudo docker exec CONTAINER_ID mkdir /sd2022/  
			$ sudo docker exec -i -t CONTAINER_ID ls  

			$ sudo docker exec -i -t CONTAINER_ID ifconfig  	
			$ ping 172.17.0.3   
			$ CTRL + C para cancelar o ping   




###	Entrar em um container ativo e em backgroud

			$ sudo docker attach CONTAINER_ID  

			ls <----- para verificar se foi criado  


###		Sair de um container ativo

			$ exit




## Atividade 9 ---- CONTAINERS com usuários


### Container com usuários


#### 1 criar uma imagem com usuário

>	criar uma pasta com seu nome

	$ mkdir padoinativ9 

> 	entrar na pasta criada

	$ cd padoinativ9

>	criar um arquivo Dockefile com o seguinte conteudo

			FROM ubuntu  
			MAINTAINER padoin  
			RUN mkdir -p /test  
			RUN useradd appuser   
			RUN usermod -a -G sudo appuser  
			USER appuser  


> 	criar uma imagem  

	$ sudo docker build -t ubuntu:5 -f Dockerfile .


#### 2 criar um container com a imagem e executar com o usuário

	$ sudo docker run -i -t -u appuser  ubuntu:5 /bin/bash





## Atividade 10 ---- CONTAINERS com pastas compartilhadas


 
> 	criar uma pasta com seu nome
	
	$ mkdir meudir
	

> 	criar um container conectando a pasta no home com a pasta do container

	$ sudo docker run -v /home/sd2022/meudir:/test -i -t ubuntu /bin/bash


>			dica:  
>			- diretorio_do_home:diretorio_do_container  
>			- a pasta test será criada dentro do container  





## Atividade 11 ---- FUNÇÕES AVANÇADAS 



###		Salvando (committing) um container

			$ sudo docker commit 0812726e17d0  ubuntu:2




>			dica:  
>			- será criado uma nova imagem com nome ubuntu:2 






## Atividade 12 ---- FUNÇÕES AVANÇADAS 



#### Parar docker

	$ pgrep docker


	$ sudo systemctl stop docker  
	ou  
	$ sudo /etc/init.d/docker stop  







## Atividade 13 ---- FUNÇÕES AVANÇADAS 



	docker build ...  
	docker push ...  

 




### local imagens e containers


	$ sudo ls  /var/lib/docker/containers -l  
 
	$ sudo ls  /var/lib/docker/image -l  





### Ref

https://docs.docker.com/

https://docs.docker.com/engine/reference/commandline/image_ls/





200.132.195.199
200.132.195.2
200.132.194.204
200.132.195.12


scp Install-Docker-on-Linux-Mint.sh sd2022@200.132.195.199:/home/sd2022

scp sd2022@200.132.195.199:/home/sd2022/nome.c .




## Atividade 14 ---- docker com nginx



> rodar 
	$ docker run nginx

> com nome
	$ docker run --name nginx nginx

> com porta

	$ docker run --name nginx -p 8080:80 nginx

> 			para testar - browser localhost:8080
> 									- em outro terminal $ lynx localhost:8080

> completo

	$ docker run --rm --name nginx -p 8080:80 nginx


docker exec -it nginx bash 

	cd /usr/share/nginx/html/  
	apt update  
	apt install vim  
	vi index.html  
		altera o arquivo   
			para testar - em outro terminal $ lynx localhost:8080  


> com volume ----compartilhando a pasta


	$ mkdir www

	$ docker run --rm --name nginx -p 8080:80 -v ~/www:/usr/share/nginx/html nginx

	cd www  
	vi index.html  
> 							<!DOCTYPE html>
>							<html>
>							<head>
>							<title>testando!</title>
>							</head>
>							<body>
>							<h1>testando!</h1>
>							</body>
>							</html>

>	para testar - em outro terminal $ lynx localhost:8080



#### criar uma imagem 

	$ vi Dockerfile

>					FROM nginx 
>					RUN apt update && apt install -y vim  
>					COPY www/index.html /usr/share/nginx/html  


#### criar um container com a minha imagem 

	$ docker pull nginx  

	$ docker build -t nginxpadoin:latest .   


#### rodar o container

	$ docker run --rm --name nginx -p 8080:80  nginxpadoin:latest  







## Atividade 15 ---- docker com servidor go



#### criar uma imagem  


	$ vi Dockerfile

>		FROM golang:1.17  
>		WORKDIR /go/src  
>		COPY main.go .  
>		RUN go build -o server main.go  
>		CMD ["./server"]  

 
 

	$ vi main.go


>				package main  

>				import (  
>				    "log"  
>				    "net/http"  
>				)  

>				func main() {  
>				    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {  
>				        w.Write([]byte("<h1>Welcome</h1>"))  
>				    })  
>				    log.Fatal(http.ListenAndServe(":8080", nil))  
>				}  



	$ sudo docker build -t gopadoin . 


	$ docker run --rm --name nginx -p 8080:80  gopadoin


> 			para testar - browser localhost:8080  
> 									- em outro terminal $ lynx localhost:8080




