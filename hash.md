# Dicas de hash 




## criar um hash 

$  echo "padoin" | md5sum  
$  echo "padoin" | sha256sum  
$  echo "padoin" | sha512sum  


## criar um hash de um arquivo

$ echo "12/05 padoin 50,00"  > a.txt  
$ md5sum  a.txt  


## validar o hash de um arquivo

$ md5sum  a.txt > hashcriado  
$ md5sum  -c a.txt hashcriado  


 
###	checar chaves publicas/privadas 
$ cd~  
$ cd .ssh  
$ cat id_rsa  
$ ssh-keygen -y -e -f id_rsa  
$ cat id_rsa.pub  




> ## Dicas hash  
> Padoin, Edson Luiz  
> padoin@unijui.edu.br



 
