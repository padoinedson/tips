# Passos para entrega do trabalho






### 1o. instalar e configurar o git  

$ sudo apt install git  

$ git config --global user.name "padoinedson"  
> substitua `padoinedson` pelo seu `login` no github  

$ git config --global user.email "padoin.edson@gmail.com"  
> substitua `padoin.edson` pelo seu `email` no github  


### 2o. criar uma chave ssh com o seu login do github


$ sudo apt install ssh

$ ssh-keygen -t ed25519 -C "padoinedson@github.com"
> substitua `padoinedson` pelo seu `login` no github  

$ eval ` "$(ssh-agent -s)"  `

$ ssh -vT ` padoinedson@github.com `

$ ssh-add `~/.ssh/id_ed25519`

$ cat ` ~/.ssh/id_ed25519.pub `

> adicionar a chave púclica para o github em ` settings ` - `SSH and GPG keys `  
> copie ela para a sua conta  (não cole os espaços ou quebra de linha)




### 3o. acessar o email recebido do github e aceitar o convite para contribuir no repositório  




### 4o. clonar o projeto remoto com modo de acesso ssh

$ `git clone git@github.com:padoinedson/pp-trabalhos.git`

 


### 5o. fazer o trabalho salvando na pasta e entregar

$ cd pp-trabalhos  

> fazer o trabalho a salvar com nome `t1-seunome.c`

$ git pull

$ git add t1-seunome.c

$ git status

$ git commit -m "entregando t1 seunome"

$ git push 





 


> ## Dicas github
> Padoin, Edson Luiz  
> padoin@unijui.edu.br
