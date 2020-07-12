# devenv-kafka

Local Development Environment for Apache Kafka. Provides you with an opinionated single node
cluster for local development consisting of

 * Zookeper
 * Broker
 * Schema Registry (http://localhost:8081)
 * Kafka Connect (http://localhost:8083)
 * Confluent Control Center (http://localhost:9021)

In addition, it contains other services I commonly use in conjunction with Kafka:

 * Single node Elastic-Stack consisting of Elasticsearch (http://localhost:9200) and Kibana
   (http://localhost:5601)
 * Prometheus + Grafana (TBD)


# Connect Configuration

The provided Kafka Connect service can be configured to use components provided by the confluent
hub. To this end, the `connect` folder is mounted into the connect container. In order to use
a custom component from [confluent hub](https://www.confluent.io/hub/), install it using the
CLI

```bash
confluent-hub install --component-dir connect custom/component:0.1.0
```