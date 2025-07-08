FROM tomcat:9.0-jdk11
RUN rm -rf /usr/local/tomcat/webapps/ROOT
RUN apt-get update && apt-get install -y unzip wget

COPY tomcat-cluster-redis-session-manager/lib/* /usr/local/tomcat/lib/
COPY tomcat-cluster-redis-session-manager/conf/* /usr/local/tomcat/conf
COPY redis-data-cache.properties /usr/local/tomcat/conf/
COPY context.xml /usr/local/tomcat/conf/
COPY target/petclinic.war /usr/local/tomcat/webapps/ROOT.war
COPY session_check.jsp /usr/local/tomcat/webapps/ROOT/
