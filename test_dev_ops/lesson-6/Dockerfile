FROM ubuntu:18.04
MAINTAINER Vlad Kamerdinerov <anakin174jedi@gmail.com>
ENV TOMCAT_VERSION 8.5.50
RUN apt update && apt upgrade -y
RUN apt install default-jdk maven git wget -y
EXPOSE 8080
RUN wget --quiet --no-cookies https://archive.apache.org/dist/tomcat/tomcat-8/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz -O /tmp/tomcat.tgz && \
tar xzvf /tmp/tomcat.tgz -C /opt && \
mv /opt/apache-tomcat-${TOMCAT_VERSION} /opt/tomcat && \
rm /tmp/tomcat.tgz && \
rm -rf /opt/tomcat/webapps/examples && \
rm -rf /opt/tomcat/webapps/docs && \
rm -rf /opt/tomcat/webapps/ROOT
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
RUN mvn -f /boxfuse-sample-java-war-hello/pom.xml clean package
RUN cp /boxfuse-sample-java-war-hello/target/hello-1.0.war /opt/tomcat/webapps
CMD ["/opt/tomcat/bin/catalina.sh", "run"]








