FROM openjdk:8

RUN apt-get update
RUN apt-get install -y zip
RUN curl -s "https://get.sdkman.io" | bash
RUN bash -c ' . "/root/.sdkman/bin/sdkman-init.sh" && sdk install gradle 3.4.1'
RUN mkdir -p /opt
WORKDIR /opt
ADD https://github.com/apache/kafka/archive/0.10.2.0.tar.gz /opt/.
RUN tar xf *.gz
WORKDIR /opt/kafka-0.10.2.0
RUN /root/.sdkman/candidates/gradle/3.4.1/bin/gradle
RUN ./gradlew jar
EXPOSE 2181
CMD bin/zookeeper-server-start.sh config/zookeeper.properties

