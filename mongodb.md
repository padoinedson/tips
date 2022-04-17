
# Dicas de shell para Linux



## instalar pacote

$ sudo apt install mongodb



## verificar o status do banco de dados 

$ sudo systemctl status mongodb




## verificar a versão instalada do banco de dados  

$ mongod --version



## executar 

$ /usr/bin/mongo



## comandos básicos


> show databases

> use sd

> show dbs

> db.customers.find()

> db.customers.insert( {nome:"luis", idade:"41"})

> db.customers.find()


> db.customers.find().pretty()


> db.customers.insert( {nome:"anna", idade:"40"})
  
> db.customers.find().pretty()


> db.customers.find({nome:"anna"}).pretty()


> db.createCollection("alunos")

> show collections

> db.alunos.insert({nome:"pedro", sobrenome:"santos"})

> db.alunos.find()




### atividade 1 - docker mongo  


$ sudo docker search mongo  
$ sudo docker pull mongo  
$ sudo docker run -it --name mongodb  mongo   /bin/bash  


$ sudo systemctl enable mongod   


mongo --eval 'db.runCommand({ connectionStatus: 1 })'  


$ sudo systemctl start mongod  
ou  
$ sudo service mongod start  

$ sudo systemctl status mongod  
ou  
$ sudo service mongod status  






> ## Dicas mongo
> Padoin, Edson Luiz  
> padoin@unijui.edu.br
