# Dicas de SSH 




## Cliente 


### instalar o ssh

	$ sudo apt install ssh

### gerar a chave publica:

	$ ssh-keygen -t rsa 


### copiar a chave publica para o servidor

	$ cd  
	$ cd .ssh  
	$ scp id_rsa.pub usuario@IP_do_servidor:/home/labinf/seunome.pub  





## Servidor 

### instalar o ssh

	$ sudo apt install ssh

### gerar a chave publica:

	$ ssh-keygen -t rsa 


### autorizar - copiando a chava pública do cliente no final do arquivo .ssh/authorized_keys do servidor

> 	opção 1    
	$ cd    
	$ cat seunome.pub >> `.ssh/authorized_keys`    

>	opção 2:  
	vi `~/.ssh/authorized_keys`    


###	atualizar permissões
	$ cd .ssh
	$ chmod 0600 authorized_keys



###	checar chaves publicas/privadas 
	$ cd~  
	$ cd .ssh
	$ cat id_rsa  	
	$ ssh-keygen -y -e -f id_rsa
	$ cat id_rsa.pub




> ## Dicas ssh  
> Padoin, Edson Luiz  
> padoin@unijui.edu.br





Dar permissões na chave pública:
$	chmod 700 key


Efetuar conexão remota:
$	ssh -i key usuario@IP_do_servidor
