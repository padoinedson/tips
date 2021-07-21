# Dicas de Git e Github para Linux

Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.
* [Link] (http://git-scm.com/)



## instalar o GIT

$ sudo apt install git


## criar um diretorio e entrar
 
$ mkdir projeto

$ cd projeto



## inicializar o git no diretorio

$ git init

$ ls -la


## configurar o git

$ git config --list

$ git config --global user.name "seu_nome"
$ git config --global user.email seu_nome@unijui.edu.br

$ git config --list



## criar um arquivo na pasta


$ echo "Brasil" > a.txt 

$ ls

$ cat a.txt


## adicionar arquivo no index

$ git add a.txt

$ git status


## commit dos arquivo(s) do index


$ git commit -a -m "primeiro commit"

		-a  			→ todos os arquivos alterados 
		-m 	"texto"  	→ adiciona uma mensagem

$ git status


## verificar log

$ git log




## modificar arquivo

$ echo "Argentina" >> a.txt 

$ cat a.txt

$ git status

$ git diff

$ git commit -a -m "segundo commit"

$ git status

$ git log