# Dicas de screen para Linux



## instalação
$ sudo apt install screen



## configuração permanente no arquivo `.screenrc`  `Tutorial`

$ nano ~/.screenrc

	shell -${SHELL}

	caption always "%n(%t) : %c"

	defscrollback 1024

	startup_message off

	hardstatus on

	hardstatus alwayslastline


## utilização 1


$ screen 

		Ctrl+a c  -> novo shell

		Ctrl+a nº  -> troca de shellscreen	

		Ctrl+a d  -> fechar screen

		Ctrl+a  ? -> help

		exit -> para sair o screen



## utilização 2

$ screen -r -> para recuperar a tela onde estava 

$ screen -ls  -> Listando as "janelas" criadas pelo screen




## configuração temporária no screen

		Ctrl+a : 
		hardstatus alwayslastline "%c %w" 

