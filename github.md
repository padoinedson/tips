# Dicas de Git e Github para Linux




------------------------------------------------------------
## clonar um projeto remoto

$ git clone https://github.com/padoinedson/tips.git




------------------------------------------------------------
## list servidor remoto

$ git remote -v



------------------------------------------------------------
## copiar as modificações do servidor para o repositório local

$ git pull



------------------------------------------------------------
## adicionando arquivo
 
$ echo "#include" >> a.c

$ git add a.c 

$ git status

$ git commit -m "criado arquivo a.c"

$ git push -u origin main



------------------------------------------------------------
## alterando arquivos

 
$ echo "# pp2021" >> b.c

$ git diff

$ git add b.c 

$ git commit -m "alterado b.c"

$ git push -u origin main





------------------------------------------------------------
## criar um branch


$ git checkout -b "teste-de-funcionlidade"

cria arquivos
edita arquivos

$ git add d.c 

$ git commit -m "alterado d.c"

$ git push -u origin teste-de-funcionlidade


------------------------------------------------------------
## trocar de branch

$ git checkout main


$ git checkout teste-de-funcionlidade



------------------------------------------------------------
## merge


$ git checkout main  -> estar trabalhando no main

$ git merge teste-de-funcionlidade



### Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.
* [Link] (http://git-scm.com/)