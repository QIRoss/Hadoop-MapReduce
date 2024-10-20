FROM maven:3.8.1-openjdk-11 AS builder
WORKDIR /app

COPY . .

RUN mvn clean package

FROM flink:1.15
COPY --from=builder /app/target/flink-kafka-example-1.0-SNAPSHOT.jar /opt/flink/usrlib/

CMD ["flink", "run", "/opt/flink/usrlib/flink-kafka-example-1.0-SNAPSHOT.jar"]
