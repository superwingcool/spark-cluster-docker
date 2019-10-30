FROM centos:7
LABEL author="superwingcool" email="superwingcool@gmail.com"
LABEL version="1.0"

ENV JDK_VERSION=jdk-8u45-linux-x64.tar.gz
ENV JAVA_HOME=/usr/local/jdk
ENV SPARK_VERSION=spark-2.3.4-bin-hadoop2.7
ENV SPARK_HOME=/spark

COPY  software/${JDK_VERSION} /tmp
COPY  software/${SPARK_VERSION}.tar /tmp

WORKDIR /tmp

#install java
RUN tar -zxvf ${JDK_VERSION}  \
    && mv jdk1.8.0_45 /usr/local/jdk \
    && rm ${JDK_VERSION}

ENV JAVA_HOME ${JAVA_HOME}
ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin

#install spark
RUN tar -xvf ${SPARK_VERSION}.tar  \
    && mv ${SPARK_VERSION} ${SPARK_HOME} \
    && rm ${SPARK_VERSION}.tar

