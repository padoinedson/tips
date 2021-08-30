# Dicas de Github para Linux

# colaborar com projeto de equipes



<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTq65a7eURVcc8cpEB42M35mNIKilVo6ccW9XoAQampc2M4xRopPWGzA_ai8ho2YhyEgaQ&usqp=CAU">


## acessar o email recebido do github e aceitar o convite para participar da equipe



## clonar o projeto remoto da equipe

$ git clone https://github.com/padoinedson/exercicio1.git





## **CONFIGURAÇÃO DO GITHUB**


## 1o. trocar o modo de acesso do servidor remoto (http -> ssh)

$ cd exercicio1  
$ git remote -v

> origin  https://github.com/padoinedson/exercicio1.git (fetch)  
> origin  https://github.com/padoinedson/exercicio1.git (push)  
> verifique que está com acesso https  


## trocar o modo de acesso
$ git remote set-url origin ` git@github.com:padoinedson/exercicio1.git `


## verificar o modo de acesso
$ git remote -v
> verifique que está com acesso ssh  



## copiar as modificações do servidor para o repositório local

$ git pull




## adicionar um arquivo
 
$ echo "este arquivo sera adicionado ao github" > seunome.txt

$ git status

$ git add seunome.txt

$ git status

$ git commit -m "criado arquivo seunome.txt"

$ git push 




## alterar o arquivo

 
$ echo "adicionamos mais uma linha ao arquivo" >> seunome.txt

$ git diff

$ git commit -am "alterado seunome.txt"

$ git push 

$ git status







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
