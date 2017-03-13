FROM openjdk:8

ADD https://dl.bintray.com/sbt/debian/sbt-0.13.13.deb /tmp/.
RUN dpkg -i /tmp/*.deb
ADD https://github.com/yahoo/kafka-manager/archive/1.3.3.4.tar.gz /tmp/.
WORKDIR /tmp
RUN tar -xf *.gz
WORKDIR /opt/kafka-manager-1.3.3.4
RUN sbt clean dist
RUN mkdir -p /opt/

