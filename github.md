# Dicas de Github para Linux




Se você ainda não usou/instalou git favor visite: [Link](https://github.com/padoinedson/tips/blob/main/git.md)

# CRIAÇÃO DA CONTA 


> Acesse https://github.com/ e crie a sua conta





## clonar um repositório remoto com modo de acesso do servidor remoto http

$ git clone https://github.com/padoinedson/pp2022.git





# CONFIGURAÇÃO  

## 1o. trocar o modo de acesso do servidor remoto (http -> ssh)

### listar servidor remoto

$ cd sd2022  
$ git remote -v

> origin  https://github.com/padoinedson/pp2022.git (fetch)  
> origin  https://github.com/padoinedson/pp2022.git (push)  
> verifique que está como https  


### trocar o modo de acesso
$ git remote set-url origin `git@github.com:padoinedson/pp2022.git`


### verificar o modo de acesso
$ git remote -v

> origin  git@github.com:padoinedson/pp2022.git (fetch)  
> origin  git@github.com:padoinedson/pp2022.git (push)  
> agora está como ssh





## 2o. criar uma chave ssh com o seu login do github


$ sudo apt install ssh

> substitua `seu-login-no-git-hub` pelo seu `login` no github  

$ ssh-keygen -t ed25519 -C "seu-login-no-git-hub@github.com"

$ eval ` "$(ssh-agent -s)"  `

$ ssh -vT ` seu-login-no-git-hub@github.com `

$ ssh-add `~/.ssh/id_ed25519`

$ cat ` ~/.ssh/id_ed25519.pub `

> adicionar a chave púclica para o github em ` settings ` - `SSH and GPG keys `  
> copie ela para a sua conta  (não cole os espaços ou quebra de linha)



# UTILIZAÇÃO  


## copiar as modificações do servidor para o repositório local

$ git pull






## adicionar um arquivo
 
$ resolva o exercicio no arquivo `ex1-par-seunome.c` e salve dentro da pasta

$ git status

$ git add `ex1-par-seunome.c`.txt

$ git status

$ git commit -m "entregando exercicio 1"



## copiar as modificações do repositório local para o servidor `github`

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
