# latest confluent kafka connect image [base image]
FROM confluentinc/cp-kafka-connect:6.1.1

# connectors from confluent hub
# debezium [mysql, postgresql, sql server, mongodb]
# mongodb, file pulse, snowflake
RUN confluent-hub install --no-prompt mongodb/kafka-connect-mongodb:1.1.0 \
&&  confluent-hub install --no-prompt debezium/debezium-connector-mysql:1.1.0 \
&&  confluent-hub install --no-prompt debezium/debezium-connector-postgresql:1.1.0 \
&&  confluent-hub install --no-prompt debezium/debezium-connector-sqlserver:1.1.0 \
&&  confluent-hub install --no-prompt confluentinc/kafka-connect-jdbc:10.1.1
# RUN confluent-hub install --no-prompt debezium/debezium-connector-mongodb:1.1.0
# RUN confluent-hub install --no-prompt streamthoughts/kafka-connect-file-pulse:1.2.1
# RUN confluent-hub install --no-prompt snowflakeinc/snowflake-kafka-connector:1.2.4

# copy mssql and mysql jar files to image
COPY mssql-jdbc-7.2.1.jre8.jar /usr/share/java/kafka-connect-jdbc
COPY mysql-connector-java-8.0.16.jar /usr/share/java/kafka-connect-jdbc
COPY postgresql-42.2.20.jar /usr/share/java/kafka-connect-jdbc

