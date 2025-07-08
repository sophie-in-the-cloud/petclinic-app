FROM tomcat:9.0-jdk11
RUN rm -rf /usr/local/tomcat/webapps/ROOT
RUN apt-get update && apt-get install -y unzip wget
WORKDIR /tmp
RUN wget https://github.com/ran-jit/tomcat-cluster-redis-session-manager/releases/download/2.0.4/tomcat-cluster-redis-session-manager.zip && unzip tomcat-cluster-redis-session-manager.zip
COPY /tmp/tomcat-cluster-redis-session-manager/lib/* /usr/local/tomcat/lib/
COPY /tmp/tomcat-cluster-redis-session-manager/conf/* /usr/local/tomcat/conf
COPY redis-data-cache.properties /usr/local/tomcat/conf/
COPY context.xml /usr/local/tomcat/conf/
COPY target/petclinic.war /usr/local/tomcat/webapps/ROOT.war
COPY session_check.jsp /usr/local/tomcat/webapps/ROOT/
