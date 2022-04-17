# Dicas de SSHFS - SSH Filesystem





## instalar o SSHFS

### Servidor

$ sudo apt install sshfs


### Cliente
 
$ sudo apt install sshfs






## utilização 

### Cliente

> criar um diretorio onde será mapeado o servidor
 
$ mkdir nome2904


#### -- conectar -- mapear o servidor no diretório criado no cliente

> sshfs	user@IPserver:PATH	   		 pasta_local	  

$ sshfs `sd2022@200.132.194.75:/home/sd2022/`   `nome2904/`
 

 
$ cd nome2904/

$ ls

$ echo "testando o sshfs......" > nome.txt





#### -- desconectar

$ cd .. ou cd ou cd ~

> fusermount -u pasta_local   

$ fusermount -u `nome2904`





 

> ## Dicas sshfs  
> Padoin, Edson Luiz  
> padoin@unijui.edu.br
