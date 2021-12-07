# Dicas de Git para Linux




<img src="https://git-scm.com/images/logo@2x.png">


## instalar o GIT

$ sudo apt install `git`



## criar um diretorio e entrar
 
$ mkdir projeto

$ cd projeto



## inicializar o git no diretorio

$ git init

$ ls -la


## **CONFIGURAÇÃO DO GIT**

## 1o. adicionar user e email 

> $ git config --list  
> $ git config --global user.name "seu_nome_no_github"  
> $ git config --global user.email "seu_email@no_github"  
> $ git config --list



## criar um arquivo na pasta


$ echo "Brasil" > a.txt 

$ ls

$ cat a.txt


## adicionar arquivo no index

$ git add a.txt

$ git status


## fazer commit dos arquivo(s) do index


$ git commit -a -m "primeiro commit"

>		-a  			→ todos os arquivos alterados 
>		-m 	"texto"  	→ adiciona uma mensagem

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



## recuperar arquivo do último commit

$ echo "Chile" >> a.txt 

$ cat a.txt

$ git status

$ git diff

$ git checkout -- a.txt

$ git diff

$ cat a.txt



## recuperar versão antiga 
 

$ git log

$ cat a.txt

$ git reset --hard <numero>

$ cat a.txt





## remover arquivo do index

$ git rm a.txt






## excluir o arquivo


$  git rm a.txt 

$  git commit -am "excluindo arquivo a.txt"

$  git push 

$  git status 





## criar um branch


$ git checkout -b "teste-de-funcionlidade"

> ... criar arquivos e/ou editar arquivos  

$ git add d.c 

$ git commit -m "alterado d.c"

$ git push -u origin teste-de-funcionlidade




## trocar de branch

$ git checkout main

$ git checkout teste-de-funcionlidade




## merge

$ git checkout main  -> estar trabalhando no main

$ git merge teste-de-funcionlidade



## ignorar arquivos no commit

criar um arquivo com nome `.gitignore` na pasta




### Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

* [Link](http://git-scm.com/)

* [Link com os downloads](https://git-scm.com/downloads)


> ## Dicas git  
> Padoin, Edson Luiz  
> padoin@unijui.edu.br
