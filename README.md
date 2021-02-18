# ibm-mq-jms-client

Sample project as part of the `IBM MQ Developer Essentials learning path and badge`. \
Contains to client side Java apps. \ 

1) \ 
Uses `JMS API` to connect to `IBM MQ` messaging provider. \
Puts a message that holds sample data to a queue and the consumes it from the queue. \
Implements Point-to-Point messaging pattern. \ 
`JmsPutGet.java` is the entry point. 

#### Run JmsPutGet 
Change to `build` folder, then run: 
> java -cp "..\libs\javax.jms-api-2.0.1.jar;..\libs\com.ibm.mq.allclient-9.1.4.0.jar;." com.github.kanataidarov.ibm_mq_jms_client.p2p.JmsPutGet 

2) \ 
JMS application that integrates a Ticket reseller client with a an Event booking service. \
Implements Publisher/Subscriber messaging pattern. \ 
`Reseller.java` is the entry point. \ 

#### Run Reseller 
Change to `build` folder, then run: 
> java -cp "..\libs\javax.jms-api-2.0.1.jar;..\libs\com.ibm.mq.allclient-9.1.4.0.jar;." com.github.kanataidarov.ibm_mq_jms_client.pub_sub.Reseller

## Requirements
 - `Java 8` or higher 
 - `Docker` & `docker-compose` 
 - `IBM MQ` Java-client library (`com.ibm.mq.allclient-9.1.4.0.jar`)
 - `JMS API` library (`javax.jms-api-2.0.1.jar`)

## Run project 
> docker-compose up *(starts IBM MQ Console at address: https://localhost:9443, default login: admin, default password: passw0rd)* \
> java -cp ".\libs\com.ibm.mq.allclient-9.1.4.0.jar;.\libs\javax.jms-api-2.0.1.jar;." com.github.kanataidarov.ibm_mq_jms_client.JmsPutGet \

## Compile project 
>  javac -cp "libs\javax.jms-api-2.0.1.jar;libs\com.ibm.mq.allclient-9.1.4.0.jar" -d "build\" .\src\com\github\kanataidarov\ibm_mq_jms_client\pub_sub\*.java \ 
Compilation result can be found in `build` folder. 

## Ticket Service
To start service run: 
> docker-compose up -d 

`IBM MQ Developer Essentials learning path and badge` provided Ticket Service as MQ docker image. When deployed it will start both MQ server and the Ticket service. The MQ Server is preconfigured to create and configure the queues and topics that the Ticket Service requires. \
Based on `ibmcom/mq:latest` image from `Docker Hub`. 

#### Environment variables
You can override the default MQ connection settings using environment variables on the system where you run your `Reseller` application code. \

* **MQ_BADGE_QM_HOSTNAME** - Specify the Host name or IP address of your queue manager
* **MQ_BADGE_QM_NAME** - Set the queue manager name
* **MQ_BADGE_QM_PORT** - Listener port for your queue manager
* **MQ_BADGE_CHANNEL** - MQ Channel name
* **MQ_BADGE_USER** - User name that application uses to connect to MQ
* **MQ_BADGE_PASSWORD** - Password that the application uses to connect to MQ
