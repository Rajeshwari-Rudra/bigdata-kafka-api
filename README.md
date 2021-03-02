# bigdata-kafka-api
Demo project of kafka api

# kafka-api

Example Kafka Producer and Consumer apps.

- Article: <https://www.javaworld.com/article/3060078/big-data/big-data-messaging-with-kafka-part-1.html>

## Recommended Environment

* [VS Code](https://code.visualstudio.com/)
* [VS Code Extension - Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)

## Prerequisities

* OpenJDK or JDK (8 or up)
* Apache Zookeeper, installed and working
* Apache Kafka, installed and working

## Start Zookeeper Service

- To start a zookeeper, open Powershell in your kafka directory and run this command

```Powershell
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```
- Note:- Leave this window open or minimize it.
----------------------------------------
## Command to start a Kafka Server
* Now open a new window and run Powershell as Administrator in your Kafka directory


```Powershell
.\bin\windows\kafka-server-start.bat .\config\server.properties
```
- Leave this window open or minimize it.

## Command to create a topic
- Choose your own topic name.
- Here, I have choosen 'account' as my topic name

```PowerShell
 .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic account
```

## Compile and Build the Fat Jar File

Open PowerShell as Administrator in the root project folder, compile the code using Maven and create an executable jar file. Generated artificacts can be found in the new 'target' folder.

```PowerShell
mvn clean compile assembly:single
```

## To start a Consumer

Open PowerShell as Administrator in the root project folder, start the original consumer app using topic account and group1 with:

```PowerShell
 java -cp target/bigdata-kafka-api-1.0-SNAPSHOT-jar-with-dependencies.jar edu.nwmissouri.bigdatarajeshwari.Consumer account group1
 
```
- Leave this window open or minimize it.

## To Start a Producer

Open a new PowerShell as Administrator in the root project folder, start the Producer app using topic account:

```PowerShell
 java -cp target/bigdata-kafka-api-1.0-SNAPSHOT-jar-with-dependencies.jar edu.nwmissouri.bigdatarajeshwari.ProducerSentence account
 java -cp target/bigdata-kafka-api-1.0-SNAPSHOT-jar-with-dependencies.jar edu.nwmissouri.bigdatarajeshwari.ProducerAccountHolder account
```
- Leave this window open or minimize it.





## References

- [Reference Repo](https://github.com/denisecase/kafka-api)
- [Kafa Tutorial](http://cloudurable.com/blog/kafka-tutorial-kafka-producer/index.html)
