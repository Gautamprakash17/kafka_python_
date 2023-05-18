# kafka_python_
#from windows: open kafka folder:
     Required Commands:

          .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties

          .\bin\windows\kafka-server-start.bat .\config\server.properties

#if you want to run on ec2 then:
           1. wget https://downloads.apache.org/kafka/3.4.0/kafka_2.13-3.4.0.tgz
           2. tar -xvf kafka_2.13-3.4.0.tgz

           3.--------------------------------------------------
            java -version
            sudo yum update
            sudo yum install java-1.8.0
            #sudo yum install java-1.8.0-openjdk
            java -version
            cd kafka_2.13-3.4.0



------------------------------------
#same for both loacal as well as on ec2
     -------------------------------
           Start Zoo-keeper:
      -------------------------------
                  bin/zookeeper-server-start.sh config/zookeeper.properties

#Open another window to start kafka
                    But first ssh to to your ec2 machine as done above

------------------------------------------
            Start Kafka-server:
----------------------------------------
#Duplicate the session & enter in a new WINDOW --
                    CONNECT TO EC2 INSTANCE BY SSH....... KEY
 #WILL ALLOCATE SOME AMOUNT OF MEMORY TO KAFKA SERVER
              export KAFKA_HEAP_OPTS="-Xmx256M -Xms128M"
              cd kafka_2.13-3.4.0
              bin/kafka-server-start.sh config/server.properties

It is pointing to private server , change server.properties so that it can run in public IP 

To do this , you can follow any of the 2 approaches shared belwo --
Do a "sudo nano config/server.properties" - change ADVERTISED_LISTENERS to public ip of the EC2 instance

-----------------------------------------------
Create the topic:
-----------------------------
          Duplicate the session & enter in a new console --
          cd kafka_2.12-3.3.1
          bin/kafka-topics.sh --create --topic demo_testing2 --bootstrap-server {Put the Public IP or your EC2 Instance:9092} --replication-factor 1 --partitions 1

----------------------------
Start Producer:
--------------------------
         bin/kafka-console-producer.sh --topic demo_test --bootstrap-server {Put the Public IP of your EC2 Instance:9092} 




---------------------------------------
Start Consumer:
-------------------------
Duplicate the session & enter in a new console --
cd kafka_2.12-3.3.1
bin/kafka-console-consumer.sh --topic demo_test --bootstrap-server {Put the Public IP or your EC2 Instance:9092}




