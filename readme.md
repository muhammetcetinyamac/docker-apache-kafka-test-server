# Dockerized Kafka Test Server
## Installation
```sh
git clone https://github.com/muhammetcetinyamac/docker-apache-kafka-test-server.git
cd docker-apache-kafka-test-server
docker-compose -f docker-compose.yaml up
```

## Configuration
The configuration can easily be setup with the Bitnami Apache Kafka Docker image using the following environment
- KAFKA_CERTIFICATE_PASSWORD: Password for certificates. No defaults.
- KAFKA_HEAP_OPTS: Apache Kafka's Java Heap size. Default: -Xmx1024m -Xms1024m.
- KAFKA_ZOOKEEPER_PROTOCOL: Authentication protocol for Zookeeper connections. Allowed protocols: PLAINTEXT, SASL, SSL, and SASL_SSL. Defaults: PLAINTEXT.
- KAFKA_ZOOKEEPER_USER: Apache Kafka Zookeeper user for SASL authentication. No defaults.
- KAFKA_ZOOKEEPER_PASSWORD: Apache Kafka Zookeeper user password for SASL authentication. No defaults.
- KAFKA_ZOOKEEPER_TLS_KEYSTORE_PASSWORD: Apache Kafka Zookeeper keystore file password and key password. No defaults.
- KAFKA_ZOOKEEPER_TLS_TRUSTSTORE_PASSWORD: Apache Kafka Zookeeper truststore file password. No defaults.
- KAFKA_ZOOKEEPER_TLS_VERIFY_HOSTNAME: Verify Zookeeper hostname on TLS certificates. Defaults: true.
- KAFKA_ZOOKEEPER_TLS_TYPE: Choose the TLS certificate format to use. Allowed values: JKS, PEM. Defaults: JKS.
- KAFKA_CFG_LISTENERS: Kafka listeners configuration override. No defaults.
- KAFKA_CFG_ADVERTISED_LISTENERS: Kafka advertised.listeners configuration override. No defaults.
- KAFKA_CFG_SASL_ENABLED_MECHANISMS: Allowed mechanism when using SASL either for clients, inter broker, or zookeeper comunications. Allowed values: PLAIN, SCRAM-SHA-256, SCRAM-SHA-512 or a comma separated combination of those values. Default: PLAIN,SCRAM-SHA-256,SCRAM-SHA-512. NOTE: KRaft <= 3.4 does not yet support SCRAM mechanisms, so this list will be automatically reduced to only PLAIN SASL mechanism.
- KAFKA_TLS_CLIENT_AUTH: Sets the value for ssl.client.auth. Allowed values: required, requested, none. Defaults: required.
- KAFKA_TLS_<uppercase_listener_name>_CLIENT_AUTH: Sets the value for listener.name.<listener>.ssl.client.auth used to configure mTLS with SASL. Allowed values: required, requested, none.
- KAFKA_TLS_TYPE: Choose the TLS certificate format to use. Allowed values: JKS, PEM. Defaults: JKS.
- KAFKA_CLIENT_USERS: Users that will be created into Zookeeper when using SASL for client communications. Separated by commas. Default: user
- KAFKA_CLIENT_PASSWORDS: Passwords for the users specified atKAFKA_CLIENT_USERS. Separated by commas. Default: bitnami
- KAFKA_CFG_MAX_PARTITION_FETCH_BYTES: The maximum amount of data per-partition the server will return. No defaults.
- KAFKA_CFG_MAX_REQUEST_SIZE: The maximum size of a request in bytes. No defaults.
- KAFKA_CFG_SASL_MECHANISM_INTER_BROKER_PROTOCOL: SASL mechanism to use for inter broker communications. No defaults. NOTE: KRaft <= 3.4 does not yet support SCRAM mechanisms, so the only supported SASL mechanism in KRaft mode would be PLAIN.
- KAFKA_INTER_BROKER_USER: Apache Kafka inter broker communication user. Default: user.
- KAFKA_INTER_BROKER_PASSWORD: Apache Kafka inter broker communication password. Default: bitnami.
- KAFKA_CFG_SASL_MECHANISM_CONTROLLER_PROTOCOL: SASL mechanism to use for controllers communications. No defaults. NOTE: KRaft <= 3.4 does not yet support SCRAM mechanisms, so the only supported SASL mechanism in KRaft mode would be PLAIN.
- KAFKA_CONTROLLER_USER: Apache Kafka controllers communication user. Default: controller_user.
- KAFKA_CONTROLLER_PASSWORD: Apache Kafka controllers communication password. Default: bitnami.
- KAFKA_CFG_PROCESS_ROLES: Node roles when running in KRaft mode. No defaults.
- KAFKA_CFG_NODE_ID: Unique node id, required when running in KRaft mode. No defaults.
- KAFKA_CFG_CONTROLLER_QUORUM_VOTERS: Map of id/endpoint information for the set of controller quorum voters in a comma-separated list of {id}@{host}:{port} entries. No defaults.
- KAFKA_KRAFT_CLUSTER_ID: Kafka cluster ID when using Kafka Raft (KRaft). No defaults.

For source and detailed information: https://hub.docker.com/r/bitnami/kafka
