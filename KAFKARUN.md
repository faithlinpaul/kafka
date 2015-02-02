
fpaul@fpaul:~/tools/kafka$ bin/zookeeper-server-start.sh config/zookeeper.properties
fpaul@fpaul:~/tools/kafka$ bin/kafka-server-start.sh config/server.properties
fpaul@fpaul:~/tools/kafka$ bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor  1 --partitions 1 --topic test
Created topic "test".
fpaul@fpaul:~/tools/kafka$ bin/kafka-topics.sh --list --zookeeper localhost:2181
test
fpaul@fpaul:~/tools/kafka$ bin/kafka-console-producer.sh  --broker-list localhost:9092 --topic test
[2015-02-02 14:55:27,872] WARN Property topic is not valid (kafka.utils.VerifiableProperties)
First message
Second 
fpaul@fpaul:~/tools/kafka$ bin/kafka-console-consumer.sh --zookeeper localhost:2181 --topic test --from-beginning
First message
Second 
fpaul@fpaul:~/tools/kafka$ JMX_PORT=9997 bin/kafka-server-start.sh config/server-1.properties &
[1] 20467
fpaul@fpaul:~/tools/kafka$ [2015-02-02 15:10:48,206] INFO Verifying properties (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,241] INFO Property broker.id is overridden to 1 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,241] INFO Property log.cleaner.enable is overridden to false (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,241] INFO Property log.dirs is overridden to /tmp/kafka-logs-1 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,242] INFO Property log.retention.check.interval.ms is overridden to 300000 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,242] INFO Property log.retention.hours is overridden to 168 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,242] INFO Property log.segment.bytes is overridden to 1073741824 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,242] INFO Property num.io.threads is overridden to 8 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,243] INFO Property num.network.threads is overridden to 3 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,243] INFO Property num.partitions is overridden to 1 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,243] INFO Property num.recovery.threads.per.data.dir is overridden to 1 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,243] INFO Property port is overridden to 9093 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,243] INFO Property socket.receive.buffer.bytes is overridden to 65536 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,244] INFO Property socket.request.max.bytes is overridden to 104857600 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,244] INFO Property socket.send.buffer.bytes is overridden to 102400 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,244] INFO Property zookeeper.connect is overridden to localhost:2181 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,244] INFO Property zookeeper.connection.timeout.ms is overridden to 2000 (kafka.utils.VerifiableProperties)
[2015-02-02 15:10:48,273] INFO [Kafka Server 1], starting (kafka.server.KafkaServer)
[2015-02-02 15:10:48,274] INFO [Kafka Server 1], Connecting to zookeeper on localhost:2181 (kafka.server.KafkaServer)
[2015-02-02 15:10:48,283] INFO Starting ZkClient event thread. (org.I0Itec.zkclient.ZkEventThread)
[2015-02-02 15:10:48,289] INFO Client environment:zookeeper.version=3.4.6-1569965, built on 02/20/2014 09:09 GMT (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,289] INFO Client environment:host.name=fpaul (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,289] INFO Client environment:java.version=1.7.0_65 (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,289] INFO Client environment:java.vendor=Oracle Corporation (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,289] INFO Client environment:java.home=/usr/lib/jvm/java-7-openjdk-amd64/jre (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,289] INFO Client environment:java.class.path=:/home/fpaul/tools/kafka/bin/../core/build/dependant-libs-2.10.1*/*.jar:/home/fpaul/tools/kafka/bin/../examples/build/libs//kafka-examples*.jar:/home/fpaul/tools/kafka/bin/../contrib/hadoop-consumer/build/libs//kafka-hadoop-consumer*.jar:/home/fpaul/tools/kafka/bin/../contrib/hadoop-producer/build/libs//kafka-hadoop-producer*.jar:/home/fpaul/tools/kafka/bin/../clients/build/libs/kafka-clients*.jar:/home/fpaul/tools/kafka/bin/../libs/jopt-simple-3.2.jar:/home/fpaul/tools/kafka/bin/../libs/kafka_2.10-0.8.2-beta.jar:/home/fpaul/tools/kafka/bin/../libs/kafka_2.10-0.8.2-beta-javadoc.jar:/home/fpaul/tools/kafka/bin/../libs/kafka_2.10-0.8.2-beta-scaladoc.jar:/home/fpaul/tools/kafka/bin/../libs/kafka_2.10-0.8.2-beta-sources.jar:/home/fpaul/tools/kafka/bin/../libs/kafka_2.10-0.8.2-beta-test.jar:/home/fpaul/tools/kafka/bin/../libs/kafka-clients-0.8.2-beta.jar:/home/fpaul/tools/kafka/bin/../libs/log4j-1.2.16.jar:/home/fpaul/tools/kafka/bin/../libs/lz4-1.2.0.jar:/home/fpaul/tools/kafka/bin/../libs/metrics-core-2.2.0.jar:/home/fpaul/tools/kafka/bin/../libs/scala-library-2.10.1.jar:/home/fpaul/tools/kafka/bin/../libs/slf4j-api-1.7.6.jar:/home/fpaul/tools/kafka/bin/../libs/slf4j-log4j12-1.6.1.jar:/home/fpaul/tools/kafka/bin/../libs/snappy-java-1.1.1.3.jar:/home/fpaul/tools/kafka/bin/../libs/zkclient-0.3.jar:/home/fpaul/tools/kafka/bin/../libs/zookeeper-3.4.6.jar:/home/fpaul/tools/kafka/bin/../core/build/libs/kafka_2.10*.jar (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,289] INFO Client environment:java.library.path=/usr/java/packages/lib/amd64:/usr/lib/x86_64-linux-gnu/jni:/lib/x86_64-linux-gnu:/usr/lib/x86_64-linux-gnu:/usr/lib/jni:/lib:/usr/lib (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,289] INFO Client environment:java.io.tmpdir=/tmp (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,289] INFO Client environment:java.compiler=<NA> (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,289] INFO Client environment:os.name=Linux (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,289] INFO Client environment:os.arch=amd64 (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,289] INFO Client environment:os.version=3.13.0-44-generic (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,290] INFO Client environment:user.name=fpaul (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,290] INFO Client environment:user.home=/home/fpaul (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,290] INFO Client environment:user.dir=/home/fpaul/tools/kafka_2.10-0.8.2-beta (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,290] INFO Initiating client connection, connectString=localhost:2181 sessionTimeout=6000 watcher=org.I0Itec.zkclient.ZkClient@6bdd02c3 (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:10:48,312] INFO Opening socket connection to server localhost/127.0.0.1:2181. Will not attempt to authenticate using SASL (unknown error) (org.apache.zookeeper.ClientCnxn)
[2015-02-02 15:10:48,318] INFO Socket connection established to localhost/127.0.0.1:2181, initiating session (org.apache.zookeeper.ClientCnxn)
[2015-02-02 15:10:48,328] INFO Session establishment complete on server localhost/127.0.0.1:2181, sessionid = 0x14b498ba06c000b, negotiated timeout = 6000 (org.apache.zookeeper.ClientCnxn)
[2015-02-02 15:10:48,330] INFO zookeeper state changed (SyncConnected) (org.I0Itec.zkclient.ZkClient)
[2015-02-02 15:10:48,449] INFO Log directory '/tmp/kafka-logs-1' not found, creating it. (kafka.log.LogManager)
[2015-02-02 15:10:48,455] INFO Loading logs. (kafka.log.LogManager)
[2015-02-02 15:10:48,459] INFO Logs loading complete. (kafka.log.LogManager)
[2015-02-02 15:10:48,460] INFO Starting log cleanup with a period of 300000 ms. (kafka.log.LogManager)
[2015-02-02 15:10:48,463] INFO Starting log flusher with a default period of 9223372036854775807 ms. (kafka.log.LogManager)
[2015-02-02 15:10:48,511] INFO Awaiting socket connections on 0.0.0.0:9093. (kafka.network.Acceptor)
[2015-02-02 15:10:48,512] INFO [Socket Server on Broker 1], Started (kafka.network.SocketServer)
[2015-02-02 15:10:48,585] INFO Will not load MX4J, mx4j-tools.jar is not in the classpath (kafka.utils.Mx4jLoader$)
[2015-02-02 15:10:48,638] INFO Registered broker 1 at path /brokers/ids/1 with address fpaul:9093. (kafka.utils.ZkUtils$)
[2015-02-02 15:10:48,652] INFO [Kafka Server 1], started (kafka.server.KafkaServer)

fpaul@fpaul:~/tools/kafka$ JMX_PORT=9998 bin/kafka-server-start.sh config/server-2.properties &
[2] 20518
fpaul@fpaul:~/tools/kafka$ [2015-02-02 15:11:05,074] INFO Verifying properties (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,105] INFO Property broker.id is overridden to 2 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,105] INFO Property log.cleaner.enable is overridden to false (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,105] INFO Property log.dirs is overridden to /tmp/kafka-logs-2 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,105] INFO Property log.retention.check.interval.ms is overridden to 300000 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,106] INFO Property log.retention.hours is overridden to 168 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,106] INFO Property log.segment.bytes is overridden to 1073741824 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,106] INFO Property num.io.threads is overridden to 8 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,106] INFO Property num.network.threads is overridden to 3 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,107] INFO Property num.partitions is overridden to 1 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,107] INFO Property num.recovery.threads.per.data.dir is overridden to 1 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,107] INFO Property port is overridden to 9094 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,107] INFO Property socket.receive.buffer.bytes is overridden to 65536 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,107] INFO Property socket.request.max.bytes is overridden to 104857600 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,108] INFO Property socket.send.buffer.bytes is overridden to 102400 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,108] INFO Property zookeeper.connect is overridden to localhost:2181 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,108] INFO Property zookeeper.connection.timeout.ms is overridden to 2000 (kafka.utils.VerifiableProperties)
[2015-02-02 15:11:05,138] INFO [Kafka Server 2], starting (kafka.server.KafkaServer)
[2015-02-02 15:11:05,140] INFO [Kafka Server 2], Connecting to zookeeper on localhost:2181 (kafka.server.KafkaServer)
[2015-02-02 15:11:05,150] INFO Starting ZkClient event thread. (org.I0Itec.zkclient.ZkEventThread)
[2015-02-02 15:11:05,157] INFO Client environment:zookeeper.version=3.4.6-1569965, built on 02/20/2014 09:09 GMT (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,157] INFO Client environment:host.name=fpaul (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,157] INFO Client environment:java.version=1.7.0_65 (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,157] INFO Client environment:java.vendor=Oracle Corporation (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,158] INFO Client environment:java.home=/usr/lib/jvm/java-7-openjdk-amd64/jre (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,158] INFO Client environment:java.class.path=:/home/fpaul/tools/kafka/bin/../core/build/dependant-libs-2.10.1*/*.jar:/home/fpaul/tools/kafka/bin/../examples/build/libs//kafka-examples*.jar:/home/fpaul/tools/kafka/bin/../contrib/hadoop-consumer/build/libs//kafka-hadoop-consumer*.jar:/home/fpaul/tools/kafka/bin/../contrib/hadoop-producer/build/libs//kafka-hadoop-producer*.jar:/home/fpaul/tools/kafka/bin/../clients/build/libs/kafka-clients*.jar:/home/fpaul/tools/kafka/bin/../libs/jopt-simple-3.2.jar:/home/fpaul/tools/kafka/bin/../libs/kafka_2.10-0.8.2-beta.jar:/home/fpaul/tools/kafka/bin/../libs/kafka_2.10-0.8.2-beta-javadoc.jar:/home/fpaul/tools/kafka/bin/../libs/kafka_2.10-0.8.2-beta-scaladoc.jar:/home/fpaul/tools/kafka/bin/../libs/kafka_2.10-0.8.2-beta-sources.jar:/home/fpaul/tools/kafka/bin/../libs/kafka_2.10-0.8.2-beta-test.jar:/home/fpaul/tools/kafka/bin/../libs/kafka-clients-0.8.2-beta.jar:/home/fpaul/tools/kafka/bin/../libs/log4j-1.2.16.jar:/home/fpaul/tools/kafka/bin/../libs/lz4-1.2.0.jar:/home/fpaul/tools/kafka/bin/../libs/metrics-core-2.2.0.jar:/home/fpaul/tools/kafka/bin/../libs/scala-library-2.10.1.jar:/home/fpaul/tools/kafka/bin/../libs/slf4j-api-1.7.6.jar:/home/fpaul/tools/kafka/bin/../libs/slf4j-log4j12-1.6.1.jar:/home/fpaul/tools/kafka/bin/../libs/snappy-java-1.1.1.3.jar:/home/fpaul/tools/kafka/bin/../libs/zkclient-0.3.jar:/home/fpaul/tools/kafka/bin/../libs/zookeeper-3.4.6.jar:/home/fpaul/tools/kafka/bin/../core/build/libs/kafka_2.10*.jar (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,158] INFO Client environment:java.library.path=/usr/java/packages/lib/amd64:/usr/lib/x86_64-linux-gnu/jni:/lib/x86_64-linux-gnu:/usr/lib/x86_64-linux-gnu:/usr/lib/jni:/lib:/usr/lib (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,158] INFO Client environment:java.io.tmpdir=/tmp (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,158] INFO Client environment:java.compiler=<NA> (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,158] INFO Client environment:os.name=Linux (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,158] INFO Client environment:os.arch=amd64 (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,158] INFO Client environment:os.version=3.13.0-44-generic (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,158] INFO Client environment:user.name=fpaul (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,158] INFO Client environment:user.home=/home/fpaul (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,158] INFO Client environment:user.dir=/home/fpaul/tools/kafka_2.10-0.8.2-beta (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,159] INFO Initiating client connection, connectString=localhost:2181 sessionTimeout=6000 watcher=org.I0Itec.zkclient.ZkClient@6bdd02c3 (org.apache.zookeeper.ZooKeeper)
[2015-02-02 15:11:05,186] INFO Opening socket connection to server localhost/127.0.0.1:2181. Will not attempt to authenticate using SASL (unknown error) (org.apache.zookeeper.ClientCnxn)
[2015-02-02 15:11:05,190] INFO Socket connection established to localhost/127.0.0.1:2181, initiating session (org.apache.zookeeper.ClientCnxn)
[2015-02-02 15:11:05,200] INFO Session establishment complete on server localhost/127.0.0.1:2181, sessionid = 0x14b498ba06c000c, negotiated timeout = 6000 (org.apache.zookeeper.ClientCnxn)
[2015-02-02 15:11:05,202] INFO zookeeper state changed (SyncConnected) (org.I0Itec.zkclient.ZkClient)
[2015-02-02 15:11:05,323] INFO Log directory '/tmp/kafka-logs-2' not found, creating it. (kafka.log.LogManager)
[2015-02-02 15:11:05,328] INFO Loading logs. (kafka.log.LogManager)
[2015-02-02 15:11:05,333] INFO Logs loading complete. (kafka.log.LogManager)
[2015-02-02 15:11:05,334] INFO Starting log cleanup with a period of 300000 ms. (kafka.log.LogManager)
[2015-02-02 15:11:05,338] INFO Starting log flusher with a default period of 9223372036854775807 ms. (kafka.log.LogManager)
[2015-02-02 15:11:05,358] INFO Awaiting socket connections on 0.0.0.0:9094. (kafka.network.Acceptor)
[2015-02-02 15:11:05,359] INFO [Socket Server on Broker 2], Started (kafka.network.SocketServer)
[2015-02-02 15:11:05,411] INFO Will not load MX4J, mx4j-tools.jar is not in the classpath (kafka.utils.Mx4jLoader$)
[2015-02-02 15:11:05,467] INFO Registered broker 2 at path /brokers/ids/2 with address fpaul:9094. (kafka.utils.ZkUtils$)
[2015-02-02 15:11:05,492] INFO [Kafka Server 2], started (kafka.server.KafkaServer)

fpaul@fpaul:~/tools/kafka$ bin/kafka-topics.sh --describe  --zookeeper localhost:2181
Topic:my-replicated-topic	PartitionCount:1	ReplicationFactor:3	Configs:
Topic: my-replicated-topic	Partition: 0	Leader: 1	Replicas: 1,0,2	Isr: 1,0,2
Topic:test	PartitionCount:1	ReplicationFactor:1	Configs:
Topic: test	Partition: 0	Leader: 0	Replicas: 0	Isr: 0

fpaul@fpaul:~/tools/kafka$ bin/kafka-console-producer.sh --broker-list localhost:9092 --topic my-replicated-topic
[2015-02-02 15:23:16,299] WARN Property topic is not valid (kafka.utils.VerifiableProperties)
test 1 ooooooooooo
test 2 9999999999999999
hello
passup

fpaul@fpaul:~/tools/kafka$ bin/kafka-console-consumer.sh --zookeeper localhost:2181 --from-beginning --topic my-replicated-topic
[2015-02-02 15:25:01,189] INFO Closing socket connection to /127.0.0.1. (kafka.network.Processor)
test 1 ooooooooooo
test 2 9999999999999999
hello
passup
fpaul@fpaul:~/tools/kafka$ pkill -9 -f server-1.properties


fpaul@fpaul:~/tools/kafka$ bin/kafka-topics.sh --describe  --zookeeper localhost:2181
Topic:my-replicated-topic	PartitionCount:1	ReplicationFactor:3	Configs:
	Topic: my-replicated-topic	Partition: 0	Leader: 0	Replicas: 1,0,2	Isr: 0,2
Topic:test	PartitionCount:1	ReplicationFactor:1	Configs:
	Topic: test	Partition: 0	Leader: 0	Replicas: 0	Isr: 0




[2015-02-02 15:27:27,394] INFO [ReplicaFetcherThread-0-0], Starting  (kafka.server.ReplicaFetcherThread)
[2015-02-02 15:27:27,394] INFO [ReplicaFetcherThread-0-1], Shutting down (kafka.server.ReplicaFetcherThread)
[2015-02-02 15:27:27,588] INFO [ReplicaFetcherThread-0-1], Stopped  (kafka.server.ReplicaFetcherThread)
[2015-02-02 15:27:27,588] INFO [ReplicaFetcherThread-0-1], Shutdown completed (kafka.server.ReplicaFetcherThread)
fpaul@fpaul:~/tools/kafka$ 
[1]-  Killed                  JMX_PORT=9997 bin/kafka-server-start.sh config/server-1.properties
fpaul@fpaul:~/tools/kafka$ 
fpaul@fpaul:~/tools/kafka$ bin/kafka-console-consumer.sh --zookeeper localhost:2181 --from-beginning --topic my-replicated-topic
test 1 ooooooooooo
test 2 9999999999999999
hello
passup


