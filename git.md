# Dicas de Git para Linux




<img src="https://git-scm.com/images/logo@2x.png">


# INSTALAÇÃO  
## instalar o pacote

$ sudo apt install `git`




# CONFIGURAÇÃO  
## adicionar usuário e email 

$ git config --list  
$ git config --global user.name "seu_nome_no_github"  
$ git config --global user.email "seu_email@no_github"  
$ git config --list



# UTILIZAÇÃO  


## criar um diretorio e entrar
 
$ mkdir projeto

$ cd projeto



## inicializar o git no diretorio

$ git init

$ ls -la



## criar um arquivo na pasta


$ echo "Brasil" > a.txt 

$ ls

$ cat a.txt


## adicionar arquivo no index

$ git add a.txt

$ git status


## fazer commit dos arquivo(s) do index


$ git commit -a -m "primeiro commit"



| Opção      | Descrição |
| ----------- | ----------- |
|  -a    | comitar todos os arquivos alterados       |
|  -m 	"texto"    | adicionar uma mensagem ao commit       |
 

$ git status




# HISTÓRICO

## verificar log

$ git log  
$ git log  -p "nome_do_arquivo"



### Atividade - modificar arquivo - adicionar texto ao final do arquivo

$ echo "Argentina" >> a.txt 

$ cat a.txt

$ git status

$ git diff

$ git commit -a -m "segundo commit"

$ git status

$ git log





# DESFAZER

## recuperar arquivo do último commit /descarar alterações locais

$ echo "Chile" >> a.txt 

$ cat a.txt

$ git status

$ git diff

$ git checkout -- a.txt

$ git diff

$ cat a.txt


## descartar mudanças de um arquivo local  

$ git restore "nome_do_arquivo" 


## desfazer/recuperar versão antiga   
 

$ git log

$ cat a.txt

$ git reset --hard <número>

$ cat a.txt


## remover arquivo do index  

$ git rm a.txt






## excluir o arquivo  


$  git rm a.txt 

$  git commit -am "excluindo arquivo a.txt"

$  git status 




# BRANCHES


## listar todos os branches  

$ git branch -av



## criar um branch  

$ git branch testing

$ git log
> exibe os dois branches(master, testing) --- o HEAD aponta para master  
> (HEAD -> master, testing)  




## alternar entre branches/mudar ramo

$ git checkout testing

$ git log
> exibe os dois branches(master, testing) --- o HEAD aponta para testing  
> (HEAD -> testing, master) 



$ echo "Equador" >> d.txt   

$ git add d.c  

$ git commit -m "adicionei d.c"  

> criacao do arquivo no branch testing




## voltar para o branch master

$ git checkout master  



# FUNDIR 


## merge de um branch no master

$ git checkout master  
> deve estar trabalhando no master

$ git merge testing





## ignorar arquivos no commit

criar um arquivo com nome `.gitignore` na pasta





* [Link](http://git-scm.com/)

* [Link downloads](https://git-scm.com/downloads)



> ## Dicas git  
> Padoin, Edson Luiz  
> padoin@unijui.edu.br

