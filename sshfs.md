# Dicas de SSHFS - SSH Filesystem




## Atividade 1 ---- INSTALAÇÃO 

### Servidor

$ sudo apt install sshfs


### Cliente
 
$ sudo apt install sshfs






##	Test 1 - 

### Cliente

> criar um diretorio onde será mapeado o sistema de arquivos do servidor
 
$ mkdir nome2904




#### conectar/mapear o sistema de arquivos do servidor no diretório criado no cliente

> sshfs	user@IPserver:PATH	   		 pasta_local	  

$ sshfs `sd2022@200.132.195.243:/home/sd2022/`   `nome2904/`
  
$ cd nome2904/

$ ls




#### desconectar

$ cd .. ou cd ou cd ~

> fusermount -u pasta_local   

$ fusermount -u `nome2904`





 

> ## Dicas sshfs  
> Padoin, Edson Luiz  
> padoin@unijui.edu.br
