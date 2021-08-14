# Dicas de Git e Github para Linux



<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTq65a7eURVcc8cpEB42M35mNIKilVo6ccW9XoAQampc2M4xRopPWGzA_ai8ho2YhyEgaQ&usqp=CAU">


Se você ainda não usou/instalou git visite:
* [Link](https://github.com/padoinedson/tips/blob/main/git.md)




## clonar um projeto remoto

$ git clone https://github.com/padoinedson/tips.git




## listar servidor remoto

$ git remote -v




## copiar as modificações do servidor para o repositório local

$ git pull




## adicionar um arquivo
 
$ echo "este arquivo sera adicionado ao github" > a.txt

$ git status

$ git add a.txt

$ git status

$ git commit -m "criado arquivo a.txt"

$ git push -u origin main




## alterar o arquivo

 
$ echo "adicionamos mais uma linha ao arquivo" >> a.txt

$ git diff

$ git commit -am "alterado a.txt"

$ git push 

$ git statusg




## excluindo o arquivo


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









## criar uma chave com o seu login do github

$ ssh-keygen -t ed25519 -C "padoinedson@github.com"

$ eval ` "$(ssh-agent -s)"  `

$ ssh -vT ` padoinedson@github.com `

$ ssh-add `~/.ssh/id_ed25519`



## verificar o modo de acesso

$ git remote -v

> origin  https://github.com/padoinedson/lggc.git (fetch)
> origin  https://github.com/padoinedson/lggc.git (push)
> está como https


## trocar o modo de acesso
$ git remote set-url origin ` git@github.com:padoinedson/lggc.git `


## verificar o modo de acesso
$ git remote -v

> origin  git@github.com:padoinedson/lggc.git (fetch)
> origin  git@github.com:padoinedson/lggc.git (push)
> agora está como ssh



* [Link](https://docs.github.com/pt/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)


## adicionar ssh
* [Link](https://docs.github.com/pt/github/authenticating-to-github/connecting-to-github-with-ssh)



## trocar https por ssh
* [Link](https://docs.github.com/pt/github/getting-started-with-github/getting-started-with-git/managing-remote-repositories#switching-remote-urls-from-https-to-ssh)




## adicionar colaboradores
* [Link](https://docs.github.com/pt/github/setting-up-and-managing-your-github-user-account/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository)



### site 
* [Link](http://git-scm.com/)


> ## Dicas github
> Padoin, Edson Luiz  
> padoin@unijui.edu.br
