# Dicas de BAAS - Backend as a Service





## BAAS do google
 
https://firebase.google.com/?hl=pt-br


### Console:
 
https://console.firebase.google.com/u/0/?pli=1



## cURL

> é uma ferramenta de linha de comando disponível nos principais sistemas operacionais


#### testar cURL:


$ curl www.unijui.edu.br  

$ curl -v www.unijui.edu.br  





## cURL + Firebase


$ curl      https://teste2510-31cb1.firebaseio.com/clientes.json  

$ curl -v  'https://teste2510-31cb1.firebaseio.com/clientes.json'  




#### verbos POST e GET 


$ curl -X POST -d '{ "first": "edson", "last": "padoin" }' 'https://teste2510-31cb1.firebaseio.com/clientes/100.json'  

$ curl -X GET 'https://teste2510-31cb1.firebaseio.com/clientes.json'   

$ curl -X POST -d '{ "first": "Maria", "last": "Lima" }' 'https://teste2510-31cb1.firebaseio.com/clientes/101.json'  

$ curl -X GET 'https://teste2510-31cb1.firebaseio.com/clientes.json'   

$ curl -X GET 'https://teste2510-31cb1.firebaseio.com/clientes/101.json'  




#### verbos PUT e GET 

$ curl -X PUT -d '{ "first": "Edson Luiz", "last": "Padoin" }' 'https://teste2510-31cb1.firebaseio.com/clientes/100.json'  

$ curl -X GET 'https://teste2510-31cb1.firebaseio.com/clientes.json'  




#### verbos DELETE e GET 

$  curl -X DELETE 'https://teste2510-31cb1.firebaseio.com/clientes/100.json'  

$ curl -X GET 'https://teste2510-31cb1.firebaseio.com/clientes.json'  



> ## Dicas git  
> Padoin, Edson Luiz  
> padoin@unijui.edu.br
