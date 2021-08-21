# Dicas de Github para Linux


<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTq65a7eURVcc8cpEB42M35mNIKilVo6ccW9XoAQampc2M4xRopPWGzA_ai8ho2YhyEgaQ&usqp=CAU">


Se você ainda não usou/instalou git visite: [Link](https://github.com/padoinedson/tips/blob/main/git.md)



## criar um repositório

acesse a sua conta no github.com e crie um repositório com nome teste
> use opção pública


## clonar um repositório remoto

$ git clone https://github.com/padoinunijui/teste.git









## **CONFIGURAÇÃO DO GITHUB**


## 1o. trocar o modo de acesso do servidor remoto (http -> ssh)

### listar servidor remoto

$ cd teste
$ git remote -v

> origin  https://github.com/padoinunijui/teste.git (fetch)  
> origin  https://github.com/padoinunijui/teste.git (push)  
> verifique que está como https  


## trocar o modo de acesso
$ git remote set-url origin ` git@github.com:padoinunijui/teste.git `


## verificar o modo de acesso
$ git remote -v

> origin  git@github.com:padoinunijui/teste.git (fetch)  
> origin  git@github.com:padoinunijui/teste.git (push)  
> agora está como ssh





## 2o. criar uma chave ssh com o seu login do github

$ sudo apt install ssh

$ ssh-keygen -t ed25519 -C "padoinunijui@github.com"

$ eval ` "$(ssh-agent -s)"  `

$ ssh -vT ` padoinunijui@github.com `

$ ssh-add `~/.ssh/id_ed25519`

$ cat ` ~/.ssh/id_ed25519.pub `

> adicionar a chave púclica para o github em ` settings ` - `SSH and GPG keys `  
> copie ela para a sua conta  (não cole os espaços ou quebra de linha)




## copiar as modificações do servidor para o repositório local

$ git pull






## adicionar um arquivo
 
$ echo "este arquivo sera adicionado ao github" > a.txt

$ git status

$ git add a.txt

$ git status

$ git commit -m "criado arquivo a.txt"



## copiar as modificações do repositório local para o servidor 

$ git push 













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
