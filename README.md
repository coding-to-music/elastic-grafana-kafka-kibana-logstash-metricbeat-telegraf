# elastic-grafana-kafka-kibana-logstash-metricbeat-telegraf

# 🚀 telegraf SSL - kafka SSL - logstash - elasticsearch - kibana - metricbeat- grafana monitoring system on docker compose 🚀

https://github.com/coding-to-music/elastic-grafana-kafka-kibana-logstash-metricbeat-telegraf

From / By seyeon-shijuan https://github.com/seyeon-shijuan

https://github.com/seyeon-shijuan/monitoring-system

## Environment variables:

cp .env-example .env

```java
ELK_VERSION=7.11.1
```

## GitHub

```java
git init
git add .
git remote remove origin
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:coding-to-music/elastic-grafana-kafka-kibana-logstash-metricbeat-telegraf.git
git push -u origin main
```

# docker-compose up

```
docker-compose up
```

## Errors and messages:

```
metricbeat       | 2022-07-30T06:39:56.024Z     ERROR   [publisher_pipeline_output]     pipeline/output.go:154  Failed to connect to backoff(elasticsearch(http://elasticsearch:9200)): Get "http://elasticsearch:9200": dial tcp 192.168.240.4:9200: connect: connection refused
metricbeat       | 2022-07-30T06:39:56.025Z     INFO    [publisher]     pipeline/retry.go:219   retryer: send unwait signal to consumer
metricbeat       | 2022-07-30T06:39:56.025Z     INFO    [publisher]     pipeline/retry.go:223     done
metricbeat       | 2022-07-30T06:39:56.024Z     INFO    [publisher_pipeline_output]     pipeline/output.go:145  Attempting to reconnect to backoff(elasticsearch(http://elasticsearch:9200)) with 5 reconnect attempt(s)
metricbeat       | 2022-07-30T06:39:56.034Z     WARN    [transport]     transport/tcp.go:52     DNS lookup failure "elasticsearch": lookup elasticsearch: no such host
kibana_1         | {"type":"log","@timestamp":"2022-07-30T06:39:56+00:00","tags":["warning","elasticsearch","monitoring"],"pid":6,"message":"Unable to revive connection: http://elasticsearch:9200/"}
kibana_1         | {"type":"log","@timestamp":"2022-07-30T06:39:56+00:00","tags":["warning","elasticsearch","monitoring"],"pid":6,"message":"No living connections"}
kibana_1         | {"type":"log","@timestamp":"2022-07-30T06:39:56+00:00","tags":["warning","plugins","licensing"],"pid":6,"message":"License information could not be obtained from Elasticsearch due to Error: No Living connections error"}
kafka-manager    | 2022-07-30 06:39:58,061 - [INFO] k.m.a.KafkaManagerActor - Updating internal state...
logstash_1       | [2022-07-30T06:40:00,482][WARN ][logstash.outputs.elasticsearch][main] Attempted to resurrect connection to dead ES instance, but got an error. {:url=>"http://elasticsearch:9200/", :error_type=>LogStash::Outputs::ElasticSearch::HttpClient::Pool::HostUnreachableError, :error=>"Elasticsearch Unreachable: [http://elasticsearch:9200/][Manticore::ResolutionFailure] elasticsearch"}
kafka            | [2022-07-30 06:40:02,105] WARN [SocketServer brokerId=1001] Unexpected error from /192.168.240.9; closing connection (org.apache.kafka.common.network.Selector)
kafka            | org.apache.kafka.common.network.InvalidReceiveException: Invalid receive (size = 1347375956 larger than 104857600)
kafka            |      at org.apache.kafka.common.network.NetworkReceive.readFrom(NetworkReceive.java:105)
kafka            |      at org.apache.kafka.common.network.KafkaChannel.receive(KafkaChannel.java:447)
kafka            |      at org.apache.kafka.common.network.KafkaChannel.read(KafkaChannel.java:397)
kafka            |      at org.apache.kafka.common.network.Selector.attemptRead(Selector.java:678)
kafka            |      at org.apache.kafka.common.network.Selector.pollSelectionKeys(Selector.java:580)
kafka            |      at org.apache.kafka.common.network.Selector.poll(Selector.java:485)
kafka            |      at kafka.network.Processor.poll(SocketServer.scala:913)
kafka            |      at kafka.network.Processor.run(SocketServer.scala:816)
kafka            |      at java.lang.Thread.run(Thread.java:748)
metricbeat       | 2022-07-30T06:40:02.106Z     INFO    module/wrapper.go:259   Error fetching data for metricset kafka.broker: error making http request: Post "http://kafka:9092/jolokia/%3FignoreErrors=true&canonicalNaming=false": read tcp 192.168.240.9:52718->192.168.240.7:9092: read: connection reset by peer
logstash_1       | [2022-07-30T06:40:05,490][WARN ][logstash.outputs.elasticsearch][main] Attempted to resurrect connection to dead ES instance, but got an error. {:url=>"http://elasticsearch:9200/", :error_type=>LogStash::Outputs::ElasticSearch::HttpClient::Pool::HostUnreachableError, :error=>"Elasticsearch Unreachable: [http://elasticsearch:9200/][Manticore::ResolutionFailure] elasticsearch: Name or service not known"}
kafka-manager    | 2022-07-30 06:40:08,051 - [INFO] k.m.a.KafkaManagerActor - Updating internal state...
logstash_1       | [2022-07-30T06:40:10,498][WARN ][logstash.outputs.elasticsearch][main] Attempted to resurrect connection to dead ES instance, but got an error. {:url=>"http://elasticsearch:9200/", :error_type=>LogStash::Outputs::ElasticSearch::HttpClient::Pool::HostUnreachableError, :error=>"Elasticsearch Unreachable: [http://elasticsearch:9200/][Manticore::ResolutionFailure] elasticsearch"}
logstash_1       | [2022-07-30T06:40:13,486][ERROR][logstash.licensechecker.licensereader] Unable to retrieve license information from license server {:message=>"No Available connections"}
logstash_1       | [2022-07-30T06:40:13,914][WARN ][logstash.licensechecker.licensereader] Attempted to resurrect connection to dead ES instance, but got an error. {:url=>"http://elasticsearch:9200/", :error_type=>LogStash::Outputs::ElasticSearch::HttpClient::Pool::HostUnreachableError, :error=>"Elasticsearch Unreachable: [http://elasticsearch:9200/][Manticore::ResolutionFailure] elasticsearch"}
logstash_1       | [2022-07-30T06:40:15,506][WARN ][logstash.outputs.elasticsearch][main] Attempted to resurrect connection to dead ES instance, but got an error. {:url=>"http://elasticsearch:9200/", :error_type=>LogStash::Outputs::ElasticSearch::HttpClient::Pool::HostUnreachableError, :error=>"Elasticsearch Unreachable: [http://elasticsearch:9200/][Manticore::ResolutionFailure] elasticsearch: Name or service not known"}
kafka-manager    | 2022-07-30 06:40:18,051 - [INFO] k.m.a.KafkaManagerActor - Updating internal state...
^CGracefully stopping... (press Ctrl+C again to force)
Stopping kafka-manager                                                        ... done
Stopping elastic-grafana-kafka-kibana-logstash-metricbeat-telegraf_logstash_1 ... done
Stopping metricbeat                                                           ... done
Stopping kafka                                                                ... done
Stopping elastic-grafana-kafka-kibana-logstash-metricbeat-telegraf_kibana_1   ... done
Stopping zookeeper                                                            ... done
Stopping grafana                                                              ... done
Stopping telegraf                                                             ... done
```
