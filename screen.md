# Dicas de screen para Linux





## instalação
$ sudo apt install `screen`



## configuração permanente no arquivo ".screenrc"  

* editar o arquivo `.screenrc` por exemplo:

$ nano ~/.screenrc  
> 	shell -${SHELL}  
> 	caption always "%n(%t) : %c"  
> 	defscrollback 1024  
> 	startup_message off  
> 	hardstatus on  
> 	hardstatus alwayslastline
>
## utilização 1

$ screen 

> 		Ctrl+a c  -> novo shell
> 		Ctrl+a nº -> trocar entre shell	
> 		Ctrl+d ou exit      -> fechar um shell 
> 		Ctrl+a ?  -> help
> 		Ctrl+a d  -> sair do screen




## utilização 2

$ screen -r   	   -> para recuperar a screem - retornar onde estava 

$ screen -ls       -> Listando as "janelas" criadas pelo screen




## configuração temporária no screen

> 		Ctrl+a :  
> 		hardstatus alwayslastline "%c %w" 



> ## Dicas screen  
> Padoin, Edson Luiz  
> padoin@unijui.edu.br
