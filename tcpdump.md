# Dicas comando `tcpdump`



 

## instalar o programa

$ sudo apt install `tcpdump`



## listar as interfaces disponíveis 

$ `tcpdump` -D
 

## listar os pacotes que estão passando por uma interfaces espcífica

$  sudo `tcpdump` -i wlp8s0


* opções:

> `-c` - definir a qtde de pacotes

$  sudo `tcpdump` -i wlp8s0 -c 10




> `greater` - filtrar pacotes maior que n bytes

$  sudo `tcpdump` -i wlp8s0 grater 512



> `-w` - redirecionar saida para arquivo

$ sudo `tcpdump` -i wlp8s0 -w a.txt



> `src` - filtrar pacotes de um IP

$ sudo tcpdump -i wlp8s0 src 8.8.8.8






> ## Dicas tcpdump  
> Padoin, Edson Luiz  
> padoin@unijui.edu.br
