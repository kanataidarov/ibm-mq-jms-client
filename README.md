# ibm-mq-jms-client

Sample project as part of the IBM MQ Developer Essentials learning path and badge. 
Uses JMS API to connect to IBM MQ messaging provider. 
Puts a message that holds sample data to a queue and the consumes it from the queue. 

## Requirements
 - Java 8 or higher 
 - Docker & docker-compose 

## Run project 
docker-compose up (starts IBM MQ Console at address: https://localhost:9443, default login: admin, default password: passw0rd) \
java -cp ".\com.ibm.mq.allclient-9.1.4.0.jar;.\javax.jms-api-2.0.1.jar;." com.github.kanataidarov.ibm_mq_jms_client.JmsPutGet \

## Compile project
javac -cp ".\com.ibm.mq.allclient-9.1.4.0.jar;.\javax.jms-api-2.0.1.jar" .\com\github\kanataidarov\ibm_mq_jms_client\JmsPutGet.java \
