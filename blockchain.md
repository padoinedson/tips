

# Criação de uma rede ethereum privada


## --- CONTAINER 

### criar uma pasta para os dados do blockchain
> esta pasta vai ser compartilhada com o container  

$ cd ~  
$ mkdir ethereum  


### salvar o arquivo genesis.json dentro da pasta ethereum

              {
                  "config": {
                    "chainId": 2022,
                    "homesteadBlock": 0,
                    "eip150Block": 0,
                    "eip155Block": 0,
                    "eip158Block": 0,
                    "byzantiumBlock": 0,
                    "constantinopleBlock": 0,
                    "petersburgBlock": 0,
                    "istanbulBlock": 0
                  },
                  "alloc": {
                              "0x90bA23C7A92C7d524E5B5cc9D6dA30D65Ba30944": {
                                "balance": "5000"
                              },
                              "0x90F8BE615B29B10B2E4B9BbF3ae17B970c86b955": {
                                "balance": "6000"
                              }
                  },
                  "coinbase": "0x0000000000000000000000000000000000000000",
                  "difficulty": "0x20000",
                  "extraData": "",
                  "gasLimit": "0x2fefd8",
                  "nonce": "0x0000000000000111",
                  "mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000",
                  "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
                  "timestamp": "0x00"
              }

> nossa blockchain tem chainId igual a 2022  
> o arquivo genesis.json está cofigurado para criar dois usuarios com os valores (5000 e 6000)
> atualizar os campos do alloc com as chaves públicas dos usuários criados



### baixar imagem
> no hub do docker tem várias imagens prontas  
> vamos usar esta: https://hub.docker.com/r/ethereum/client-go    

$ sudo docker pull ethereum/client-go  







### rodar o container
> no 1o terminal - para gerenciar o docker

$ sudo docker run -d --name ethereum-node -v  $HOME/ethereum:/root -p 8545:8545 -p 8544:8544 -p 30301:30301 -p 30302:30302 -it --entrypoint=/bin/sh ethereum/client-go

          > se você já havia criado o container e não excluido
          $ sudo docker start ethereum-node
          $ sudo docker ps


> no 2o terminal - acessar o container

  $ sudo docker exec -it ethereum-node sh   
  $ cd /root

  > conferir se o arquivo genesis.json está no local

  $ ls


> no 3o terminal - acessar o container

  $ sudo docker exec -it ethereum-node sh   
  $ cd /root

  > conferir se o arquivo genesis.json está no local 

  $ ls


## --- GETH


### visualizar as oções de config do geth 
$ geth --help

> mais info:  
> https://hub.docker.com/r/ethereum/client-go  
> https://geth.ethereum.org/docs/rpc/server  
> https://github.com/ethereum/go-ethereum/blob/master/README.md  



## --- CONTAS


### criar as contas
> no 2o terminal 

$ geth account new --datadir ~/padoin1  

> guardar a sua chave pública

> no 3o terminal 

$ geth account new --datadir ~/padoin2
 

> guardar a sua chave pública
 


### visualizar chaves privadas das contas   
$ cat /root/padoin1/keystore/nome_do_arquivo_indicado_na_criacao



### atualizar as chaves públicas das contas criadas no arquivo genesis.json
> editar os campos alloc (chave publica e valor inicial wei - eth)   

      "alloc": {  
        "<0xd1a2DdAd9d9Da721ADa7eE7d67731C5cFFd37434>": {  
          "5000>"  
        },  
        "<0xF7EFc9DdA6CfEd205af4FD8fEf225cC61912fa7D>": {  
          "6000>"  
        }  
      }  

### conferir arquivo genesis 
$ cat /root/genesis.json



## --- NÓS

### inicializa os nós na rede 
> no 2o terminal  

$ cd /root  
$ geth init genesis.json --datadir ~/padoin1


> no 3o terminal  

$ cd /root  
$ geth init genesis.json --datadir ~/padoin2






### coloca os nós da rede para rodar 

> no 2o terminal 

$ geth --datadir ~/padoin1 --networkid 2022 --http --http.api 'txpool,eth,net,web3,personal,admin,miner' --http.corsdomain '*' --allow-insecure-unlock console


> no 3o terminal 

$ geth --datadir ~/padoin2 --networkid 2022 --http --http.api 'txpool,eth,net,web3,personal,admin,miner' --http.corsdomain '*' --port 30302  --http.port 8544  --allow-insecure-unlock console


> definir a mesma networkid do arquivo genesis.json  
> define uma porta diferente para cada nodo --port 30302     
> usar "--allow-insecure-unlock" para habilitar "unlocking accounts"  
> opção "console" chama o console do "geth"


## --- ADM

### visualizar qtde de pares
$ net.peerCount


### adiciona um par
$ admin.addPeer("enode do outro nó");
> informado quando colocamos o nó para rodar


### visualizar se adicionou os pares
$ net.peerCount


### visualizar informações sobre os pares
$ admin.peers

### conferir - genesis e head ainda são os mesmos
$ admin.nodeInfo
 





## --- CONTAS

### exibe as contas
$ eth.accounts
> em cada terminal temos uma conta  


### verificar o saldo das contas
$ eth.getBalance("0xd1a2DdAd9d9Da721ADa7eE7d67731C5cFFd37434")  
$ eth.getBalance("0xF7EFc9DdA6CfEd205af4FD8fEf225cC61912fa7D")  





## --- MINERAR

### minerar 
> 10 indica a quantidade de threads  

$ miner.start(10)

### para mineração
$ miner.stop()

### verificar o sado - conferir os ganhos da mineração
$ eth.getBalance("0xd1a2DdAd9d9Da721ADa7eE7d67731C5cFFd37434")  
 
### conferir - genesis e head não são os mesmos
$ admin.nodeInfo







## --- TRANSAÇÃO

### verificar o saldo das contas
$ eth.getBalance("0xd1a2DdAd9d9Da721ADa7eE7d67731C5cFFd37434")  
$ eth.getBalance("0xF7EFc9DdA6CfEd205af4FD8fEf225cC61912fa7D")


### liberar a conta para uso
$ personal.unlockAccount("0xd1a2DdAd9d9Da721ADa7eE7d67731C5cFFd37434")  


###  enviar uma transação
$ eth.sendTransaction({from:"0xd1a2DdAd9d9Da721ADa7eE7d67731C5cFFd37434", to:"0xF7EFc9DdA6CfEd205af4FD8fEf225cC61912fa7D", value:1000, gas:21000})

### verificar o pool de transações
$ txpool.status
> verifique que a transação está pendente  
>      {  
>        pending: 1,  
>        queued: 0  
>      }  


### minerar - 10 indica qtde threads
$ miner.start(10)

### stop miner
$ miner.stop()


### verificar o pool de transações
$ txpool.status
> verifique que a transação foi realizada  
>      {  
>        pending: 0,  
>        queued: 0  
>      }  


### ver o novo saldo das contas
$ eth.getBalance("0xd1a2DdAd9d9Da721ADa7eE7d67731C5cFFd37434")
$ eth.getBalance("0xF7EFc9DdA6CfEd205af4FD8fEf225cC61912fa7D")




## --- CONTAS


### criar conta dentro do nó
personal.newAccount()

### exibir todas as contas
$ eth.accounts

### ver o saldo de cada conta
$ eth.getBalance("0x2252c45b06524e132b57b1fd3fbf65d2e2e8fb5c")





## --- CONTAINER 

### parar o container  
$ sudo docker stop ethereum-node


### excluir o container  
$ docker rm ethereum-node





