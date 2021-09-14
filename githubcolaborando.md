# Dicas de Github para Linux

# colaborar com projeto de equipes



<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTq65a7eURVcc8cpEB42M35mNIKilVo6ccW9XoAQampc2M4xRopPWGzA_ai8ho2YhyEgaQ&usqp=CAU">


### 1o. instalar e configurar o git  

$ sudo apt install git  

$ git config --global user.name "padoinedson"  

$ git config --global user.email "padoin.edson@gmail.com"  




### 2o. acessar o email recebido do github e aceitar o convite para contribuir no repositório  




### 3o. clonar o projeto remoto da equipe

$ git clone https://github.com/padoinedson/pp-trabalhos.git



### 4o. trocar o modo de acesso do servidor remoto (http -> ssh)

$ cd pp-trabalhos  
 

$ git remote set-url origin ` git@github.com:padoinedson/pp-trabalhos.git `




### 5o. fazer o trabalho salvando na pasta e entregar

$ git pull

$ git add t1-seunome.c

$ git status

$ git commit -m "entregando t1 seunome"

$ git push 





 


> ## Dicas github
> Padoin, Edson Luiz  
> padoin@unijui.edu.br
