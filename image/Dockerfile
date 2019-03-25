FROM zer0i3/tomcat8-mysql:v1.0.4

MAINTAINER zer0i3 <zer0i3@aliyun.com>

#Install dependencies
RUN apt-get update && \
    apt-get -y dist-upgrade && \
    apt-get -y install git maven zip && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

#Get imxss and generate tar
RUN git clone https://gitee.com/coodyer/imxss.git /tmp/imxss && \
    cd /tmp/imxss && mvn package

#Deploy tar
RUN rm -rf /opt/tomcat/webapps/* && \
    unzip /tmp/imxss/target/imxss.war -d /opt/tomcat/webapps/ROOT && \
    chown -R www-data:www-data /opt/tomcat/webapps/ && \
    mkdir /data && \
    chown -R www-data:www-data /data && \
    rm -rf /tmp/* /var/tmp/*

VOLUME /opt/tomcat/webapps/ROOT/
