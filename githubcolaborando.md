# Dicas de Git e Github para Linux

# colaborando com projeto de equipes



<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTq65a7eURVcc8cpEB42M35mNIKilVo6ccW9XoAQampc2M4xRopPWGzA_ai8ho2YhyEgaQ&usqp=CAU">





## clonar um projeto remoto

$ git clone https://github.com/padoinedson/exercicio1.git






## 1o. trocar o modo de acesso do servidor remoto

$ git remote -v

> origin  https://github.com/padoinedson/exercicio1.git (fetch)  
> origin  https://github.com/padoinedson/exercicio1.git (push)  
> verifique que está como https  


## trocar o modo de acesso
$ git remote set-url origin ` git@github.com:padoinedson/exercicio1.git `


## verificar o modo de acesso
$ git remote -v




## copiar as modificações do servidor para o repositório local

$ git pull




## adicionar um arquivo
 
$ echo "este arquivo sera adicionado ao github" > a.txt

$ git status

$ git add a.txt

$ git status

$ git commit -m "criado arquivo a.txt"

$ git push 




## alterar o arquivo

 
$ echo "adicionamos mais uma linha ao arquivo" >> a.txt

$ git diff

$ git commit -am "alterado a.txt"

$ git push 

$ git status


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
