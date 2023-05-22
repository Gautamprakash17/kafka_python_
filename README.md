To run Kafka using the Command Prompt (CMD) in Windows, you need to execute a few commands in the correct order. Here are the steps to run Kafka:

1.Start ZooKeeper:

  Open a new Command Prompt window.
  Navigate to the Kafka installation directory.
  Run the following command to start ZooKeeper:
  arduino
  Copy code:
             .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
2.Start Kafka server:

  Open another Command Prompt window.
  Navigate to the Kafka installation directory.
  Run the following command to start the Kafka server:
  arduino
  Copy code:
           .\bin\windows\kafka-server-start.bat .\config\server.properties
3.Create a topic (optional):

  Open a new Command Prompt window.
  Navigate to the Kafka installation directory.
  Run the following command to create a topic:

  Copy code:
           .\bin\windows\kafka-topics.bat --create --topic my-topic --bootstrap-server 10.1.1.109:9092 --partitions 1 --replication-factor 1
  Replace "my-topic" with the desired topic name.

4.Produce messages (optional):

  Open a new Command Prompt window.
  Navigate to the Kafka installation directory.
  Run the following command to produce messages to the topic:
  Copy code:
           .\bin\windows\kafka-console-producer.bat --topic my-topic --bootstrap-server 10.1.1.109:9092

Replace "my-topic" with the desired topic name. You can then type messages that will be sent to the Kafka topic.

5.Consume messages (optional):

  Open another Command Prompt window.
  Navigate to the Kafka installation directory.
  Run the following command to consume messages from the topic:
  Copy code:
            .\bin\windows\kafka-console-consumer.bat --topic my-topic --bootstrap-server 10.1.1.109:9092 --from-beginning
Replace "my-topic" with the desired topic name. You will see the messages produced in step 4 being consumed and displayed in the console.

These commands assume you have installed Kafka and its dependencies correctly. Adjust the paths if your Kafka installation is in a different directory. Additionally, make sure to adjust topic names and other parameters as per your requirements.

By following these steps, you can run Kafka using the Command Prompt in Windows and perform basic operations like starting Kafka, creating topics, and producing/consuming messages.






