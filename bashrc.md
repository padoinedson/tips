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


## dicas de utilização no screen

$ screen 

> 		Ctrl+a c  -> novo shell
> 		Ctrl+a nº -> trocar entre shell	
> 		Ctrl+d ou exit      -> fechar um shell 
> 		Ctrl+a ?  -> help
> 		Ctrl+a d  -> sair do screen




## dicas de recuperação de screens

$ screen -ls       -> Listando as "janelas" criadas pelo screen

$ screen -r   	   -> para recuperar a screem - retornar onde estava 





## configuração temporária no screen

> 		Ctrl+a :  
> 		hardstatus alwayslastline "%c %w" 



> ## Dicas screen  
> Padoin, Edson Luiz  
> padoin@unijui.edu.br
