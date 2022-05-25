# Dicas de MQTT para Linux
 

## MQTT - Message Queuing Telemetry Transport 





### Brokers 

> https://github.com/mqtt/mqtt.github.io/wiki/servers

>	mosquitto - http://mosquitto.org/  
>	Amazon MQ - ActiveMQ    
>	Microsft  - Azure IoT Hub    
>	cloudmqtt - https://www.cloudmqtt.com/   
>	paho      - https://pypi.org/project/paho-mqtt/   
>	RabbitMQ  - https://www.rabbitmq.com/  
>	ZeroMq   
>	Kafka   




# Mosquitto

## Atividade 1 ---- INSTALAÇÃO 

###	mosquitto - install  


		$ sudo apt install mosquitto  

		$ sudo apt install mosquitto-clients  


## Atividade 1.1 ---- GERENCIAMENTO 

#### Status

		$ pgrep mosquitto  
		$ ps -ef | grep mosquitto  
		$ top  
		$ ps -fax  





####	Test 1 - localhost
 

		Terminal 1:

		$ mosquitto_sub -v -t '#'    

>				-v verbose  
>				-t topic  
>				-p port  

		Terminal 2:

		$ mosquitto_pub -h localhost -m "22.5" -t sensor1sala  



####	Test 1.1 - localhost


		Terminal 1:  

		$ mosquitto_sub -v -t 'salajantar'  

		Terminal 2:  

		$ mosquitto_pub -h localhost -m "100" -t salajantar  



####	Test 1.2 - localhost com erro


		Terminal 1:  

		$ mosquitto_sub -v -t 'sala'  


		Terminal 2:  

		$ mosquitto_pub -h localhost -m "100" -t quarto  



####	Test 2 - localhost com bash


		Terminal 1:  

		$ mosquitto_sub -v -t '#'  


		Terminal 2:  

		$ cd bash  

		$ bash sensor.sh start  

	

####	Test 2.1 - localhost com bash

		Terminal 1:  

		$ mosquitto_sub -v -t '#'  


		Terminal 2:  

		$ cd bash    

		$ bash semaforo.sh sede    



		Terminal 3:  

		$ cd bash  

		$ bash semaforo.sh posto  




####	Test 3 - servidor mosquitto.org
 


		https://test.mosquitto.org/  


		mosquitto_sub -h test.mosquitto.org -t "#" -v  

		mosquitto_pub -h test.mosquitto.org -m "22.0" -t "casa/sensor1"  

		mosquitto_pub -h test.mosquitto.org -m "22.0" -t "casa/sensor2"  




####	Test 3.1 - servidor mosquitto.org
 

		mosquitto_sub -h test.mosquitto.org -t "casa/sensor1"  

		mosquitto_pub -h test.mosquitto.org -m "22.0" -t "casa/sensor1"  

		mosquitto_pub -h test.mosquitto.org -m "22.0" -t "casa/sensor2"  




####	Test 3.2 - servidor mosquitto.org - chamada
	
		mosquitto_sub -h test.mosquitto.org -t "chamada/2204"  

		mosquitto_pub -h test.mosquitto.org -m "padoin" -t "chamadasd"  





####	Test 4 - mosquitto com Python - paho



	install  


		$ sudo apt install mosquitto  

		$ sudo apt install mosquitto-clients  

		$ pgrep mosquitto  

	
		$sudo apt-get install python-pip   

		$sudo pip install --upgrade setuptools   

		$pip install --upgrade pip  

		$pip install paho-mqtt 



####	Test 4.1 - mosquitto com Python - paho
 
		$ cd /trabalhos1/Mosquitto3 java PHP Python/python-mqtt  

		$ python Subscribe.py  

		$ python Publish.py  



####	Test 4.2 - mosquitto com Python - paho

		$ cd /trabalhos2/PahoMQTT_Python_Go/PYTHON  

		$ python sub.py  

		$ python pub.py  



####	mosquitto - shutdown

		$ pgrep mosquitto  

		$ sudo kill -9 <pid>  








####	Test 5 - mosquitto com docker






> criar uma pasta   

$ mkdir docker-mqtt  


> entrar na pasta  

$ cd docker-mqtt  


> criar um arquivo Dockerfile  

$ nano Dockerfile 


		# Dockerfile for mosquitto  
 


		FROM ubuntu  

		RUN apt-get update -y  

		RUN apt-get -y install net-tools  

		RUN apt-get -y install iputils-ping  

		RUN groupadd -g 1883 mosquitto && \  
		    useradd -r -u 1883 -g mosquitto mosquitto  

		RUN apt install mosquitto -y  

		RUN apt install mosquitto-clients -y  

		EXPOSE 1883  

		CMD ["/usr/sbin/mosquitto", "-c", "/mosquitto/config/mosquitto.conf]  



> criar uma imagem  

$ docker build -t mosquitto -f Dockerfile .   


> desistalar o docker do host   

$ sudo apt remove mosquitto  


> criar um container  

$ docker run -it -p 1883:1883 -p 9001:9001 mosquitto /bin/bash  


> levantar mosquitto  

$ mosquitto &  

 


> subscribe no terminal 1

$ mosquitto_sub -h localhost -v -t '#'  


> publish no terminal 2  

$ mosquitto_pub -h 172.17.0.2 -m "nome" -t teste  












###  RabbitMQ


https://www.rabbitmq.com/  
https://www.rabbitmq.com/download.html  
https://www.rabbitmq.com/getstarted.html  
https://www.rabbitmq.com/devtools.html  
https://www.rabbitmq.com/tutorials/tutorial-one-python.html  


	install  

		$ sudo apt-get install rabbitmq-server  

		$ pip install pika   

 
 
>	"O RabbitMQ não permite ver as mensagens sendo printadas no servidor direto pelo servidor
	Porém, é possível ver as filas que nele existem: sudo rabbitmqctl list_queues"
 

####	Test 5.1 - rabbitmq com Python - paho  


		$ cd ~/trabalhos1/RabbitMQ java Python/Python  

		$ cat ~/trabalhos1/RabbitMQ java Python/Python/1.instrucoes.txt  




####	Test 5.2 - rabbitmq com Python - paho


		$ cd ~/trabalhos2/rabbitmq python  

		python producer  

		python consumer  


















Links:
http://www.hivemq.com/blog/how-to-get-started-with-mqtt  
http://www.ibm.com/developerworks/br/cloud/library/cl-bluemix-arduino-iot2/  
https://blog.butecopensource.org/mqtt-parte-1-o-que-e-mqtt/  
https://github.com/mqtt/mqtt.github.io/wiki/servers  
